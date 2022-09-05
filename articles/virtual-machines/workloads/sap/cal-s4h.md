---
title: Deploy SAP S/4HANA or BW/4HANA on an Azure VM | Microsoft Docs
description: Deploy SAP S/4HANA or BW/4HANA on an Azure VM
services: virtual-machines-linux
documentationcenter: ''
author: pepeters
manager: timlt
editor: ''
tags: azure-resource-manager
keywords: ''

ms.assetid: 44bbd2b6-a376-4b5c-b824-e76917117fa9
ms.service: virtual-machines
ms.topic: article
ms.tgt_pltfrm: vm-linux
ms.workload: infrastructure-services
ms.date: 06/26/2021
ms.author: hobruche

---
# SAP Cloud Appliance Library

[SAP Cloud Appliance Library](https://cal.sap.com/catalog?provider=208b780d-282b-40ca-9590-5dd5ad1e52e8) offers a quick and easy way to create SAP workloads in Azure. With a few clicks you can set up a fully configured demo environment from an Appliance Template or deploy a standardized system for an SAP product based on default or custom SAP software installation stacks. 
This page lists the latest Appliance Templates and below the latest SAP S/4HANA stacks for production-ready deployments. 

For deployment of an appliance template you will need to authenticate with your S-User or P-User. You can create a P-User free of charge via the [SAP Community](https://community.sap.com/). 



[For details on Azure account creation see the SAP learning video and description](https://www.youtube.com/watch?v=iORePziUMBk&list=PLWV533hWWvDmww3OX9YPhjjS1l1n6o-H2&index=18)

You will also find detailed answers to your questions related to SAP Cloud Appliance Library on Azure [SAP CAL FAQ](https://caldocs.hana.ondemand.com/caldocs/help/Azure_FAQs.pdf)

The online library is continuously updated with Appliances for demo, proof of concept and exploration of new business cases. For the most recent ones select “Create Appliance” here from the list – or visit [cal.sap.com](https://cal.sap.com/catalog#/applianceTemplates) for further templates.

## Deployment of appliances through SAP Cloud Appliance Library

| Appliance Templates | Link |
| -------------- | :--------- |
| **SAP S/4HANA 2021 FPS01, Fully-Activated Appliance**  April 26 2022 | [Create Appliance](https://cal.sap.com/registration?sguid=3f4931de-b15b-47f1-b93d-a4267296b8bc&provider=208b780d-282b-40ca-9590-5dd5ad1e52e8) |
|This appliance contains SAP S/4HANA 2021 (FPS01) with pre-activated SAP Best Practices for SAP S/4HANA core functions, and further scenarios for Service, Master Data Governance (MDG), Portfolio Mgmt. (PPM), Human Capital Management (HCM), Analytics, Migration Cockpit, and more. User access happens via SAP Fiori, SAP GUI, SAP HANA Studio, Windows remote desktop, or the backend operating system for full administrative access. |  [Details]( https://cal.sap.com/catalog?provider=208b780d-282b-40ca-9590-5dd5ad1e52e8#/applianceTemplates/3f4931de-b15b-47f1-b93d-a4267296b8bc) ||
| **SAP S/4HANA 2021 FPS02, Fully-Activated Appliance**  July 19 2022 | [Create Appliance](https://cal.sap.com/registration?sguid=3f4931de-b15b-47f1-b93d-a4267296b8bc&provider=208b780d-282b-40ca-9590-5dd5ad1e52e8) |
|This appliance contains SAP S/4HANA 2021 (FPS02) with pre-activated SAP Best Practices for SAP S/4HANA core functions, and further scenarios for Service, Master Data Governance (MDG), Portfolio Mgmt. (PPM), Human Capital Management (HCM), Analytics, Migration Cockpit, and more. User access happens via SAP Fiori, SAP GUI, SAP HANA Studio, Windows remote desktop, or the backend operating system for full administrative access. |  [Details]( https://cal.sap.com/catalog?provider=208b780d-282b-40ca-9590-5dd5ad1e52e8#/applianceTemplates/3f4931de-b15b-47f1-b93d-a4267296b8bc) |
| **SAP BW/4HANA 2021 including BW/4HANA Content 2.0 SP08 - Dev Edition**  May 11 2022 | [Create Appliance](https://cal.sap.com/registration?sguid=06725b24-b024-4757-860d-ac2db7b49577&provider=208b780d-282b-40ca-9590-5dd5ad1e52e8) |
|This solution offers you an insight of SAP BW/4HANA. SAP BW/4HANA is the next generation Data Warehouse optimized for HANA. Beside the basic BW/4HANA options the solution offers a bunch of HANA optimized BW/4HANA Content and the next step of Hybrid Scenarios with SAP Data Warehouse Cloud. As the system is pre-configured you can start directly implementing your scenarios. |  [Details]( https://cal.sap.com/catalog?provider=208b780d-282b-40ca-9590-5dd5ad1e52e8#/applianceTemplates/06725b24-b024-4757-860d-ac2db7b49577) |
| **SAP S/4HANA 2021, Fully-Activated Appliance**  December 20 2021 | [Create Appliance](https://cal.sap.com/registration?sguid=b8a9077c-f0f7-47bd-977c-70aa6a6a2aa7&provider=208b780d-282b-40ca-9590-5dd5ad1e52e8) |
|This appliance contains SAP S/4HANA 2021 (SP00) with pre-activated SAP Best Practices for SAP S/4HANA core functions, and further scenarios for Service, Master Data Governance (MDG), Transportation Mgmt. (TM), Portfolio Mgmt. (PPM), Human Capital Management (HCM), Analytics, Migration Cockpit, and more. User access happens via SAP Fiori, SAP GUI, SAP HANA Studio, Windows remote desktop, or the backend operating system for full administrative access. |  [Details]( https://cal.sap.com/catalog?provider=208b780d-282b-40ca-9590-5dd5ad1e52e8#/applianceTemplates/b8a9077c-f0f7-47bd-977c-70aa6a6a2aa7) |
| **System Conversion for SAP S/4HANA – Source system SAP ERP6.0 before running SUM** July 05 2022  | [Create Appliance](https://cal.sap.com/registration?sguid=b28b67f3-ebab-4b03-bee9-1cd57ddb41b6&provider=208b780d-282b-40ca-9590-5dd5ad1e52e8) |
|Second solution for performing a system conversion from SAP ERP to SAP S/4HANA after preparation steps before running Software Update Manager. It has been tested and prepared to be converted from SAP EHP7 for SAP ERP 6.0 to SAP S/4HANA 2021 FPS01  |  [Details](https://cal.sap.com/catalog?provider=208b780d-282b-40ca-9590-5dd5ad1e52e8#/applianceTemplates/b28b67f3-ebab-4b03-bee9-1cd57ddb41b6) |
| **SAP NetWeaver 7.5 SP15 on SAP ASE** January 20 2020  | [Create Appliance](https://cal.sap.com/registration?sguid=69efd5d1-04de-42d8-a279-813b7a54c1f6&provider=208b780d-282b-40ca-9590-5dd5ad1e52e8) |
|SAP NetWeaver 7.5 SP15 on SAP ASE |  [Details](https://cal.sap.com/catalog?provider=208b780d-282b-40ca-9590-5dd5ad1e52e8#/solutions/69efd5d1-04de-42d8-a279-813b7a54c1f6) |



## Deployment of S/4HANA system for productive usage through SAP Cloud Appliance Library

You can now also deploy SAP S/4HANA systems with High Availability (HA), non-HA or single server architecture through SAP Cloud Appliance Library. The offering comprises default SAP S/4HANA software stacks including FPS levels as well as an integration into Maintenance Planner to enable creation and installation of custom SAP S/4HANA software stacks.
The following links highlight the Product stacks that you can quickly deploy on Azure. Just select “Deploy System”.

| All products | Link |
| -------------- | :--------- |
| **SAP S/4HANA 2021 FPS01 for Productive Deployments**   | [Deploy System](https://cal.sap.com/catalog#/products) |
|This solution comes as a standard S/4HANA system installation including High Availability capabilities to ensure higher system uptime for productive usage. The system parameters can be customized during initial provisioning according to the requirements for the target system. |
| **SAP S/4HANA 2021 FPS00 for Productive Deployments**   | [Deploy System](https://cal.sap.com/catalog#/products) |
|This solution comes as a standard S/4HANA system installation including High Availability capabilities to ensure higher system uptime for productive usage. The system parameters can be customized during initial provisioning according to the requirements for the target system. |
 
---

_Within a few hours, a healthy SAP S/4HANA appliance or product is deployed in Azure._

If you bought an SAP CAL subscription, SAP fully supports deployments through SAP CAL on Azure. The support queue is BC-VCM-CAL.




