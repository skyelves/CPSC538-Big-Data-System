### Problem Statement (1-2 Sentences) 

What are the minimum network requirements for the disaggregated datacenters? Is it possible to implement disaggragation with existing system designs and commodity networking technology?



### Why are existing solutions insufficient? 

No existing work evaluates the minimum network requirements that the network in disaggregated datacenters must provide.



### Solution Summary (1-2 Sentences)

By evaluating the performance degradation of the simulated disaggregated network, the authors show that the current network bandwidth is sufficient while the network latency is main bottleneck and point out that current transport protocols are the main root of the high latency.



### 3 Strengths

S1. This paper first evaluates the necessarity of the next-generation network and points out current network are sufficient for some applications even in datacenters.

S2. This paper conducts thorough experiments to show the impact of the different network bandwidth and latency to the application, thus pointing out the major goal of the network developing.



 

### 3 Weaknesses

O1. The conclusion of the paper, i.e., the bandwidth is sufficient while latency is the bottleneck, and the network protocol accounts for the high latency, is obvious.

O2. In this paper, the authors inject artificial delays to emulate network round-trip latency and bandwidth, however, this limits the bandwidth upper bound of the network to the memory bandwidth. However, in reality, the network bandwidth are gorwing faster than memory bandwidth. With the higher bandwidth, the application performance degradation can be lower.

O3. All experiments are based on simulation and the application are not comprehensive enough to cover all the cases.





### Validity of evaluation (strengths/weaknesses)

This paper evaluates the necessary network requirements for the disaggregated system. The evaluation is thorough and gives many detailed analyses.



### One Idea for Future Work

We can offload some network functions, such as serializing and deserializing, to the FPGA to reduce the latency.

