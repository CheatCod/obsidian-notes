Let $G = (V,E)$ be a graph

An edge $e = \set{x,y} \in E$ is a bridge in $G$ if $c(G \backslash e) > c (G)$

$c(H)$ is the number of connected components of $H$\.

Theorem: 

Let $G = (V,E)$ be a graph and let $e \in E$, then $e$ is a bridge in $G$ iff $e$ is not contained in any cycle.

Assume that $G$ is connected (proof for exercise)

First, assume that $e = \set{x,y} \in E$ is not a bridge.

THen, $c(G \backslash e) = c(G) = 1$, since $G \backslash e$ is connected, there is a walk $W$ in $G \backslash e$ from $x$ to $y$. Any shortest walk from $x$ to $y$ is a path $P$.

Now $C = (V(P), E(P) \cup \set{e})$ is a cycle in $G$ that contains $e$.

Converse:

Assume that $e = \set{x,y}$ is contained in a cycle of $G$. To show thtat $e$ is not a bridge of $G$, we show that $G \backslash e$ is connected.

Let $v,w \in V$ be two vertices.

Since $G$ is connected, there is a path $P$ in $G$ from $v$ to $w$.

If $P$ does not use the edge $e$, then it looks like 

$P : v = v_0v_1v_2...$


# Structure of Bridges

Theorem: 

Let $G = (V,E)$ be a connected graph

Let $e = \set{X,Y}$ be a bridge in $G$

Then $G \backslash e$ has exactly 2 connected componenets $X$ and $Y$

with $x \in V(X)$ and $y \in V(y)$
