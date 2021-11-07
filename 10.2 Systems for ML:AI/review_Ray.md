### Problem Statement (1-2 Sentences) 

How to build a distributed hetergenerous system for both batched computations, especially RL, and fine-grained computations?



### Why are existing solutions insufficient? 

Existing solutions fall short of satisfying requirements for RL, which either do not support fine-grained simulation or provide little support for distributed training and serving, or do not naturally support simulation and serving.



### Solution Summary (1-2 Sentences)

Ray is a general-purpose cluster-computing framework which enables simulation, training, and serving for RL applications. Ray implement an interface that can express both task-parallel and actor-based computations and enable efficient fault tolerance. 



### 3 Strengths

S1. Ray enables efficient fault tolerance with almost no cost in latency.

S2. Ray is friendly to python programmers. Since most RL algorithms are implemented in python, it makes Ray easy to use.

S3. This paper gives an detailed and thorough evaluation of Ray. Ray matches and sometimes exceeds the performance of dedicated systems for some applications.

 

### 3 Weaknesses

O1. It is absolute that we need an system to support RL, fine-grained computations and serving. But it doesn't elaborate sufficiently why they choose to implement a different system like Ray instead of modifying the current computation framework to support these functions.

O2. Ray also uses the lineage to ensure fault tolerance. This brings me the question, can we implement Ray on Spark? 



### Validity of evaluation (strengths/weaknesses)

The experiments not only show the end-to-end performance of Ray, but also break down Ray to show its individual performance for certain applications. The results also show that Ray can achieve fast recovery with little overhead.



### One Idea for Future Work

Can we build a system like Ray on Spark? Since Spark already integrates many applications such as stream processing and graph processing, people are more likely to use Spark-Ray instead of using a standalone system.

