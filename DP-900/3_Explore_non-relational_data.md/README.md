# Azure Storage for non-relational data

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
Azure Files enables you to share up to 100 TB of data in a single storage account.

Azure File Storage offers two performance tiers:
- The Standard tier uses hard disk-based hardware in a datacenter
- The Premium tier uses solid-state disks

Azure Files supports two common network file sharing protocols:
- **Server Message Block (SMB)** file sharing is commonly used across multiple operating systems (Windows, Linux, macOS).
- **Network File System (NFS)** shares are used by some Linux and macOS versions. To create an NFS share, you must use a premium tier storage account and create and configure a virtual network through which access to the share can be controlled.

## Azure Tables
Azure Table Storage is a NoSQL storage solution that makes use of tables containing _key/value_ data items.

Azure Table Storage tables have no concept of foreign keys, relationships, stored procedures, views, or other objects you might find in a relational database.

Data in Azure Table storage is usually denormalized, with each row holding the entire data for a logical entity.

To help ensure fast access, Azure Table Storage splits a table into partitions. Partitioning is a mechanism for grouping related rows, based on a common property or partition key.
- Partitions are independent from each other, and can grow or shrink as rows are added to, or removed from, a partition. A table can contain any number of partitions.
- When you search for data, you can include the partition key in the search criteria. This helps to narrow down the volume of data to be examined, and improves performance by reducing the amount of I/O (input and output operations, or reads and writes) needed to locate the data.

The key in an Azure Table Storage table comprises two elements: 
- The partition key that identifies the partition containing the row
- A row key that is unique to each row in the same partition
- Items in the same partition are stored in row key order

# Azure Cosmos DB
Azure Cosmos DB is a highly scalable cloud database service for NoSQL data.

## Learning objectives
- Describe key features and capabilities of Azure Cosmos DB
- Identify the APIs supported in Azure Cosmos DB
- Provision and use an Azure Cosmos DB instance

## When to use Cosmos DB
- Cosmos DB is a highly scalable database management system. 
- Cosmos DB automatically allocates space in a container for your partitions, and each partition can grow up to **10 GB** in size. 
- Indexes are created and maintained automatically. There's virtually no administrative overhead.
- Internally, Cosmos DB has been used by many of Microsoft's products for mission critical applications at global scale, including Skype, Xbox, Microsoft 365, Azure, and many others.
- Externally, Cosmos DB is highly suitable for the following scenarios:
  - IoT and telematics
  - Retail and marketing
  - Gaming
  - Web and mobile application










