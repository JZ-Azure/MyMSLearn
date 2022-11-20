# What is Azure HPC Cache?
HPC Cache is a managed service that accelerates file-based storage for compute-intensive workloads.

How to know if your workload is cacheable?
- Cacheable workloads have a static set of data that several clients access at the same time.
- Ideal workloads are read-heavy workloads, which means 90 percent or more NFS read operations. Similarly, 10 percent or less of the storage operations are NFS write operations.
- Workloads should also involve dozens or hundreds of clients. The more clients you have reading from the same dataset, the greater the benefit of caching.
- Clients should be as close to the cache as possible. For example, HPC Cache is in Azure, so using HPC clients in Azure minimizes latency between the cache and the clients.
- Datasets should include megabyte- or ideally gigagbyte-sized files. The working set should be at least 1 terabyte (TB) in size.

HPC Cache wouldn't be the best fit if:
- The dataset is constantly changing.
- Only a few clients are accessing data on a non-NAS server.
- A large set of the storage calls is made up of write requests.
- The file system isn't NFS.

|Criteria|Analysis|
|---|---|
|Storage|Data should be stored on NAS like NetApp, EMC Isilon, or Linux storage servers.|
|Protocol|Storage should use NFSv3 as its file system protocol.|
|Read/Write|Workloads need to be read-heavy. At least 90 percent of NFS operations need to be read.|
|Clients|Hundreds or thousands of compute clients should be in Azure requesting the same data.|
|Data|The size of the workload should be at least 1 TB.|

## Examples
Should financial institutions use HPC Cache to run simulations?
Financial simulations are a great fit for HPC Cache. The dataset of historic stock market data is unchanging. Hundreds of clients use the same data to run several simulations. The file sizes are gigabytes in size and the total working set is over 1 TB.

Should users use HPC Cache for home directories?
Using home directories isn't a good fit for HPC Cache. The dataset is only a few gigabytes in size. Only a single client accesses the data. The data is often changing. Data is stored in an SMB file system.

Should Engineering Design Automation use HPC Cache to accelerate a tools repository?
Accelerating Engineering Design Automation (EDA) tools repositories is a good fit for HPC Cache. Several clients use the tools repo while designing and architecting. The repo is large and is accessed via NFS.

Suppose a genetic research company is considering Azure HPC Cache for a workload that compares gigabyte DNA files to the same reference DNA file. The company uses hundreds of cloud clients running an NFS workload. What would make this good fit even better?
If the company installed Azure ExpressRoute to maximize bandwidth