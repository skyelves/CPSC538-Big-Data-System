### Problem Statement (1-2 Sentences) 

With the much faster data growth, memory becomes the key resource. This brings the question how to design a memory centric operating system.



### Why are existing solutions insufficient? 

Current OSes are processor-centric. Therefore, the memory capacity and bandwidth will be the bottleneck with more and more data.



### Solution Summary (1-2 Sentences)

This paper presents a new memory-centric OS architecture. NVM forms a shared memory pool so that each processor can access the memory pool equidistantly. To implement such a enormous memory pool, this paper presents many important issues, such as memory resource management, protection, translation, error handling and so on.



### 3 Strengths

S1. This paper introduces the significance of the memory-centric system.

S2. This paper introduces many significant problems to implement a practical memory-centric OS. It also discuss the problems with large scale memory.

S3. Overall, this paper has a rather complete overview of the memory-centric OS.

 

### 3 Weaknesses

O1. There is little statistics to show the rapid data growth, which can be less convincing to people who are not familiar with the field.

O2. This paper only presents the problems we may face to develop a memory-centric OS. There is little guideline or solution to these problems.

O3. A minor problem: The shared everything architecture seems interesting but not well elaborated.



### Validity of evaluation (strengths/weaknesses)

No evaluation.



### One Idea for Future Work

With the new architecture, the OS API also should be redesigned and some other trivial operations may be non-trivial in the new architecture, such as pointer chasing. How to efficiently implement pointer chasing in this memory-centric operation becomes a problem since all pointers are in the memory pool and in the different physical devices.

