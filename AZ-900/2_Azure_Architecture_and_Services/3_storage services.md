## Azure storage accounts
A storage account provides a unique namespace for your Azure Storage data that's accessible from anywhere in the world over HTTP or HTTPS.

redundancy options
- Locally redundant storage (LRS)
- Geo-redundant storage (GRS)
- Read-access geo-redundant storage (RA-GRS)
- Zone-redundant storage (ZRS)
- Geo-zone-redundant storage (GZRS)
- Read-access geo-zone-redundant storage (RA-GZRS)

|Type	| Supported services | Redundancy Options	| Usage|
|---|---|---|---|
| Standard general-purpose v2	| Blob Storage (including Data Lake Storage), Queue Storage, Table Storage, and Azure Files	| LRS, GRS, RA-GRS, ZRS, GZRS, RA-GZRS	| Standard storage account type for blobs, file shares, queues, and tables. Recommended for most scenarios using Azure Storage. If you want support for network file system (NFS) in Azure Files, use the premium file shares account type.|
|Premium block blobs	|Blob Storage (including Data Lake Storage)	|LRS, ZRS	|Premium storage account type for block blobs and append blobs. Recommended for scenarios with high transaction rates or that use smaller objects or require consistently low storage latency.|
|Premium file shares	|Azure Files	|LRS, ZRS	|Premium storage account type for file shares only. Recommended for enterprise or high-performance scale applications. Use this account type if you want a storage account that supports both Server Message Block (SMB) and NFS file shares.|
|Premium page blobs	|Page blobs only	|LRS	|Premium storage account type for page blobs only.|

### storage account naming rules
- names must be between 3 and 24 characters in length and may contain numbers and lowercase letters only.
- name must be unique within Azure.

## Redundancy
### Redundancy in the primary region (synchronously)
Data in an Azure Storage account is always replicated three times in the primary region.
- Locally redundant storage
  - Locally redundant storage (LRS) replicates your data three times within a single data center in the primary region.
  - LRS provides at least 11 nines of durability (99.999999999%) of objects over a given year.
- Zone-redundant storage
  - replicates your Azure Storage data synchronously across three Azure availability zones in the primary region.
  - ZRS offers durability for Azure Storage data objects of at least 12 nines (99.9999999999%) over a given year.

### Redundancy in a secondary region (asynchronously)
copy the data in your storage account to a secondary region that is hundreds of miles away from the primary region.
- geo-redundant storage (GRS)
  - GRS copies your data synchronously three times within a single physical location in the primary region using LRS. 
  - GRS copies your data asynchronously to a single physical location in the secondary region (the region pair) using LRS. 
  - GRS offers durability for Azure Storage data objects of at least 16 nines (99.99999999999999%) over a given year.
- geo-zone-redundant storage (GZRS)
  - GZRS storage account is copied across three Azure availability zones in the primary region (similar to ZRS)
  - GZRS data replicated to a secondary geographic region, using LRS, for protection from regional disasters.
  - GZRS is designed to provide at least 16 nines (99.99999999999999%) of durability of objects over a given year.

### Read access to data in the secondary region
- By default, data in the secondary region is available to be read only if the customer or Microsoft initiates a failover from the primary to secondary region.
- However, if you enable read access to the secondary region, your data is always available, even when the primary region is running optimally. 
  - read-access geo-redundant storage (RA-GRS) 
  - read-access geo-zone-redundant storage (RA-GZRS)

## Azure storage services
- **Azure blobs**: A massively scalable object store for text and binary data. Also includes support for big data analytics through Data Lake Storage Gen2.
  - text or binary data
  - unstructured
  - storage tiers
    - Hot
    - Cool (store for at least 30 days)
    - Achive (store for at least 180 days)
- **Azure files**: Managed file shares for cloud or on-premises deployments.
- **Azure queues**: A messaging store for reliable messaging between application components.
- **Azure disks**: Block-level storage volumes for Azure VMs. 

## Azure data migration options
- **Azure Migrate**: Azure Migrate is a service that helps you migrate from an on-premises environment to the cloud.
- **Azure Data Box**: Azure Data Box is a physical migration service that helps transfer large amounts of data in a quick, inexpensive, and reliable way. (data sizes larger than 40 TBs)

### Azure file movement options
- AzCopy
- Azure Storage Explorer
  - GUI to manage files and blobs in your Azure Storage Account.
  - uses AzCopy on the backend.
- Azure File Sync
  - Azure File Sync maintains a bidirectional synchronization of files between your on-premises and cloud Windows servers.


