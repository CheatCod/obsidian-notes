# Ambiguity

A regex $R$ that produces a "language" $R \subseteq \set{0,1}^*$ is *unambiguous* when every string $\sigma \in R$ is produce *exactly once* by $R$

Example: $(\epsilon \cup 1 \cup 11)(0^*0(1 \cup 11))^*0^*$ is unambiguous 

Recursive way to check that a reex is unambiguous:

 $\epsilon,0,1$ are unambiguous 

Let $R, S$ be regexs producing set $R,S \subseteq \set{0,1}^*$

Assume that $R,S$ are umambiguous.

- $RS$ is unambiguous iff the function $$R \times S \to RS$$
- $$(p, \sigma) \to p \sigma$$
- is a bijection  
The cartesian product remembers the left and right.

(For every string that can be obtained from concatenantion, there is exactly one way to get it, know where the comma is)

I.E. Any string of the form $p\sigma$ with $p \in R$ and $\sigma \in S$ can be factored uniquely in this form.

Example (ambiguous)

$$(\epsilon \cup 0)^*$$

- $R \cup S$ is unambiguous iff $R \land S = \emptyset$
- $R^*$ is unambiguous iff in

$$R^* = \bigcup_{k=0}^\infty RRR...R \tag{k factors}$$
the union is disjoint and each $R^k$ is unambiguous.


# Block Decompositions

> [!def] 
> Let $\sigma = b_1b_2...b_n \in \set{0,1}^*$ be a binary string
> A *block* of $\sigma$ is a maximal non empty subsequence $b_ib_{i+i}...b_j$ of consecutive bits which are all equal. $1 \le i \le j \le n$ and $b_i = b_{i+1} =... = b_j$

Ex.

$(111)(000)(1111)(000)$ 

---

$1^*1$ produces $\set{1,11,111,1111,..}$
$0^*0$ produces $\set{0,00,000,0000,..}$ 

$(1^*10^*0)^*$ is umambiguous

Produces all binary strings that end with a 0


$0^*(1^*10^*0))^*1^*$ produces every string in $\set{0,1}^*$ ← block decompositions are unambiguous

$1^*(0^*01^*1))^*0^*$ produces every string in $\set{0,1}^*$ <- block decompositions are unambiguous

$(\epsilon \cup 1 \cup 11)^*(0^*0(1 \cup 11))^*0^*$ is a block eceomposition for the set of strings it produces: binary strings in which each block of 1s is of length one or two, no three consecutive 1s, does not contain 111 as a substring.


Ex.

Blocks of 0s have even length
Blocks of 1s have length $\ge 2$

$\set{00,0000,000000,...}$ is produced by $(00)^*00$
$\set{11,111,1111,...}$ is produced by $1^*11$

$(\epsilon \cup (00)^*00)(1^*11(00)^*00)^*(\epsilon \cup 1*11)$

is a block decomposition for the set of strings it produces

Take home notes:

1. Block decompositions are unambiguous
2. Let $R$ be a regex producing $R$, and leading to $R(x)$, if $R$ is umambiguous then $R(x) = \Phi_R(x)$ is the generating series for $R$, with respect to length