## Identify data formats
- Structured
  - adheres to a fixed _schema_
  - Most commonly, _tabular_ - in other words, _tables_
- Semi-structured
  - has some structure, but allows for variations between entities
  - for example, JavaScript Object Notation (JSON)
- Unstructured
  - documents, images, audio and video data, and binary files

## Data stores
- File stores
- Databases

### Explore file storage

Storage options
- local file systems on the hard disk
- removable media such as USB drives
- shared file storage system, such as the cloud

File Formats
- Delimited text files
  - CSV, TSV
- JavaScript Object Notation (JSON)
- Extensible Markup Language (XML)
  - XML is a human-readable data format that was popular in the 1990s and 2000s.
- Binary Large Object (BLOB)
  - **_raw binary_** that must be interpreted by applications and rendered
  - images, video, audio, and application-specific documents
- Optimized file formats
  - file formats that enable compression, indexing, and efficient storage and processing
  - _Avro_ is a row-based format. It was created by Apache.
    - Each record contains a _header_ that describes the structure of the data in the record. This header is stored as JSON. The data is stored as _binary information_. An application uses the information in the header to parse the binary data and extract the fields it contains. _Avro is a good format for compressing data and minimizing storage and network bandwidth requirements._
  - _ORC_ (Optimized Row Columnar format) organizes data into columns rather than rows.
    - It was developed by HortonWorks for optimizing read and write operations in Apache Hive (Hive is a data warehouse system that supports fast data summarization and querying over large datasets). An ORC file contains stripes of data. Each stripe holds the data for a column or set of columns. A stripe contains an index into the rows in the stripe, the data for each row, and a footer that holds statistical information (count, sum, max, min, and so on) for each column.
  - _Parquet_ is another columnar data format. It was created by Cloudera and Twitter.
    - A Parquet file contains row groups. Data for each column is stored together in the same row group. Each row group contains one or more chunks of data. A Parquet file includes metadata that describes the set of rows found in each chunk. An application can use this metadata to quickly locate the correct chunk for a given set of rows, and retrieve the data in the specified columns for these rows. Parquet specializes in storing and processing nested data types efficiently. It supports very efficient compression and encoding schemes.

### Explore databases
Relational databases
- Relational databases are commonly used to store and query structured data.
- The tables are managed and queried using Structured Query Language (SQL)

Non-relational databases
- data management systems that don’t apply a relational schema to the data. 
- NoSQL database
  - Key-value databases
    - each record consists of a unique key and an associated value, which can be in any format.
  - Document databases
    - specific form of key-value database in which the value is a JSON document (which the system is optimized to parse and query)
  - Column family databases
    - store tabular data comprising rows and columns, but you can divide the columns into groups known as column-families. Each column family holds a set of columns that are logically related together.
  - Graph databases
    - store entities as nodes with links to define relationships between them.

## Transactional data processing
The work performed by transactional systems is often referred to as **_Online Transactional Processing_** (OLTP). OLTP solutions rely on a database system in which data storage is optimized for both read and write operations in order to support transactional workloads in which data records are created, retrieved, updated, and deleted (often referred to as CRUD operations). 

ACID semantics:
- Atomicity
  - each transaction is treated as a single unit, which succeeds completely or fails completely. For example, a transaction that involved debiting funds from one account and crediting the same amount to another account must complete both actions. If either action can't be completed, then the other action must fail.
- Consistency
  - transactions can only take the data in the database from one valid state to another. To continue the debit and credit example above, the completed state of the transaction must reflect the transfer of funds from one account to the other.
- Isolation
  - concurrent transactions cannot interfere with one another, and must result in a consistent database state. For example, while the transaction to transfer funds from one account to another is in-process, another transaction that checks the balance of these accounts must return consistent results - the balance-checking transaction can't retrieve a value for one account that reflects the balance before the transfer, and a value for the other account that reflects the balance after the transfer.
- Durability
  - when a transaction has been committed, it will remain committed. After the account transfer transaction has completed, the revised account balances are persisted so that even if the database system were to be switched off, the committed transaction would be reflected when it is switched on again.

## analytical data processing
- **Data lakes** are common in large-scale data analytical processing scenarios, where a large volume of _file-based data_ must be collected and analyzed. (Files)
- **Data warehouses** are an established way to store data in a _relational schema_ that is optimized for read operations – primarily queries to support reporting and data visualization. (DBs)
  - A data warehouse is a relational database in which the schema is optimized for queries that read data.
- An online analytical processing (OLAP) model is an aggregated type of data storage that is optimized for _analytical workloads_.


