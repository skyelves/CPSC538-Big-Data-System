### Problem Statement (1-2 Sentences) 

Encrypted databases rely on expensive cryptographic techniques so that they suffer from poor performance and may leak data distribution to attackers. This paper focus on how to improve the performance and protect the data.



### Why are existing solutions insufficient? 

Existing solutions, such as CryptDB and Monomi, utilize asymmetric encryption schemes, so they have poor performance.



### Solution Summary (1-2 Sentences)

Given the case the data writer and reader are always the same, Seabed, instead of using an expensive asymmetric encryption schemes, utilizes additively symmetric homomorphic encryption schemes, which is much more efficient. Seabed also introduces SPLASHE to prevent frequency attacks, based on storing auxiliary data and removing the origin data. 



### 3 Strengths

S1. Seabed is based on one neat observation, the data writer and reader are always the same. In this case, the data encryption algorithms can be simplified.

S2. This paper also points out the weakness of the Seabed.

S3. This paper has a through and detailed experiments part. The results show the amazing performance improvement over existing solutions.



### 3 Weaknesses

O1. The SPLASHE is expensive in storage overhead.

O2. The SPLASHE also needs to change the client codes, which is usually unfriendly. For every different workload, the data organization in Seabed should be different.

O3. ASHE seems to work well with addition. However, for other more complex operations, it's not clear whether it works or not. If we have to store a different copy for each different operations, the storage overhead is too expensive.



### Validity of evaluation (strengths/weaknesses)

The evaluation shows that Seabed improves the performance of encrypted DB with order of magnitude. 



### One Idea for Future Work

The biggest problem of Seabed is how to protect the data from leaking data distribution. Though SPLASHE works, but it has a high overhead and is not friendly to users. Maybe other encryption algorithms should be considered to solve the problem.