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
