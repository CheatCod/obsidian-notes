
A walk in a graph $G = (V,E)$ is a sequence of vertices

$W : v_1v_1v_2...v_k$
in which $v_{i-1}v_i \in E$ for all $1 \le i \le k$

Repeated vertices are allowed, repeated edges are allowed.

# Path

A walk is a **path** if it has "no repeated vertices",
if $0 \le i < j \le k$ then $v_i \neq v_j$

# Trail

A walk is a **trail** if it has "no repeated edges",
if $1 \le i < j \le k$ then $(v_{i-1}, v_i) \neq (v_{j-1}, v_{j})$

**Proposition**: Let $G = (V,E)$ be a graph, and $v,w \in V$.

Any walk from $v$ to $w$ of minimum length is a path.

Proof: 

Let $w: v_0 v_1 v_2...v_k = w$ be a walk from $v$ to $w$ in $G$ of minimum length

Supposed, for the sake of contradiction, that $W$ is not a path.

Then $w$ has a repeated vertex : $0 \le i < j \le k$ with $v_i = v_j$.

Now $w_0 = v_0 v_1...v_i v_{j+1} v_{j+2}...v_k$ is a walk that is strictly shorter than $w$.

Contradiction, so $w$ is a path.

# Cycle

A walk $W : v_0v_1v_2...v_k$ is a cycle if the only repeated vertex is $v_0 = v_k$
if $0 \le i < j \le k$ and $v_i = v_j$ then $i=0$ and $j=k$
and the length is $\ge 3$

Let $G = (V,E)$ be a *non-empty* graph in which every vertex as degree $\ge2$

Then $G$ contains a cycle.

Proof:
Since $G$ is not the empty graph, $G$ has a vertex $v_0$, since $deg(v_0) \ge 2$, $v_0$ has a neighbour $v_1$.

Since $deg(v_1) \ge 2$, $v_1$ has neighbour $v_2 \neq v_0$

By inuction, for all $i \ge 1$, $v_i$ has a neighbour $v_{i+1}$ with $v_{i+1} \neq v_{i-1}$.

This constructs an infinite walk $W: v_0 v_1 v_2...$ in $G$.

Since $V(G)$ is finite, some vertext $z \in V$ must occur more than once.

Corollary:
Let $G$ be a non-empty graph, with no cycle, then there exists a vertex with a degree at most 1.

**Proposition:** Let $G=(V,E)$ be a graph
Let $v,w \in V$ be vertices

Assume that $P$ and $Q$ are two different distinct paths from $v$ to $w$, then $G$ contains a cycle

**Proof:**

Let $P : v = v_0v_1v_2..v_k=w$
and $Q: v = z_0z_1z_2...z_l = w$

Since $P \neq Q$ there is a unique index $0 \le a < min(k,l)$
Such that $v_0 = z_0, v_1 = z_1, v_2 = z_2, ..., v_a = z_a$ but $v_{a+1} \neq z_{a+1}$
Let $B$ be the first index with $a+1 \le b$ and $z_b$ being on the path $P$

Note that the index $b$ must exist because $z_l = w = v_k$ is on $P$

Since $P$ is a path, it has no repeated, there is a unique index $0 \le c \le k$ such that $z_b = v_c$

Since $Q$ is a path, the subscript $c$ satisifies $c \ge a+1$

If not, $c \le a$ then $z_c = v_c = z_b$ and $c \le a le a + 1 \le b$ so $z_c = z_b$ would be a repeated vertext on $Q$
