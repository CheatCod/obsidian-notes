> [!def] 
> Let $G = (V,E)$ be a graph
> A subgraph $H = (W,F)$ is spanning if $W = V$, that is, $H$ uses all the vertices of $G$
> A spanning tree of $G$ is a spanning subgraph that is a tree


**Propositon:** A graph $G = (V,E)$ is cnnected iff it has a spanning tree

**Proof:** If $T$ is a spanning tree in $G$ and $v,w \in V(G)$.

Then $v$ reaches $w$ in $T$ (since $V(T) = V(G)$ "spanning" and $T$ is connected). Since $T$ is a subgraph of $G$, $v$ reaches $w$ in $G$, then $G$ is connected.

Conversely:

Assume that $G$ is connected, show that $G$ has a spanning tree by indcution of $q = |E|$

Fix the vertex set $V(G)$ with $|V| = p$. By the previous proposition, $q \ge p - 1$ with equality iff $G$ is a tree.