# Learning objectives
- Learn the key factors that are driving changes in data generation, roles, and technologies.
- Compare the differences between on-premises data technologies and cloud data technologies.
- Outline how the role of the data professional is changing in organizations.
- Identify use cases that involve these changes.

## Data abundance
- Data can be structured, unstructured, or aggregated. 
- For structured databases, data architects define the structure (schema) as they create the data storage in platform technologies such as _**Azure SQL Database**_ and **_Azure Synapse Analytics_**. 
- For unstructured (NoSQL) databases, each data element can have its own schema at query time. Data can be stored as a file in _**Azure Blob storage**_ or as NoSQL data in **_Azure Cosmos DB_** or **_Azure HDInsight_**.


## [Understand the difference between on-premises and cloud-based servers](https://learn.microsoft.com/en-us/training/modules/evolving-world-of-data/3-systems-on-premise-vs-cloud)

## Change data processes
- Extract, transform, and load (ETL)
  - A disadvantage of the ETL approach is that the transformation stage can take a long time. This stage can potentially tie up source system resources. 
  - This process is typically used for ingesting data from an on-premises database to an on-premises data warehouse.
- Extract, load, and transform (ELT)
  - In ELT, the data is immediately extracted and loaded into a large data repository, such as **Azure Cosmos DB** or **Azure Data Lake Storage**. This change in process reduces the resource contention on source systems.
  - This process is typically used for ingesting data from an on-premises database into the cloud.


# Learning objectives
- Contrast structured data with nonstructured data.
- Explore common Microsoft Intelligent Data Platform technologies and identify when to use them.
- List additional technologies that support the common data platform technologies.

## Explore data types
- Structured data
  - Data structure is defined at design time. This means it's designed before any information is loaded into the system.
- Nonstructured data
  - In nonrelational systems, the data structure isn't defined at design time, and data is typically loaded in its raw format. The data structure is defined only when the data is read.
  - Nonrelational systems can also support semistructured data such as JSON file formats.

Four types of **NoSQL databases**:  
1. Key-value store: Stores key-value pairs of data in a table structure.
1. Document database: Stores documents that are tagged with metadata to aid document searches.
1. Graph database: Finds relationships between data points by using a structure that's composed of vertices and edges.
1. Column database: Stores data based on columns rather than rows. Columns can be defined at the query's runtime, allowing flexibility in the data that's returned performantly.

## Understand data storage in Azure Storage
Azure Storage offers four configuration options:
1. **Azure Blob**: A scalable object store for text and binary data
  - If you need to provision a data store that will store but not query data, your cheapest option is to set up a storage account as a Blob store. 
  - Blob storage works well with images and unstructured data, and it's the cheapest way to store data in Azure.  
1. **Azure Files**: Managed file shares for cloud or on-premises deployments
1. Azure Queue: A messaging store for reliable messaging between application components
1. Azure Table: A NoSQL store for no-schema storage of structured data

