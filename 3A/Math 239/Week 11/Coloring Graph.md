Let $G = (V,E)$ be a simple graph.

Let $k \ge 1$ be an integer.

A proper $k$-colouring of $G$ is a function

$f : V(G) \to \set{1,2,3,...,k}$ 

with the property that if $vw \in E$ then $f(v) \neq f(w)$

Chromatic number of $G : \chi$ is the smallest $k$ for which $G$ has a proper $k$-colouring


**Graph of small chromatic number**

$\chi = 0$, empty graph
$\chi = 1$ at least 1 vertex, no edge
$\chi = 2$ bipartite with at least one edge
$\chi = 3$ no good characterization


# Six-colour Theorem

Let $G=(V,E)$ be a planar simple graph.

Tuhs $G$ has a proper $6$-colouring $f :v \to \set{1,2,3,4,5,6}$

**Proof**:

Induct on $|V|$

Base case:

$|V| \le 6$: then trivial

IH: Assume the result if $G$ has $p-1$ vertices

Inductive Step:

Let $G$ be a planar simple graph with $|V| = p \ge 7$

By a previous lemma, $G$ has a vertex of degree at most 5.

Now $G \backslash v$ satisfies the IH, by induction, there is a proper 6-colouring.

Since $V$ has at most 5 neighbours, at most 5 colour is used on those neighbours, so there is at least 1 color for the edge

# Five-colour Theorem

A simple planar graph $G = (V,E)$ has a proper 5-colouring 

**Proof:** Induct on $|V|$

Base: $|V| < 5$ any injective functions works.

IH: Let $G$ be a simple planar graph with $|V| = p \ge 6$

By previous lemma, $G$ has vertex $v$ of degree at most 5.

By induction, $G \backslash v$ has a proper 5-colouring

There is a volour available to use for $f(v)$ except in the case that $deg(v) = 5$ and all 5 colours are used in the neighbours
$w_1, w_2, w_3, w_4, w_5$ of $v$ in $G$

Now embed $G$ in the plane $R^2$ and number the certices adjacent to $v$ in clockwise order around the point representing $v$. 

![[Pasted image 20221123145718.png]]

We can also permute the colours so that vertex $w_i$ gets colour $i$.

Next, we adjust the colouring $f : V \backslash \set{v} \to \set{1,2,3,4,5}$ to get a new proper colouring $f : V \to \set{v} \to \set{1,2,3,4,5}$

That only uses 4 colours on the neighbours of $v$.

For $1 \le i < j \le 5$, let $G_{i,j}$ be the subgraph of $G$ induced by the set of vertices $\set{z \in V \backslash \set{v}: f(z) = i \lor f(z) = j}$ 

Each $G_{i,j}$ is bipartite, let $H$ be a connected componenet of $G_{i,j}$.

"Flip the colours" on the component $H$ to get a new $5$ colouring.
![[Pasted image 20221123151152.png]]



![[IMG_20221123_152204.jpg]]
![[IMG_20221123_152207.jpg]]
![[IMG_20221123_152317.jpg]]