## Job roles in the world of data
- **Database administrators** manage databases, assigning permissions to users, storing backup copies of data and restore data in the event of a failure.
  - A database administrator is responsible for the design, implementation, maintenance, and operational aspects of on-premises and cloud-based database systems.
  - The database administrator is also responsible for managing the security of the data in the database, granting privileges over the data, granting or denying access to users as appropriate.
  - For example, back up the database and restore it when data is lost or corrupted.
- **Data engineers** manage infrastructure and processes for data integration across the organization, applying data cleaning routines, identifying data governance rules, and implementing pipelines to transfer and transform data between systems.
  - A data engineer collaborates with stakeholders to design and implement data-related workloads, including data ingestion pipelines, cleansing and transformation activities, and data stores for analytical workloads.
  - They own the management and monitoring of data pipelines to ensure that data loads perform as expected.
  - For example, define a data pipeline for an ETL process.
- **Data analysts** explore and analyze data to create visualizations and charts that enable organizations to make informed decisions.
  - They're responsible for exploring data to identify trends and relationships, designing and building analytical models, and enabling advanced analytics capabilities through reports and visualizations.
  - A data analyst processes raw data into relevant insights based on identified business requirements to deliver relevant insights.
  - For example, creating dashboards and reports.

## Data services

### Azure SQL
Azure SQL is the collective name for a family of _relational_ database solutions based on the Microsoft SQL Server database engine.
- (PaaS) **Azure SQL Database** – a fully managed platform-as-a-service (PaaS) database hosted in Azure
- (PaaS?) **Azure SQL Managed Instance** – a hosted instance of SQL Server with automated maintenance, which allows more flexible configuration than Azure SQL DB but with more administrative responsibility for the owner.
- (IaaS) **Azure SQL VM** – a virtual machine with an installation of SQL Server, allowing maximum configurability with full management responsibility.

### Azure Database
Azure includes managed services for popular open-source relational database systems, including:
- A**zure Database for MySQL** - a simple-to-use open-source database management system that is commonly used in Linux, Apache, MySQL, and PHP (LAMP) stack apps.
- **Azure Database for MariaDB** - a newer database management system, created by the original developers of MySQL. The database engine has since been rewritten and optimized to improve performance. MariaDB offers compatibility with Oracle Database (another popular commercial database management system).
- **Azure Database for PostgreSQL** - a hybrid relational-object database. You can store data in relational tables, but a PostgreSQL database also enables you to store custom data types, with their own non-relational properties.

### Azure Cosmos DB
Azure Cosmos DB is a global-scale non-relational (**_NoSQL_**) database system that supports multiple application programming interfaces (APIs), enabling you to store and manage data as _JSON_ documents, _key-value_ pairs, _column-families_, and _graphs_.

### Azure Storage
Azure Storage is a core Azure service that enables you to store data in:
- **Blob containers** - scalable, cost-effective storage for binary files.
- **File shares** - network file shares such as you typically find in corporate networks.
- **Tables** - key-value storage for applications that need to read and write data values quickly.

Data engineers use Azure Storage to host _data lakes_ - blob storage with a hierarchical namespace that enables files to be organized in folders in a distributed file system.

### Azure Data Factory
Azure Data Factory is an Azure service that enables you to define and schedule _data pipelines to transfer and transform data_.

### Azure Synapse Analytics
Azure Synapse Analytics is a comprehensive, unified data analytics solution that provides a single service interface for multiple analytical capabilities, including:
- **Pipelines** - based on the same technology as Azure Data Factory.
- **SQL** - a highly scalable SQL database engine, optimized for data warehouse workloads.
- **Apache Spark** - an open-source distributed data processing system that supports multiple programming languages and APIs, including Java, Scala, Python, and SQL.
- **Azure Synapse Data Explorer** - a high-performance data analytics solution that is optimized for real-time querying of log and telemetry data using Kusto Query Language (KQL).

### Azure Databricks
Azure Databricks is an Azure-integrated version of the popular Databricks platform, which combines the _Apache Spark_ data processing platform with _SQL database_ semantics and an _integrated management interface_ to enable large-scale data analytics.

### Azure HDInsight
Azure HDInsight is an Azure service that provides Azure-hosted clusters for popular Apache open-source big data processing technologies. 

### Azure Stream Analytics
Azure Stream Analytics is a real-time stream processing engine that captures a stream of data from an input, applies a query to extract and manipulate data from the input stream, and writes the results to an output for analysis or further processing.

### Azure Data Explorer
Azure Data Explorer is a standalone service that offers the same high-performance querying of log and telemetry data as the _Azure Synapse Data Explorer runtime_ in Azure Synapse Analytics.

### Microsoft Purview
Microsoft Purview provides a solution for enterprise-wide data governance and discoverability. 

### Microsoft Power BI
Microsoft Power BI is a platform for analytical data modeling and reporting that data analysts can use to create and share interactive data visualizations.
