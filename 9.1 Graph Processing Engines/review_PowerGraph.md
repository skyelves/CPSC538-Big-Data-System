### Problem Statement (1-2 Sentences) 

The natural graphs have highly skewed power-law degree distributions and are hard to partition with edge cut. PowerGraph answers the question how to efficiently perform distributed graph-parallel computing on natural graphs.



### Why are existing solutions insufficient? 

Existing solutions, such as Preggel and GraphLab, encode computation as vertex programs and interact along edges. The efficiency relies on each vertex having a small neighborhood.



### Solution Summary (1-2 Sentences)

This paper first analyses the characteristics of the natural graphs, which have highly skewed power-law degree distributions. It's hard to partition natural graphs with the existing solutions (edge-cuts). Then the authors propose PowerGraph, which adopts the vertex-cuts, which greatly simplifies the communication. 



### 3 Strengths

S1. This paper draws abstracts of the graph computations, the Gather-Apply-Scatter model. 

S2. This paper first gives the analysises of the natural graphs.

S3. PowerGraph presents several graph placements to achieve vertex-cuts and validate their efficiency with sufficient details and experiments.



### 3 Weaknesses

O1. Vertex-cuts may not work well for some sub-graphs which doesn't follow power-low distributions.

O2. The number of replicas for a vertex can be large in some cases, causing inefficiency.

O3. If the numbers of replicas for a vertex are large, it also increases the communication costs to maintain consistency.



### Validity of evaluation (strengths/weaknesses)

The evaluation shows that PowerGraph outperforms the existing solutions by order of magnitude. It also shows the improvements of Greedy vertex-cuts.



### One Idea for Future Work

PowerGraph works only for static graphs. Can we extend it to the graph streams?