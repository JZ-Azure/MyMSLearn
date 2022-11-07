# Fundamentals of large-scale data warehousing 
## Learning objectives
- Identify common elements of a large-scale data warehousing solution
- Describe key features for data ingestion pipelines
- Identify common types of analytical data store and related Azure services
- Provision Azure Synapse Analytics and use it to ingest, process, and query data

## Data ingestion pipelines
- On Azure, large-scale data ingestion is best implemented by creating pipelines that orchestrate ETL processes. 
- You can create and run pipelines using **Azure Data Factory**
- You can use the same pipeline engine in **Azure Synapse Analytics** if you want to manage all of the components of your data warehousing solution in a unified workspace.

## Analytical data stores
Two common types of analytical data store:
- Data warehouse
  - A data warehouse is a _relational database_ in which the data is stored in a schema that is optimized for _data analytics_ rather than _transactional workloads_.
  - A data warehouse is a great choice when you have transactional data that can be organized into a structured schema of tables, and you want to use SQL to query them.
- Data lakes
  - A data lake is a file store, usually on a distributed file system for high performance data access. 
  - Technologies like Spark or Hadoop are often used to process queries on the stored files and return data for reporting and analytics.
  - Data lakes are great for supporting a mix of structured, semi-structured, and even unstructured data that you want to analyze without the need for schema enforcement when the data is written to the store.

### Azure services for analytical stores
- **Azure Synapse Analytics** is a unified, end-to-end solution for large scale data analytics.
- **Azure Databricks** is an Azure implementation of the popular Databricks platform.
- **Azure HDInsight** is an Azure service that supports multiple open-source data analytics cluster types.

# Fundamentals of real-time analytics
## Learning objectives
- Compare batch and stream processing
- Describe common elements of streaming data solutions
- Describe features and capabilities of Azure Stream Analytics
- Describe features and capabilities of Spark Structured Streaming on Azure
- Describe features and capabilities of Azure Synapse Data Explorer

### Real-time analytics in Azure
- Azure Stream Analytics (PaaS)
- Spark Structured Streaming
- Azure Data Explorer

### _Sources_ for stream processing
- **Azure Event Hubs**: A data ingestion service that you can use to manage queues of event data, ensuring that each event is processed in order, exactly once.
- **Azure IoT Hub**: A data ingestion service that is similar to Azure Event Hubs, but which is optimized for managing event data from Internet-of-things (IoT) devices.
- **Azure Data Lake Store Gen 2**: A highly scalable storage service that is often used in batch processing scenarios, but which can also be used as a source of streaming data.
- **Apache Kafka**: An open-source data ingestion solution that is commonly used together with Apache Spark. You can use Azure HDInsight to create a Kafka cluster.

### _Sinks_ for stream processing
- **Azure Event Hubs**: Used to queue the processed data for further downstream processing.
- **Azure Data Lake Store Gen 2** or **Azure blob storage**: Used to persist the processed results as a file.
- **Azure SQL Database** or **Azure Synapse Analytics**, or **Azure Databricks**: Used to persist the processed results in a database table for querying and analysis.
- **Microsoft Power BI**: Used to generate real time data visualizations in reports and dashboards.

### Apache Spark on Microsoft Azure
You can use Spark on Microsoft Azure in the following services:
- Azure Synapse Analytics
- Azure Databricks
- Azure HDInsight

Spark can be used to run code (usually written in Python, Scala, or Java) in parallel across multiple cluster nodes, enabling it to process very large volumes of data efficiently. Spark can be used for both batch processing and stream processing.


### Azure Data Explorer
Azure Data Explorer is a standalone Azure service for efficiently analyzing data.  The service is also encapsulated as a runtime in Azure Synapse Analytics, where it is referred to as Azure Synapse Data Explorer; enabling you to build and manage analytical solutions that combine SQL, Spark, and Data Explorer analytics in a single workspace.

### Kusto Query Language (KQL)
To query Data Explorer tables, you can use Kusto Query Language (KQL), a language that is specifically optimized for fast read performance – particularly with telemetry data that includes a timestamp attribute.

To learn more about Kusto Query Language, see the Write your first query with [Kusto Query Language](https://learn.microsoft.com/en-us/training/modules/write-first-query-kusto-query-language/) module


# Fundamentals of data visualization
## Learning objectives
- Describe a high-level process for creating reporting solutions with Microsoft Power BI
- Describe core principles of analytical data modeling
- Identify common types of data visualization and their uses
- Create an interactive report with Power BI Desktop


