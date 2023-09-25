
Let $G = (V,E)$ be a graph with bipartition $(A,B)$, then $G$ has an A-saturating matching $M$ iff the following Hall's Theorem holds:

$$
\forall S \subseteq A : |N(S)| \ge |S|
$$

Where $N(S) = \set{W: wv \in E \text{ for some } v \in S}$ is the neighbourhood of $S$

Proof:

First assume that $M$ is an A-saturating matching.

For each $v \in A$, let $f(v)$ be the vertex of $B$, such that $\set{v, f(v)} \in M$. This defines an injective function $f : A \to B$

Let $S \subseteq A$ be any subset. The function $g$ restricted to $S$ gives an injective function from $S$ tp $N(S)$. So $|S| \le |N(S)|$

So Hall's condition is satisfied.

We prove the converse in the contrapositive form.

- Assume that $G$ does not have an A-saturating matching
- Show that Hall's Condition is not satisifted

Let $M \subseteq E$ be a maximum matching in $G$ 

Then $|M| \le |A|$ because $M$ is not A-saturating.

Let $C \subseteq V$ be a minimum cover of $G$.

By Konig's Theorem, $|C| = |M|$

Consider the set $S \ A = \backslash C$

Now every edge of $G$ with one end in $S$ has its other end in $C \cap B$

So $N(S) \subseteq C n B$

$|S| = |A \backslash C| = |A| - |A \cap C|$
$|C \cap B| = |C| - |A \cap C|$

So

$|N(S)| \le |C \cap B| = |M| - |A \cap C| \le |A| - |A \cap C| = |S|$

So this set $S$ show that Hall's condition is not satisified.

**Corollary to Hall's Theorem**

Let $G = (V,E)$ be a graph with bipartition $(A,B)$ assume that every verte has degree $d \ge 1$

Then $|A| = |B|$ and there are perfect matchings $M_1, M_2, ..., M_d$ such that every edge is in exactly on of these matchings.

Perfect matching: every vertex is saturated.

**Proof**

By the bipartite version of handshake lemma:

$$
d \cdot |A| = \sum_{v \in A} deg(v) = |E| = \sum_{w \in B} deg(w) = d|B|
$$

Since $D \ge 1$ it follows that $|A| = |B|$

We prove the second statement by induction on $d \ge 1$

Base: $d=1$ in this case $G$ is itself a perfect matching

IH: Assume the result for $d-1$ regular bipartite graph

Induction Let $G$ be $d$-regular.

Claim: $G$ has an A-saturating matching.

Why? Hall's condition is satisfied:

Consider any subset $S \subseteq A$

For $U \subseteq V$ let$\partial u = \set{e \in E : e \text{ is incident with exactly one vertex in u}}$

Notice that $\partial S \in \partial $N(S)$

So $|\partial S| \le |\partial N(S)|$
But since $G$ is $d$-regular,

$|\partial S| = d \cdot |S|$ and $|\partial N(S)| = d \cdot |N(S)$

Since $d \ge 1$ we conclude that $|S| \le |N(S)|$

Hall's condition is satisfied.


Let $M_d$ e an A-saturating matching of $G$. Since $|B| = |A|$, this $M_d$ is a perfect matching.

Let $H =  G \backslash M_d$. This satisfies the induction hypothesis, so can be positioned into perfect matchings $M_1, ..., M_{d-1}$

Those matchings finish the proof.