
Let $G = (V,E)$ be a graph

A subgraph of $G$ is a pair

$H = (W, F)$ in which

- $W \subseteq V$
- $F \subseteq E$
- $(W,F)$ is a graph
if $e \in \set{v,w} \in F$
then $v \in W$ and $w \in W$

Lemma: Let $G=(V,E)$ be a graph and $H = (W,F) a subgraph of $G$,

if $G$ is bipartite, then $H$ is bipartite

Proof:

Let $(A,B)$ be a bipartition of $G$. 

Then $A \cap W, B \cap W$ is a biparition of $H$

Corollary: If $G$ contains an odd cycle as a subgraph, then $G$ is not bipartite.

