Dependability in Edge Computing
###############################

:date: 2020-2-17
:category: Paper Review
:author: Joseph Anthony C. Hermocilla


This article [BAGCHI2019_] addresses three challenges related to the dependability of edge computing namely:

1. How should failures be handled?
2. How should security and privacy issues be addressed?
3. How should multi-tenancy be addressed in resource-constrained edge devices?

Edge computing attempts to improve the performance of software applications by placing computing resources closer to user devices and information sources. This has the effect of increasing the bandwidth and reducing latency. The word "edge" refers to the location of the computing resources in the network topology. In the case of the Internet, it is about two hops (routers) away from the user's device. 

For example, a smart toaster (the IoT device) with limited computing capabilities that needs to perform machine learning can use the edge server located in the datacenter of the ISP (a home router can also act as edge server). The traditional approach would be to offload the computation to Google servers over the cloud. 

The key idea is that if the user's device (local) cannot perform the required operation, it can offload the computation to a device near it (edge) instead of a server-class device (cloud) located across the globe.

*How should failures be handled?*

Since edge computing is in its infancy, most design decisions are made on a small scale. However, the number of user devices connecting to the network continues to increase. In addition, IoT devices continue to generate large volumes of data.  This results in the clogging of the network with some requests being dropped.  Time-critical applications will fail since computations will be forwarded to the cloud. 

One way to solve this lack of failover options is to agree on peer-based failover, similar to what is being done in microgrids. To solve real-time requirements, edge devices can forward delay-tolerant computations to the cloud to lessen the workload on the edge devices. The scheduler can then prioritize time-critical applications. 

*How should security and privacy issues be addressed?*

Edge devices will most probably be cheap (compared to server-grade machines used in the cloud) and will be heterogeneous. This will require mechanisms that can guarantee privacy and security in edge devices with limited computing resources and with different configurations. 

In particular, edge devices are easy to access physically since they are near the vicinity of user devices. This makes them susceptible to physical tampering. Traditional security mechanisms like code signatures and PKI can still be used but with some performance degradation. Device management will require some form of key-based authentication to make sure that edge devices have not been modified after deployment. Finally, updates should be made regularly on edge devices to patch vulnerabilities. 

*How should multi-tenancy be addressed in resource-constrained edge devices?*

Edge devices should be able to support multiple tenants or applications in the same manner as the cloud. Issues such as billing and scheduling will need to be addressed also. All these should be done in resource-constrained devices. 

Two example applications in the context of the issues described above, a smart toaster and a smart door lock, were presented in the paper. These two applications have different requirements in terms of bandwidth and latency. 

My takeaway from this paper is that edge computing is very similar to cloud computing. One difference is that edge devices are resource-constrained compared to cloud servers. This makes it difficult to make these systems dependable. Management is also a challenge  as edge devices are heterogeneous and owned by different entities.

.. [BAGCHI2019] Saurabh Bagchi, Muhammad-Bilal Siddiqui, Paul Wood, and Heng Zhang. 2019. Dependability in edge computing. Commun. ACM 63, 1 (December 2019), 58–66. `DOI:https://doi.org/10.1145/3362068 <https://doi.org/10.1145/3362068>`_
  
 
