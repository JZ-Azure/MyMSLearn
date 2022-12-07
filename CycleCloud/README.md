- [MSLearn Cyclecloud](https://learn.microsoft.com/en-us/azure/cyclecloud/overview?view=cyclecloud-8), [Tutorial on CycleCloud](https://learn.microsoft.com/en-us/training/modules/customize-clusters-azure-cyclecloud/)
- **Multi-Region**: 
[Deploy Multi-Region HPC clusters in Azure with CycleCloud](https://techcommunity.microsoft.com/t5/azure-high-performance-computing/deploy-multi-region-hpc-clusters-in-azure-with-cyclecloud/ba-p/3061269)
- **LDAP**: 
[Integrating LDAP into CycleCloud Cluster for User authentication](https://techcommunity.microsoft.com/t5/azure-high-performance-computing/integrating-ldap-into-cyclecloud-cluster-for-user-authentication/ba-p/3588364)
- **VM Images**: 
  - [Azure HPC VM Images](https://techcommunity.microsoft.com/t5/azure-compute-blog/azure-hpc-vm-images/ba-p/977094)
  - [azhpc-images repo at GitHub](https://github.com/Azure/azhpc-images)
- **Video Tutorial**: [Deploy end-to-end HPC environment with CycleCloud | Azure HPC](https://www.youtube.com/watch?v=_Hugv386nsg&t=5s)

TODO:

[High-performance computing on InfiniBand enabled H-series and N-series VMs](https://learn.microsoft.com/en-us/azure/virtual-machines/workloads/hpc/overview)

[Best Practices for using HB and HC VMs](https://learn.microsoft.com/en-us/azure/cyclecloud/how-to/hb-hc-best-practices?view=cyclecloud-8)

# What is Azure CycleCloud?
At its most basic, a High Performance Computing (HPC) system is a pool of computational resources backed by performant file systems and interconnected by low-latency networks. These computational resources are usually managed by HPC Schedulers, software applications that schedule jobs.

Building individual HPC systems on Azure from basic infrastructure units such as Virtual Machines, Disks, and Network Interfaces can be cumbersome, especially if these resources are ephemeral — existing only for the time required to solve the HPC task at hand. Additionally, operators want to create multiple, separate HPC environments that can be tailored to various business units, research teams, or individuals. Managing these multiple HPC systems can be operationally complexity.

Azure CycleCloud is an enterprise-friendly tool for orchestrating and managing High Performance Computing (HPC) environments on Azure. With CycleCloud, users can provision infrastructure for HPC systems, deploy familiar HPC schedulers, and automatically scale the infrastructure to run jobs efficiently at any scale. Through CycleCloud, users can create different types of file systems and mount them to the compute cluster nodes to support HPC workloads.
- CycleCloud is an installable web application that you can run on premise or in an Azure VM.
- CycleCloud provides a number of official cluster templates for schedulers (**PBSPro, LSF, Grid Engine, Slurm, HTCondor**), and filesystems (**NFS, BeeGFS**).
- CycleCloud **does NOT dictate cluster topology**; the installation comes with templates that are designed to get HPC systems up and running in Azure quickly, but HPC operators can customize these templates to tailor the infrastructure to meet their requirements.
