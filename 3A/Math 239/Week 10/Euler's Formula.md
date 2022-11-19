[[2022-11-18]]

Let $G = (V,E,B)$ be a multigraph with a planar embedding $(P, \Gamma)$ with face $F$.

Let $G$ have $c(G)$ connected components 

Then

$$|V| - |E| +|F| = c(G)+1$$


**Lemma:**
If $G=(V,E)$ is a *simple* graph with $|E| \ge 2$ and $(F, \Gamma)$ is a planar embedding of $G$, then every face $f \in F$ has degree $\ge 3$


**Corollary:**
If $G= (V,E)$ is simple, connected, and embedded in the plan, and $|V| \ge 3#, then every face of the embedding has degree $\ge 3$


Now let $G = (V,E)$ be a simple connected graph with $|V| = p \ge 3$.

Let $(P, \Gamma)$ be a plane embedding of $G$ with set of faces $F$

So $|V| - |E| + |F| = 2$ by Euler's formula

By the face shaking lemma: 

$$
\sum_{f \in F} deg(F) = 2|E|
$$

By the corollary, every face has $deg(F) \ge 3$

Therefore,
$$
2|E| = \sum_{f \in F} deg(F) \ge \sum {f \in F} 3 = 3|F|
$$

So
$$
6|F| \le 4|E|
$$

Multiply Euler's formula by $3$ and eliminate $|F|$

$$6 = 3|V| - 3|E| + 3|F| \le 3|V| - |E|$$

**Corollary:**

If $G$ is a connected simple planar graph with $|V| \ge 2$, then

$$
|E| \le 3|V| - 6
$$

E.g.

$G = K_5$

$|E| = 10 \ge 9 = 3|V| - 6$

So $K_5$ is not a planar graph

This argument doesn't work on $K_{3,3}$

If $G$ is a simple connected graph drawn in the plane and $G$ has no 3-cycles and $|V| \ge 2$, then every face of the embedding has degree $\ge 4$.

In this case, by the Faceshaking lemma,

$$
2|E| = \sum_{f \in F} deg(f) \ge \sum_{f in F} 4 = 4|F|
$$

So $$2|F| \le |E|$$
By eular's formula:

$$
4 = 2|V| - 2|E| + 2|F| \le 2|V| - |E|
$$

**Corollary:**

If $G = (V,E)$ is planar, connected, simple, $|V| \ge 2$ and has no 3-cycles, then

$$
|E| \le 2|V| - 4
$$

This applies to $K_{3,3}$, since

$$
|E(K_{3,3})| = 9 > 8 = 2|V(K_{3,3})| -4
$$

So $K_{3,3}$ is not planar.


# Subdivision of Edges

Let $G = (V,E)$ be a graph.

Let $e = xy$ be an edge.

The subdivision of $e$ in $G$ is denoted by $G \cdot e$, and is defined as follows:

vertices: $$
V(G \cdot e) = V(G) \cup \set{z}, z \notin V(G)
$$
edges:

$$
E(G \cdot e) = (E(G) \backslash \set{xy}) \cup \set{xz, zy}
$$

(put a new vertex $z$ of degree 2 in the middle of edge $e$)

**Lemma**.

A graph $G = (V,E)$ is planar iff $G \cdot e$ is planar

**Lemma:**

If $G$ is planar and $H$ is a subgraph of $G$ then $H$ is planar.

**Corollay:**

If $G$ contains as a subgraph a repeated subdivision of $K_5$ or $K_{3,3}$ , then $G$ is not planar.

**Kuratowski's Theorem:**

A graph is planar iff it does not contain a (repeated) subdivision of $K_5$ or $K_{3,3}$ as a subgraph

**Proof**