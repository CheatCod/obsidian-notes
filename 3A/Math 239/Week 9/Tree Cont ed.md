**2-outof-3 Theorem:**

Let $G = (V,E)$ be a graph with $p$ vertices and $q$ edges, if any of the two following conditions holds, then all 3 holds ($G$ is a tree)

1. $G$ is connected
2. $G$ has no cycles
3. $|V| = |E| - 1$

**Proof:**

$1 \land 2 \to 3$ is the previous theorem
$1 \land 3 \to 2$:

Assume that $G$ is connected and $p = q - 1$.

Proof by induction on $q = |E|$

Base case: $q=0$. A connected graph with $q=0, q=p-1$ has $p = 1$ vertex, and hence no cycles.

IH:  Result holds for connected $G'$ with $q' = p' - 1$, if $q' < q$

Inductive step:

Let $G$ be connected with $q = p - 1$, and $p \ge 2$ vertices 

Claim: $G$ has a vertex pf degree 1.

If not, then every vertex has degree $\ge 2$
(no vertice of degree 0 since $G$ is connected and $|V| \ge 2$)

By the handshaking lemma:

$$q = \frac{1}{2} \sum_{v \in V} deg(v) \ge \frac{1}{2} \sum_{v \in V} 2 = |V| = p > p - 1$$

Let $v \in V$ be a vertex of degree 1 in $G$, then $G' = G \backslash v$ is connected.

$q' = |E(G')| = q -1$ and $p' = |V(G')| = p -1$, therefore $p' = q' - 1$ and $q' < q$.

By induction, $G'$ has no cycles

$2 \land 3 \to 1$:

**Proof:**

Assume that $G$ has no cycles and satisfies $q = p - 1$.

Let the connected componenet of $G$ be $G_1, G_2, ..., G_c$. We want to show that $c = 1$.

Each $G_i$ is connected and does not contain a cycle, since $G$ does not contain a cycle.

Since each $G_i$ is a tree, it satisfies $q_i = p_i - 1$

Now $p = |V(G)| = p_1 + p_2 + ... + p_c$
and $q = |E(G)| = q_1 + q_2 + ... q_c$

Where $q_i = |E(G_i)|$ and $p_i = |V(G_i)|$

From condition $3$
$1 = p - q = (p_1 + p_2 ... p_c) - (q_1 + q_2 + ... + q_c)$
$= (p_1 - q_1) + (p_2 - q_2) + ..$
$= 1 + 1 + ... = c$

**Proposition**.

If $G = (V,E)$ is a connected graph, then $|E| \ge |V| - 1$ iff $G$ is a tree

**Proof:**

Induct on $q = |E|$

Base: $q = 0$, since $G$ is connected, $p = 1$, and $G$ is a tree

IH: Assume the result for graphs $G'$ with $q' = |E(G')| < q$

Inductive Step: 

If every edge of $G$ is a bridge, then $G$ is a tree (since it is conncted and every edge is a bridge).

Thus $q = p - 1$ and $G$ is a tree, as desired.

Otherwise, let $e \ E(G)$ be an edge that is not a bridge. Let $G' = G \backslash e$.

Since $e$ is not a bridge, $G'$ is connected and has $q' = q - 1$ edges and $p' = p$ vertices.

By induction, $q' \ge p' - 1$ with equality iff $G'$ is a tree.

Now $q = q' + 1 \ge (p' - 1) + 1 = p' = p > q - 1$

And sinc $e$ is not a bridge, it is contained in a cycle in $G$, so $G$ is not a tree.

