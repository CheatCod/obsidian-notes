# Binary Strings

> [!def] 
> $\set{0,1}^n$ is the set of binary strings of length n.
> $\sigma = b_1b_2...b_n$, each bit $b_i \in \set{0,1}$
> The length $l(\sigma) = n$
> 

There are $2^n$ number of binary strings of length $n$

$\set{0,1}^* = \cup_{n=0}^\infty \set{0,1}^n$ is the set of all binary strings of any length

It follows from the String lemma that $$\Phi_{\set{0,1}^*}(x) = \frac{1}{1-\Phi_{\set{0,1}}(x)} = \frac{1}{1-2x}$$


## Regular Expression
- $\epsilon, 0, 1$ are regex
- if $R$ and $S$ are regex then so are $RS$ and $R \cup S$
- 
