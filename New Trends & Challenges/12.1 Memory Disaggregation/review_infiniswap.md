### Problem Statement (1-2 Sentences) 

How to increase the memory utilization in the presence of inbalanced memory utilization across a cluster?



### Why are existing solutions insufficient? 

Existing solutions either require new architecture or new hardware or application changing, which makes them impractical to be deployed.



### Solution Summary (1-2 Sentences)

This paper presents a remote memory paging system, named INFINISWAP, using RDMA. INFINISWAP transparently exposes unused remote memory to the local OS and using one-sided RDMA operations to bypass remote CPUs.



### 3 Strengths

S1. INFINISWAP requires no modification to the application and doesn't require new hardware.

S2. INFINISWAP only uses one-sided RDMA so that it can bypass the remote CPU when accessing remote memory.

S3. There are some mathetical proof to show the efficiency of its policies.

 

### 3 Weaknesses

O1. INFINISWAP doesn't provide application performance isolation.

O2. When performing eviction, the servers have to communicate with each other. In some cases, the workload in each server changes dramatically, there may be frequent evictions, thus consuming high bandwidth.

O3. A minor weakness. INFINISWAP assumes the network is the bottleneck and is built on INFINIBAND. However, in the real world, most network are based on Ethernet. Therefore, INFINISWAP is still impractical to deploy into industry.





### Validity of evaluation (strengths/weaknesses)

There is a complete set of experiments to show INFINISWAP has a stable and significant improvement in all workloads. The overall cluster memory utilization has about 20% increase, which is rather notable since the original utilization is only about 40%. Also the latency with INFINISWAP is only slightly increased, compared with in-memory MemCached.



### One Idea for Future Work

Can we achieve memory disaggregation on Ethernet with little overhead?

