---
title: What's New in Azure Cache for Redis
description: Recent updates for Azure Cache for Redis
author: flang-msft

ms.author: franlanglois
ms.service: cache
ms.topic: reference
ms.date: 09/01/2022

---

# What's New in Azure Cache for Redis

## September 2022

### Support for managed identity in Azure Cache for Redis

Authenticating storage account connections using managed identity has now reached General Availability (GA).

For more information, see [Managed identity for storage](cache-managed-identity.md).

## August 2022

### RedisJSON module available in Azure Cache for Redis Enterprise  

The Enterprise and Enterprise Flash tiers of Azure Cache for Redis now support the **RedisJSON** module. This module adds native functionality to store, query, and search JSON-formatted data that allows you to store data more easily in a document-style format in Redis. By using this module, you simplify common use cases like storing product catalog or user profile data.  

The **RedisJSON** module implements the community version of the module so you can use your existing knowledge and workstreams. **RedisJSON** is  designed for use with the search functionality of **RediSearch**. Using both modules provides integrated indexing and querying of data. For more information, see [RedisJSON](https://aka.ms/redisJSON).

The **RediSearch** module is also now available for Azure Cache for Redis. For more information on using Redis modules in Azure Cache for Redis, see [Use Redis modules with Azure Cache for Redis](cache-redis-modules.md).

## July 2022

### Redis 6 becomes default for new cache instances

Beginning November 1, 2022, all versions of Azure Cache for Redis REST API, PowerShell, Azure CLI, and Azure SDK will create Redis instances using the latest stable version of Redis offered by Azure Cache for Redis by default. Previously, Redis version 4.0 was the default version used. However, as of October 2021, the latest stable Redis version offered in Azure Cache for Redis is 6.0.

>[!NOTE]
> This change does not affect any existing instances. It is only applicable to new instances created from November 1, 2022, and onward.
>
> The default Redis version that is used when creating a cache instance can vary because it is  based on the latest stable version offered in Azure Cache for Redis.

If you need a specific version of Redis for your application, we recommend using latest artifact versions as shown in the table below. Then, choose the Redis version explicitly when you create the cache.

| Artifact | Version that  supports specifying Redis version  |
|---------|---------|
| REST API              | 2020-06-01 and newer |
| PowerShell            | 6.3.0 and newer |
| Azure CLI             | 2.27.0 and newer |
| Azure SDK for .NET  | 7.0.0 and newer |
| Azure SDK for Python | 13.0.0 and newer |
| Azure SDK  for Java  | 2.2.0 and newer |
| Azure SDK for JavaScript| 6.0.0 and newer |
| Azure SDK for Go    | v49.1.0 and newer |

## April 2022

### New metrics for connection creation rate

These two new metrics can help identify whether Azure Cache for Redis clients are frequently disconnecting and reconnecting, which can cause higher CPU usage and **Redis Server Load**.

- Connections Created Per Second
- Connections Closed Per Second

For more information, see [View cache metrics](cache-how-to-monitor.md#view-cache-metrics).

### Default cache change

On May 15, 2022, all new Azure Cache for Redis instances will use Redis 6 by default. You can still create a Redis 4 instance by explicitly selecting the version when you create an Azure Cache for Redis instance.

This change doesn't affect any existing instances. The change is only applicable to new instances created after May 15, 2022.

The default version of Redis that is used when creating a cache can change over time. Azure Cache for Redis might adopt a new version when a new version of open-source Redis is released. If you need a specific version of Redis for your application, we recommend choosing the Redis version explicitly when you create the cache.

## February 2022

### TLS Certificate Change

As of May 2022, Azure Cache for Redis rolls over to TLS certificates issued by DigiCert Global G2 CA Root. The current Baltimore CyberTrust Root expires in May 2025, requiring this change.

We expect that most Azure Cache for Redis customers won't be affected. However, your application might be affected if you explicitly specify a list of acceptable certificate authorities (CAs), known as *certificate pinning*.

For more information, read this blog that contains instructions on [how to check whether your client application is affected](https://techcommunity.microsoft.com/t5/azure-developer-community-blog/azure-cache-for-redis-tls-upcoming-migration-to-digicert-global/ba-p/3171086). We recommend taking the actions recommended in the blog to avoid cache connectivity loss.

### Active geo-replication for Azure Cache For Redis Enterprise GA

Active geo-replication for Azure Cache for Redis Enterprise is now generally available (GA).

Active geo-replication is a powerful tool that enables Azure Cache for Redis clusters to be linked together for seamless active-active replication of data. Your applications can write to one Redis cluster and your data is automatically copied to the other linked clusters, and vice versa. For more information, see this [post](https://aka.ms/ActiveGeoGA) in the *Azure Developer Community Blog*.

## January 2022

### Support for managed identity in Azure Cache for Redis

Azure Cache for Redis now supports authenticating storage account connections using managed identity. Identity is established through Azure Active Directory, and both system-assigned and user-assigned identities are supported. Support for managed identity further allows the service to establish trusted access to storage for uses including data persistence and importing/exporting cache data.

For more information, see [Managed identity with Azure Cache for Redis](cache-managed-identity.md).

## October 2021

### Azure Cache for Redis 6.0 GA

Azure Cache for Redis 6.0 is now generally available. The new version includes:

- Redis Streams, a new data type
- Performance enhancements
- Enhanced developer productivity
- Boosts security

You can now use an append-only data structure, Redis Streams, to ingest, manage, and make sense of data that is continuously being generated.

Additionally, Azure Cache for Redis 6.0 introduces new commands: `STRALGO`, `ZPOPMIN`, `ZPOPMAX`, and `HELP` for performance and ease of use.

Get started with Azure Cache for Redis 6.0, today, and select Redis 6.0 during cache creation. Also, you can upgrade your existing Redis 4.0 cache instances. For more information, see [Set Redis version for Azure Cache for Redis](cache-how-to-version.md).

### Diagnostics for connected clients

Azure Cache for Redis now integrates with Azure diagnostic settings to log information on all client connections to your cache. Logging and then analyzing this diagnostic setting helps you understand who is connecting to your caches and the timestamp of those connections. This data could be used to identify the scope of a security breach and for security auditing purposes. Users can route these logs to a destination of their choice, such as a storage account or Event Hubs.

For more information, see [Monitor Azure Cache for Redis data using diagnostic settings](cache-monitor-diagnostic-settings.md).

### Azure Cache for Redis Enterprise update

Active geo-replication public preview now supports:

- RediSearch Module: Deploy RediSearch with active geo-replication
- Five caches in a replication group. Previously, supported two caches.
- OSS clustering policy - suitable for high-performance workloads and provides better scalability.

## October 2020

### Azure TLS Certificate Change

Microsoft is updating Azure services to use TLS certificates from a different set of Root Certificate Authorities (CAs). This change is being made because the current CA certificates don't comply with one of the CA/Browser Forum Baseline requirements. For full details, see [Azure TLS Certificate Changes](../security/fundamentals/tls-certificate-changes.md).

For more information on the effect to Azure Cache for Redis, see [Azure TLS Certificate Change](cache-best-practices-development.md#azure-tls-certificate-change).

## Next steps

If you have more questions, contact us through [support](https://azure.microsoft.com/support/options/).
