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

# Understand data storage in Azure Storage
Azure Storage offers four configuration options:
1. **Azure Blob**: A scalable object store for text and binary data. If you need to provision a data store that will store but not query data, your cheapest option is to set up a storage account as a Blob store. Blob storage works well with images and unstructured data, and it's the cheapest way to store data in Azure.  
1. **Azure Files**: Managed file shares for cloud or on-premises deployments
1. Azure Queue: A messaging store for reliable messaging between application components
1. Azure Table: A NoSQL store for no-schema storage of structured data

# Understand data storage in Azure Data Lake Storage
Azure Data Lake Storage is a Hadoop-compatible data repository that **can store any size or type of data**. Data Lake Storage Gen2 users take advantage of Azure Blob storage, a hierarchical file system, and performance tuning that helps them process big-data analytics solutions. In Gen2, developers can access data through either the Blob API or the Data Lake file API. **Gen2 can also act as a storage layer** for a wide range of compute platforms, including **Azure Databricks**, **Hadoop**, and **Azure HDInsight**, but data doesn't need to be loaded into the platforms.

### Where to use Data Lake Storage Gen2
Data Lake Storage is designed to **store massive amounts of data for big-data analytics**. For example, Contoso Life Sciences is a cancer research center that analyzes petabytes of genetic data, patient data, and records of related sample data. Data Lake Storage Gen2 reduces computation times, making the research faster and less expensive.

The _**compute aspect**_ that sits above this storage can vary. The aspect can include platforms like 
1. **HDInsight**
1. **Hadoop**
1. **Azure Databricks**

### Data ingestion
To ingest data into your system, use **Azure Data Factory**, **Apache Sqoop**, **Azure Storage Explorer**, the **AzCopy tool**, **PowerShell**, or **Visual Studio**. To use the File Upload feature to import file sizes above 2 GB, use PowerShell or Visual Studio. AzCopy supports a maximum file size of 1 TB and automatically splits data files that exceed 200 GB.

### Queries
- In Gen 1, data engineers query data by using the** U-SQL language**. 
- In Gen 2, use the **Azure Blob Storage API** or the **Azure Data Lake System (ADLS) API**.

## Understand Azure Cosmos DB
Azure Cosmos DB is a **globally distributed**, **multimodel database**. You can deploy it by using several API models:
- SQL API
- MongoDB API (for semistructured data)
- Cassandra API (for wide columns)
- Gremlin API (for graph databases)
- Table API

### When to use Azure Cosmos DB
Deploy Azure Cosmos DB when you need a **NoSQL database** of the supported API model, at planet scale, and with low latency performance. Currently, Azure Cosmos DB supports **five-nines uptime** (99.999 percent). It can support **response times below 10 ms** when it's provisioned correctly.

### Data ingestion
To ingest data into Azure Cosmos DB, use Azure Data Factory, create an application that writes data into Azure Cosmos DB through its API, upload JSON documents, or directly edit the document.

### Data security
Azure Cosmos DB supports data encryption, IP firewall configurations, and access from virtual networks. Data is encrypted automatically. User authentication is based on tokens, and Azure Active Directory provides role-based security.

Azure Cosmos DB meets many security compliance certifications, including **HIPAA**, FedRAMP, SOX, and HITRUST.

# Understand Azure SQL Database
Azure SQL Database is a managed relational database service. It supports structures such as **relational data** and **unstructured** formats such as **spatial and XML data**. SQL Database provides online transaction processing (OLTP) that can scale on demand. You'll also find the comprehensive security and availability that you appreciate in Azure database services.

### When to use SQL Database
Use SQL Database when you need to scale up and scale down OLTP systems on demand. SQL Database is a good solution when your organization wants to take advantage of Azure security and availability features. Organizations that choose SQL Database also avoid the risks of capital expenditures and of increasing operational spending on complex on-premises systems.

SQL Database can be more flexible than an on-premises SQL Server solution because you can provision and configure it in minutes. Even more, SQL Database is backed up by the Azure service-level agreement (SLA).

### Ingesting and processing data
SQL Database can ingest data through application integration from a wide range of developer SDKs. Allowed programming languages include .NET, Python, Java, and Node.js. Beyond applications, you can also ingest data through Transact-SQL (T-SQL) techniques and from the movement of data using **Azure Data Factory**.

### Queries
Use **T-SQL** to query the contents of a SQL Database. This method benefits from a wide range of standard SQL features to filter, order, and project the data into the form you need.

# Understand Azure Synapse Analytics
Azure Synapse Analytics is a cloud-based data platform that brings together enterprise **data warehousing** and **Big Data analytics**. It can process massive amounts of data and answer complex business questions with limitless scale.

### When to use Azure Synapse Analytics
Data loads can increase the processing time for on-premises data warehousing descriptive analytic solutions. Organizations that face this issue might look to a cloud-based alternative to reduce processing time and release business intelligence reports faster. But many organizations first consider scaling up on-premises servers. As this approach reaches its physical limits, they look for a solution on a **petabyte scale that doesn't involve complex installations and configurations**. The SQL Pools capability of Azure Synapse Analytics can meet this need.

### Key features
SQL Pools uses **massively parallel processing (MPP)** to quickly run queries across petabytes of data. Because the storage is separated from the compute nodes, you can scale the compute nodes independently to meet any demand at any time.

In Azure Synapse Analytics, the **Data Movement Service (DMS)** coordinates and transports data between compute nodes as necessary. But you can use a replicated table to reduce data movement and improve performance. Azure Synapse Analytics supports three types of distributed tables: hash, round-robin and replicated. Use these tables to tune performance.

Importantly, Azure Synapse Analytics can also pause and resume the compute layer. This means you pay only for the computation you use. This capability is useful in data warehousing.

### Ingesting and processing data
Azure Synapse Analytics uses the extract, load, and transform (**ELT**) approach for bulk data. SQL professionals are already familiar with bulk-copy tools such as bcp and the SQLBulkCopy API. Data engineers who work with Azure Synapse Analytics will soon learn how quickly **PolyBase** can load data.

PolyBase is a technology that removes complexity for data engineers. They take advantage of techniques for big-data ingestion and processing by offloading complex calculations to the cloud. Developers use PolyBase to apply stored procedures, labels, views, and SQL to their applications. You can also use Azure Data Factory to ingest and process data using PolyBase too.

### Queries
As a data engineer, you can use the familiar Transact-SQL to query the contents of Azure Synapse Analytics. This method takes advantage of a wide range of features, including the WHERE, ORDER BY, and GROUP BY clauses. Load data fast by using PolyBase with additional Transact-SQL constructs such as CREATE TABLE and SELECT.

# Understand Azure Stream Analytics
Data engineers use Azure Stream Analytics to process streaming data and respond to data anomalies in real time. You can use Stream Analytics for Internet of Things (IoT) monitoring, web logs, remote patient monitoring, and point of sale (POS) systems.

# Understand Azure HDInsight
Azure HDInsight provides technologies to help you ingest, process, and analyze big data. It supports batch processing, data warehousing, IoT, and data science.
