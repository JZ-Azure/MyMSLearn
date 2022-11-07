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
