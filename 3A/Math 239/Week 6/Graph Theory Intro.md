A Graph is a pair of sets $G = (V,E)$ in which the elements of $E$ are 2-element subsets of $V$.

An element of $V$ is a vertex.
An element of $E$ is an edge.

## Circulants

Fix integer $n \ge 1$,

Let $V$ be $Z_n = \set{[0], [1],...,[n-1]}$ (integers modulo $n$)

Fix a subset $S \subseteq \mathbb{Z}_n$ with $0 \notin S$,

$E = \set{{[v], [v+s]} : v \in \mathbb{Z}_n \land s \in S}$

e.g. $n=12, S = \set{1,3,4,8}$

## Complete Bipartite Graphs

$V = \set{a_1, a_2, ..., a_r} \cup \set{b_1, b_2, ... ,b_s}$
$E = \set{a_ib_j : 1 \le i \le r, 1 \le j \le s}$

## Paths
$V = \set{1,2,...n}$
$E = \set{\set{i, i+1} : 1 \le i \le n-1}$

## Cartesian Product of Graphs

$G = (V, E)$ and $H = (W, F)$ are graphs
$V(G \times H) = V(G) \times V(H)$ (cartesian product of sets)
$(v_1, w_1)$ and  $(v_2, w_2)$ are adjacent in $G \times H$
if either ($(v_1 = v_2)$ and $w_1, w_2 \in F$) or ($(v_1, v_2 \in E(G))$ and $w_1, w_2 \in F$)

$P_a \times P_b$ is called a grid.
