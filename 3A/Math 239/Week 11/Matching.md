
[[2022-11-25]]

**Job assignment problem**:

Given a set of jobs $J_1, J_2, J_3...., J_a$

and a collection of processors or workers or teams $P_1, P_2, ..., P_b$

Each processor is capable of doing some subset of jobs.

Assign jobs to processor such that
- each job is assigned to $\le 1$ processor
- each processor is assigned $\le 1$ job
- get as many processors working as possible

Model with a bipartite graph

$J = \set{J_1, J_2, ..., J_a}$
$P = \set{P_1, P_2, ... , P_b}$ 

$\set{J_s, P_t}$ is an edge if processor $P_t$ can do job $J_s$

![[IMG_20221125_143926.jpg]]


#  Matching

Let $G = (V,E)$ be a simple graph.

A matching in $G$ is a set of edges $M \subseteq E$ such that every vertex in the spanning subgraph $(V,M)$ has degree $\le 1$. 

Vertex $v \in V$ is M-unsaturated if $deg_m(v) = 0$
and is M-saturated if $deg_m(v) = 1$

**Questions:**
- Given a matching, can we find a bigger matching?
- If not, how can we prove that $M$ is as big as possible.

If $G$ has a pair of vertices that are both $M$-unsaturated and are adjacent, then we can find a matching strictly bigger than $M$
![[IMG_20221125_145235.jpg]]
($P$ is an augmenting path for $M$)

Let $G = (V,E)$ be a graph.

Let $M \subseteq E$ be a matching in $G$.

Let $P: v_0,v_1,v_2,...,v_k$ be a pathin $G$.

We say that $P$ is an $M$-alternating path if for ak $1 \le i \le k -1$:

$\set{v_{i -1}, v_i} \in M$ iff $\set{v_i, v_{i+1}} \notin M$ (every other path)

Flipping $M$ alone $P$ is the symmetric difference of sets $\hat{M} = M \xor E(P)$
![[IMG_20221125_145910.jpg]]

This path $P$ is $M$-augumenting if it has at least one edge, is $M$-alternating, and the end vertices are both $M$-unsaturated.


**Proposition**

Let $G = (V,E)$ be a graph, let $M \in E$ be a matching in $G$. Then $M$ is a maximum size matching iff there is no augumenting path for $M$ 

**Proof**
First, if $P$ is an $M$-augumenting path, then $M xor E(P)$ is a strictly bigger matching than $M$, so $M$ is not a maximum matching.

Conversly, assume that $M$ is not a maximum matching in $G$.

Let $\hat{M}$ be a matching in $G$ that is bigger than $M$,

Look at the symmetric different $M xor \hat{M}$
![[IMG_20221125_151551.jpg]]

So each connected componenet of $M xor \hat{M}$ is either a path or a cycle.

Since $|\hat{M}| > |M|$, at least one component of $M \triangle \hat{M}$ has more edges from $\hat{M}$ than from $M$.

Since both $M$ and $\hat{M}$ are matchings, every cycle component of $M \triangle \hat{M}$ has the same number of edges from $M$ from $\hat{M}$.

It follows that $Q$ is an $M$-augumenting path in $G$