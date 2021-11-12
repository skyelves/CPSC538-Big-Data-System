### Problem Statement (1-2 Sentences) 

How to build a a serverless computing platform to provide researchers and developers with an open source implementation of a Lambda architecture?



### Why are existing solutions insufficient? 

Most existing solutions,except OpenWhisk, are closed and proprietary. No open-source Lambda architectures for researchers to evaluate new approaches to serverless computing.



### Solution Summary (1-2 Sentences)

This paper puts forward the advantages of Lambda over other virtualizations and gives a detailed elaboration of the Lambda background. And it finally presents OpenLambda, which consists of three modules: load balancers, handler store, and workers.



### 3 Strengths

S1. The introduction of the Lambda is quite detailed and sufficient. 

S2. The advantages of Lambda over other virtualizations, such as VMs and containers, are sound and solid.

S3. This paper also points out several directions to build a Lambda architecture system and highlights some important problems.

 

### 3 Weaknesses

O1. The security issues are not discussed in this paper.

O2. For long term applications, whose start up time is negligible to the running time, does Lambda architectures also have such huge advantages over other virtualizations? This should be a very important part to give an thorough overview of the Lambda.



### Validity of evaluation (strengths/weaknesses)

The advantages of Lambda are well showed in the experiments. However, for the long applications, the evaluations are missing. Since it's not a conference full paper, it's not necessary to have a complete evaluation part.



### One Idea for Future Work

In the Lambda architectures, to pursue the ultimate performance, there is no virtualizaion of containers or VMs at the cost of security issues. How to achieve memory isolation or something in Lambda architectures?

