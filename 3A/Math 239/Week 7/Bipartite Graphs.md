Let $G = (V,E)$ be a graph.

A bipartition of $G$ is an order pair $(A,B)$ s.t.

- $A,B \subseteq V$ with $A \cup B = V$ and $A \cap B = \emptyset$
and
- For every edge $e \in E$, $e \cap A \neq \emptyset \land e \cap B \neq \emptyset$


e.g. Cycles:

Lemma: A cycle $C_n$ is bipartite iff $n$ is even

Proof.

$C_n$ has vertices $\set{0,1,2,...,n-1}$ (integer mod n)

$vw$ is an edge iff the $| v- w| \equiv 1$ mod $n$ ($v- w \equiv +-1$ mod $n$)

If $n$ is even then $A = \set{0,2,4,6,...,2n-2}$, $B = \set{1,3,5,...,2n-1}$
gives a bipartition $(A,B)$ for $C_n$

If $n$ is odd, supposed that $(A,B)$ is a bipartition of $C_n$

W.L.O.C, assume that $0 \in A$.

Since 
$0 \in A$ and $\set{0,1} \in E$, we have $1 \in B$
$1 \in A$ and $\set{1,2} \in E$, we have $2 \in B$
$2 \in A$ and $\set{2,3} \in E$, we have $3 \in B$

By induction: for all $0 \le v \le n -1$, $v \in A$ if $v$ is even, $v \in B$ if v is odd

Since $n$ is odd, $N-1$ is even, so $n-1 \in A$

Now $\set{0, n-1} \in E(C_n)$ is an edge with both ends in $A$.

So $(A,B)$ is not a bipartition.

if $G$ has no edges then $\forall S \subseteq V: (S, V \backslash S)$ is a bipartition 


