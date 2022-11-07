## Learning objectives
- Azure blob storage
- Azure Data Lake Gen2
- Azure file storage
- Azure table storage
- Provision and use an Azure Storage account


## Azure blob storage
Azure Blob Storage is a service that enables you to store massive amounts of unstructured data as _binary large objects_, or _blobs_, in the cloud. 

Three different types of blob:
- Block blobs
  - Each block can vary in size, up to _100 MB_.
  - A block blob can contain up to _50,000_ blocks, giving a maximum size of over 4.7 TB.
  - The _block_ is the smallest amount of data that can be read or written as an _individual unit_. 
  - Block blobs are best used to store _discrete, large, binary objects_ that change _infrequently_.
- Page blobs
  - A page blob is organized as a collection of _fixed size 512-byte pages_
  - A page blob is optimized to support random read and write operations; you can fetch and store data for a single page if necessary. 
  - A page blob can hold up to _8 TB of data_. 
  - Azure uses page blobs to implement _virtual disk storage_ for virtual machines.
- Append blobs
  - An append blob is a block blob optimized to support append operations. 
  - You can only add blocks to the end of an append blob; updating or deleting existing blocks isn't supported. 
  - Each block can vary in size, up to 4 MB. The maximum size of an append blob is just over 195 GB.

Three access tiers:
- Hot
- Cool
  - lower performance and incurs reduced storage charges
- Achive
  - the lowest storage cost, but with increased latency
  - Blobs in the Archive tier are effectively stored in an _offline state_. 
  - Typical reading latency for the Hot and Cool tiers is a few milliseconds, but for the Archive tier, it can take _hours_ for the data to become available. 
  - To retrieve a blob from the Archive tier, you must _change the access tier to Hot or Cool_. 
  - The blob will then be _rehydrated_. You can read the blob only when the rehydration process is complete.

## Azure DataLake Storage Gen2
- Azure Data Lake Storage Gen2 enables you to take advantage of the scalability of blob storage and the cost-control of storage tiers, combined with the hierarchical file system capabilities and compatibility with major analytics systems of Azure Data Lake Store.
- Systems like Hadoop in Azure HDInsight, Azure Databricks, and Azure Synapse Analytics can mount a distributed file system hosted in Azure Data Lake Store Gen2 and use it to process huge volumes of data.
- To create an Azure Data Lake Store Gen2 files system, you must enable the _Hierarchical Namespace_ option of an Azure Storage account. 

## Azure Files
