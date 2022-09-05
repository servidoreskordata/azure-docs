---
title: Secure Azure Kubernetes Service inferencing environment
description: Learn about securing an Azure Kubernetes Service inferencing environment and how to configure it. 
titleSuffix: Azure Machine Learning
author: bozhong68
ms.author: bozhlin
ms.reviewer: larryfr ssalgado
ms.service: machine-learning
ms.subservice: core
ms.date: 08/31/2022
ms.topic: how-to
ms.custom: build-spring-2022, cliv2, sdkv2, event-tier1-build-2022
#customer intent: I would like to have machine learning with all private IP only 
---

# Secure Azure Kubernetes Service inferencing environment

If you have an Azure Kubernetes (AKS) cluster behind of VNet, you would need to secure Azure Machine Learning workspace resources and compute environment using the same VNet. In this article, you'll learn: 
  * What is a secure AKS inferencing environment
  * How to configure a secure AKS inferencing environment

## What is a secure AKS inferencing environment

Azure Machine Learning AKS inferencing environment consists of workspace, your AKS cluster, and workspace associated resources - Azure Storage, Azure Key Vault, and Azure Container Services(ARC). The following table compares how services access different part of Azure Machine Learning network with or without a VNet.

| Scenario | Workspace | Associated resources (Storage account, Key Vault, ACR) | AKS cluster |
|-|-|-|-|-|
|**No virtual network**| Public IP | Public IP | Public IP |
|**Public workspace, all other resources in a virtual network** | Public IP | Public IP (service endpoint) <br> **- or -** <br> Private IP (private endpoint) | Private IP  |
|**Secure resources in a virtual network**| Private IP (private endpoint) | Public IP (service endpoint) <br> **- or -** <br> Private IP (private endpoint) | Private IP  | 

In a secure AKS inferencing environment, AKS cluster accesses different part of Azure Machine Learning services with private endpoint only (private IP). The following network diagram shows a secured Azure Machine Learning workspace with a private AKS cluster or default AKS cluster behind of VNet.

 [![A secure AKS inferencing envrionment: AKS cluster accesses different part of AzureML services with private endpoint, including workspace and its associated resources](./media/how-to-network-security-overview/secure-inferencing-environment.svg)](./media/how-to-network-security-overview/secure-inferencing-environment.svg)

## How to configure a secure AKS inferencing environment

To configure a secure AKS inferencing environment, you must have VNet information for AKS. [VNet](../virtual-network/quick-create-portal.md) can be created independently or during AKS cluster deployment. There are two options for AKS cluster in a VNet:
  * Deploy default AKS cluster to your VNet
  * Or create private AKS cluster to your VNet

For default AKS cluster, you can find VNet information under the resource group of `MC_[rg_name][aks_name][region]`. 

After you have VNet information for AKS cluster and if you already have workspace available, use following steps to configure a secure AKS inferencing environment:
  
  * Use your AKS cluster VNet information to add new private endpoints for the Azure Storage Account, Azure Key Vault, and Azure Container Registry used by your workspace. These private endpoints should exist in the same VNet as AKS cluster. For more information, see the [secure workspace with private endpoint](./how-to-secure-workspace-vnet.md#secure-the-workspace-with-private-endpoint) article.
  * If you have other storage that is used by your workspace, add a new private endpoint for that storage. The private endpoint should exist in the AKS cluster VNet and have private DNS zone integration enabled.
  * Add a new private endpoint to your workspace. This private endpoint should exist in AKS cluster VNet and have private DNS zone integration enabled.

If you have AKS cluster ready but don't have workspace created yet, you can use AKS cluster VNet when creating the workspace. Use the AKS cluster VNet information when following the [create secure workspace](./tutorial-create-secure-workspace.md) tutorial. Once the workspace has been created, add a new private endpoint to your workspace as the last step. For all the above steps, it's important to ensure that all private endpoints should exist in the same AKS cluster VNet and have private DNS zone integration enabled.

Special notes for configuring a secure AKS inferencing environment:
  * Use system-assigned managed identity when creating workspace, as storage account with private endpoint only allows access with system-assigned managed identity.
  * When attaching AKS cluster to an HBI workspace, assign a system-assigned managed identity with both `Storage Blob Data Contributor` and `Storage Account Contributor` roles.
  * If you're using default ACR created by workspace, ensure you have the __premium SKU__ for ACR. Also enable the `Firewall exception` to allow trusted Microsoft services to access ACR.
  * If your workspace is also behind of VNet, follow instruction [securely connect to your workspace](./how-to-secure-workspace-vnet.md#securely-connect-to-your-workspace) to access workspace.
  * For storage account private endpoint, make sure to enable `Allow Azure services on the trusted services list to access this storage account`.

## Next steps

This article is part of a series on securing an Azure Machine Learning workflow. See the other articles in this series:

* [Virtual network overview](how-to-network-security-overview.md)
* [Secure the training environment](how-to-secure-training-vnet.md)
* [Secure online endpoints (inference)](how-to-secure-online-endpoint.md)
* [Enable studio functionality](how-to-enable-studio-virtual-network.md)
* [Use custom DNS](how-to-custom-dns.md)
* [Use a firewall](how-to-access-azureml-behind-firewall.md)
* [Tutorial: Create a secure workspace](tutorial-create-secure-workspace.md)
* [Tutorial: Create a secure workspace using a template](tutorial-create-secure-workspace-template.md)
* [API platform network isolation](how-to-configure-network-isolation-with-v2.md)