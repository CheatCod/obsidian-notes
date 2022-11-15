
**Theorem:** A graph $G = (V,E)$ is bipartite iff $G$ does not contain an odd cycle as a subgraph.

**Proof:** Weeks ago we saw that if $G$ contains a cycle, then $G$ is not bipartite.

Conversely, assume that $G$ is not bipartite.

**Reduction to the connected case:**
Let the components of $G$ be $G_1, G_2, ..., G_c$

Facts: 
- $G$ contains an odd cycle iff at least one componenet $G_i$ contains an odd cycle.
- $G$ is bipartite iff every componenet $G_i$ is bipartite 

From these facts, if the theorem holds for each component $G_i$, then it holds for $G$.

*We only need to prove the theorem for connected graphs.*

Now we can assume that $G$ is connected and not bipartite.

Since $G$ is connected, it has a spanning tree $T$.

By the lemma, $T$ has a bipartition $(A,B)$

Since $V(T) = V(G)$, and $G$ is not bipartite.

$(A,B)$ is not a bipartition of $G$

Some edge $e=xy$ of $G$ has both ends in $A$ and $B$.

Exchanging $A$ and $B$ if neccessary, we may assume that $x,y \in A$.

Let $P$ be the unique path in $T$ from $x$ to $y$. (by proposition ??)

Notie that $e$ is not in $T$, since $(A,B)$ is a bipartition of $T$, but both ends of $e$ are in $A$.

Now $C = P \cup \set{e}$ is an odd cycle in $G$. 

This follows because $P$ has an even number of edges, since both $x,y \in A$





