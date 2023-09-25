
Let $R$ be a relation schema, the collection $\set{R_1,..R_n}$ of relations is a decomposition of $R$ is $R = R_1 \cup ... \cup R_n$

![[Pasted image 20221031145425.png]]


# "Good" Schema Decomp

- Lossless-join decompositions
	- We should be  able to construct the instance of the original table from the instances of the table in the composition

> [!def] Lossless
> A composition $\set{R_1,R_2}$ of $R$ is lossless iff the common attributes of $R_1$ and $R_2$ from a superkey for either schema.

- Dependency-preserving decompositions
- 