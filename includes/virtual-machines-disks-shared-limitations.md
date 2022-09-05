---
 title: include file
 description: include file
 services: virtual-machines
 author: roygara
 ms.service: virtual-machines
 ms.topic: include
 ms.date: 08/01/2022
 ms.author: rogarana
 ms.custom: include file
---

### General limitations

Enabling shared disks is only available to a subset of disk types. Currently only ultra disks, premium SSD v2 (preview), premium SSDs, and standard SSDs can enable shared disks. Shared disks can be attached to individual VMSS instances but can't be defined in the VMSS models or automatically deployed.

Each managed disk that has shared disks enabled are also subject to the following limitations, organized by disk type:

### Ultra disks

Ultra disks have their own separate list of limitations, unrelated to shared disks. For ultra disk limitations, refer to [Using Azure ultra disks](../articles/virtual-machines/disks-enable-ultra-ssd.md).

When sharing ultra disks, they have the following additional limitations:

- Only basic disks can be used with some versions of Windows Server Failover Cluster, for details see [Failover clustering hardware requirements and storage options](/windows-server/failover-clustering/clustering-requirements).
- Can't be shared across availability zones.


### Premium SSD v2 (preview)

Premium SSD v2 disks have their own separate list of limitations, unrelated to shared disks. For these limitations, see [Premium SSD v2 limitations](../articles/virtual-machines/disks-types.md#premium-ssd-v2-limitations).

When sharing Premium SSD v2 disks, they have the following additional limitation:

- Only basic disks can be used with some versions of Windows Server Failover Cluster, for details see [Failover clustering hardware requirements and storage options](/windows-server/failover-clustering/clustering-requirements).
- Can't be shared across availability zones.

### Premium SSD

- Can only be enabled on data disks, not OS disks.
- Host caching isn't available for premium SSD disks with `maxShares>1`.
- Disk bursting isn't available for premium SSD disks with `maxShares>1`.
- When using Availability sets or virtual machine scale sets with Azure shared disks, [storage fault domain alignment](../articles/virtual-machines/availability.md) with virtual machine fault domain isn't enforced for the shared data disk.
- When using [proximity placement groups (PPG)](../articles/virtual-machines/windows/proximity-placement-groups.md), all virtual machines sharing a disk must be part of the same PPG.
- Only basic disks can be used with some versions of Windows Server Failover Cluster, for details see [Failover clustering hardware requirements and storage options](/windows-server/failover-clustering/clustering-requirements).
- Azure Site Recovery support isn't yet available.
- Azure Backup is available through [Azure Disk Backup](../articles/backup/disk-backup-overview.md).
- Only [server-side encryption](../articles/virtual-machines/disk-encryption.md) is supported, [Azure Disk Encryption](../articles/virtual-machines/windows/disk-encryption-overview.md) isn't currently supported.
- Can only be shared across availability zones if using [Zone-redundant storage for managed disks](../articles/virtual-machines/disks-redundancy.md#zone-redundant-storage-for-managed-disks).

### Standard SSDs

- Can only be enabled on data disks, not OS disks.
- Host caching isn't available for standard SSDs with `maxShares>1`.
- When using Availability sets and virtual machine scale sets with Azure shared disks, [storage fault domain alignment](../articles/virtual-machines/availability.md) with virtual machine fault domain isn't enforced for the shared data disk.
- When using [proximity placement groups (PPG)](../articles/virtual-machines/windows/proximity-placement-groups.md), all virtual machines sharing a disk must be part of the same PPG.
- Only basic disks can be used with some versions of Windows Server Failover Cluster, for details see [Failover clustering hardware requirements and storage options](/windows-server/failover-clustering/clustering-requirements).
- Azure Site Recovery support isn't yet available.
- Azure Backup is available through [Azure Disk Backup](../articles/backup/disk-backup-overview.md).
- Only [server-side encryption](../articles/virtual-machines/disk-encryption.md) is supported, [Azure Disk Encryption](../articles/virtual-machines/windows/disk-encryption-overview.md) isn't currently supported.
- Can only be shared across availability zones if using [Zone-redundant storage for managed disks](../articles/virtual-machines/disks-redundancy.md#zone-redundant-storage-for-managed-disks).