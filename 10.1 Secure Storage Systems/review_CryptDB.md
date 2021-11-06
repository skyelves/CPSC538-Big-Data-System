### Problem Statement (1-2 Sentences) 

How to perform SQL queries over encrypted data in Database?



### Why are existing solutions insufficient? 

Existing solutions either rely on running all computations on clients, where DB only works as a storage system, or using prohibitively expensive fully homomorphic encryption schemes, inducing order of magnitude overhead.



### Solution Summary (1-2 Sentences)

The key insight of CryptDB is that because SQL uses a well-defined set of operators, we don't need homomorphic encryption schemes but some weaker encryption schemes. CryptDB divides the encryptions into 6 kinds, RNG, DET, OPE, HOM, JOIN and OPE-JOIN, and SEARCH, according to the SQL queries. With the Onion encryption design, we can perform efficient SQL queries on the according kind of encrypted data.



### 3 Strengths

S1. CryptDB only reveals the necessary data depending on the temporary SQL queries and do not leak other information.

S2. CryptDB supports most frequently used SQL operations. Especially to support join operations, CryptDB introduces a new cryptographic primitive, JOIN-ADJ (adjustable join) to dynamically adjust keys for each column.

S3. The performance of CryptDB only degrades about 20% on almost all regular SQL operations.



### 3 Weaknesses

O1. If the encryption of column is not already at an onion layer when serving a request, it needs to first decrypt the column, which may incur very high tail latency.

O2. For the storage overhead, the workload in the phpBB application is too small. And the workload for TPC-C is not well illustrated.

O3. The tail latency is not measured in the evaluation part.



### Validity of evaluation (strengths/weaknesses)

The experiments show that CryptDB achieves considerable performance as plaintext SQL, with only 20% degradtion. It also shows that it only needs very limited programming efforts to adapt to CryptDB. However, there are very limited evaluation of storage overhead and tail latency.



### One Idea for Future Work

CryptDB only protects data confidentiality but don't ensure integrity. Checksum can be used to inform the users if the data has been modified or not.

Can we move more functionalities from proxy to clients to defend against second kind of threat?

