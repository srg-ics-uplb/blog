Cloud Benchmarking for Maximising Performance of Scientific Applications
########################################################################

:date: 2019-4-29
:category: Paper Review
:author: Joseph Anthony C. Hermocilla


It is quite difficult for users to select VM configurations to optimize the 
performance of their applications, especially if there are a lot of choices. 
For example, if I want to run computational chemistry app, I need to make a decision 
whether to use a VM with 1 VCPU and 2GB RAM or a VM with 2 VCPUs and 4GB RAM. 

Cloud providers run benchmarks to measure the performance of various VM configurations for applications. 
However, these benchmarks are done independent of the application to be deployed. Most likely because 
providers have no knowledge of what application will be deployed.

This paper [VARGHESE2019_] addresses these issues by introducing an application-aware benchmarking 
methodology. The main hypothesis presented in the paper is that by taking into account application 
requirements in addition to benchmarking data, VMs can be ranked in order of performance and 
cost-effectiveness to maximize performance. Although there are different kinds of applications 
that can be run in the cloud, the paper focused on high-performance computing applications with 
the goal of minimizing execution time to minimize costs. (Running applications in the cloud is  
usually charged per hour.) The authors validated they results against real-world applications.
The following are the steps in the proposed methodology.

1. Capture attributes of cloud VMs
2. Group attributes of cloud VMs
3. Benckmark cloud VMs
4. Normalize attribute groups
5. Provide weights to groups
6. Rank cloud VMs

Steps 5-6 are repeated for each deployment.

In Step 2, the following are the identified attribute groups:
- memory and process
- local communication
- computation
- storage

As for the benchmarking part, the researchers used bonnie++, lmbench, and sysbench.

It is worth noting that this paper did not consider inter-VM communication. The 
local communication is between the cores in the VM only. Perhaps a future work will 
be to consider inter-VM communication in the methodology.

.. [VARGHESE2019] Varghese, B., Akgun, O., Miguel, I., Thai, L., & Barker, A. (2019). Cloud Benchmarking for Maximising Performance of Scientific Applications. IEEE Transactions on Cloud Computing, 7(1), 170–182.
