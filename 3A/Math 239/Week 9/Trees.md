A graph is **minimally connected** if it is connected and has "no redundancy", that is, every edge is a bridge.

**Lemma:** A graph is minimally connected iff it is connected and does not contain a cycle.

**Proof:**
$\rightarrow$
Assume that $G = (V,E)$ is minimally connected. 

Suppose that $C \in G$ is a cycle, let $e \in E(C)$, then $e$ is not a bridge, so $G$ has no cycles.

$\leftarrow$
Conversly, assume that $G$ is connected and has no cycles, if $e \in E(G)$ is not a bridge, then $e$ is in a cycle of $G$. (by prop ??)

> [!def] Tree
> A graph is a **tree** is it is connected, and it does not contain any cycles 

**Proposition:** If $T=(V,E)$ is a tree with $|V| \ge 2$ vertices, then $T$ has $\ge 2$ vertices of degree 1

**Proof:**

Let $P: v_0v_1...v_k$ be a path in $T$ that is as long as possible. Since $T$ is connected and $|V| \ge 2$, $T$ has at least one edge. So $P$ has at least 2 vertices, so $v_0 \neq v_k$

Now $v_0$ has degree 1 in $T$

Suppose not: let $v_0 w \in E(T)$ with $w \neq v_q$

If $w$ is not on $p$, then $wv_0v_1v_2...v_k$ is a path in $T$ that is strictly smaller than $P$, therefore a contradiction.

Therefore, $w$ is on $P$, say $w = v_j$ for some $2 \le j \le k$.

Now $v_0v_1v_2...v_jv_0$ is a cycle, therefore a contradiction.

So $w$ can't exist.
So $v_)$ has degree 1 in $T$

Similary, $v_k$ also has degree 1 in $T$

**Proposition:** Let $T = (V,E)$ be a tree with $|V| = p$ vertices and $|E| = q$ edges. Then $q = p-1$.

There are mainly 3 proof techniques in graph theory:

1. Direct proof
2. Proof by contradiction
3. Proof by induction

**Proof:** By induction o $p = |V|$ 
Base: $p=1, q=0$

Induction hypothesis: Assume the result for all trees with $<p$ vertices.

Inductive step:

Let $T = (V,E)$ be a tree with $|V| = p \ge 2$ vertices.

By the lemma, $T$ has a leaf $v \in V$, a vertex of degree 1.

Let $e = vw$ be the only edge of $T$ incident with $v$

Let $T' = (V \backslash \set{v}, E \backslash \set{e})$ be obtained by deleting $v$ from $T$.

Claim: $T'$ is a tree.

**Proposition:**

Let $G = (V,E)$ be a non-empty connected graph, then $G$ is a tree iff for any $v,w \in V$, there is exactly one path in $G$ from $v$ to $w$