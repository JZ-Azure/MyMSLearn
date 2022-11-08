[Self Study Guide](https://learn.microsoft.com/en-us/users/23110622/collections/0kjyh8rn5gdrjj)

# Q&A

Azure HDInsight is a cloud service that lets you implement, manage, and monitor a cluster for _Hadoop, Spark, HBase, Kafka, Storm, Hive LLAP_, and _ML Service_ in an easy and effective way. Its applications include batch and stream processing, data science, and interactive query over big data storage. Decoupling compute from storage allows for processing at scale.

Azure Databricks is a cloud service from the creators of Apache Spark, combined with a great integration with the Azure platform. It _supports only Spark clusters_, but since the Spark framework comes with modules and libraries for batch processing, stream processing, data science, and graph databases, it is rapidly growing in popularity.

Advanced analytics or the data science process may quickly become complex, since it involves a lot of resources and it is a time-consuming activity. The most common methodologies used to approach a data science lifecycle, the _Team Data Science Process_ (TDSP). TDSP is an agile approach to data science projects and usually involves several different roles.

Three main types of workload can be found in a typical modern data warehouse: Streaming data, Batch data, Relational data

Consumer groups allow consumers to maintain dedicated and isolated views over the data stream. The source stream is unique—each group can read data at its own pace and starting from its own offset. For example, you may have a real-time dashboard that reads data every 5 seconds and an hourly job that performs historical aggregations over ingress events; both are reading the same stream, but the former will read events minutes before the latter.

The most important difference between Online transaction processing (OLTP) and Online analytical processing (OLAP) is that OLAP is implemented for reading big amounts of data for data analysis, whereas OLTP is designed for many parallel write transactions.

vCore is short for virtual core and it’s a model that was designed to make it simpler to translate your on prem hardware resource specs into similar specs on the Azure SQL database platform.

Durability ensures that the information can be accessed later even after a system crash. Most relational database systems (RDBSs) use a mechanism to quickly store each step of an activity and then confirm all of them at the same time (known as a commit).

The name “atomicity” derives from the concept of an atom. It is something that must be together. It is “all or nothing.” Ensuring that all the information is stored as one block, as an atom including all the parts at the same time, is atomicity. It ensures that all the information is stored as one block, including all the parts at the same time.

Cosmos DB has an SLA of _99.999 percent_ and guarantees _10-millisecond writes_ completed in _any region_.

Azure Databricks billing is based on Databricks Units (DBUs), metrics used to track how many seconds the runtime works. In addition, you have to consider the infrastructure cost for the nodes of your clusters (which are normal Azure VMs), for the public IP address, and for the internal Blob storage account

Tools or programmatic approaches like bcp and SqlBulkCopy API can still be used to load the data into Azure Synapse Analytics. They are slower than PolyBase or the COPY command, though, and for this reason they are not the preferred way.

Azure Data Factory (ADF) is a cloud-based ETL and data integration service. You can use it to create data-driven workflows for orchestrating data movement and transforming data at scale

It is common that such architectures contain a mix of four workloads: relational, nonrelational, batch, and streaming. These architectures are often called modern data warehouses, to distinguish them from traditional data warehouses.

Relational databases are not well suited for high-throughput workloads or massive insert/update batches. Instead, they best handle small transactions targeting one or few records.

- Descriptive: What's happening
- Diagnositc: Why it happened
- Predictive: What will happen
- Prescriptive: What should I do

Cosmos DB Table API supports multi-region _writes_. Cosmos DB Table API and Azure Table storage support multi-region _reads_ replicas. 

Azure Table lets you store semi-structured data. Unlike in a relational table, each row can have different columns of data. 
