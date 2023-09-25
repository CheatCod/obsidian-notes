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

> [!def]
> **Regular Expression:**
> - $\epsilon, 0, 1$ are regex
> - If $R$ and $S$ are regex then so are $RS$ and $R \cup S$
> - If $R$ is a regex then so is $R^*$

A regular expression $R$ will
1. produce some set of strings (def 3.5)
2. leads to a rational function $R(x)$ (def 3.11)

> [!def]  Definition 3.11
> Let $R$ and $S$ be Regex leading to rational functions
> $R(x)$ and $S(x)$:
> - $\epsilon$ leads to $x^0 = 1$
> - $0$ leads to $x^1 = x$
> - $1$ leads to $x^1 = x$
> - $RS$ leads to $R(x)S(x)$
> - $R*$ leads to $\frac{1}{1-R(x)}$


$(\epsilon \cup 0)^*$ leads to $\frac{1}{1-(1+x)} = -x^{-1}$ ← this is not meaningful

## Concatenation Product (Defn 3.3)

Let $A$ and $B$ be subset of $\set{0,1}^*$

The concatenation product is the set 

$$AB = \set{ab:a \in A , b in B}$$
if $a = a_1a_2...a_m, b = b_1b_2...b_n$
Then $ab = a_1a_2...a_mb_1b_2...b_n$

> [!note] 
> This is not the same as cartesian product.
> For ex.
> $A = \set{1110, 111}, B = \set{0110, 110}$
> $A \times B = \set{1110.0110, 1110.110, 111.0110, 111.110}$ 
> $1110.0110$ is produced twice
> Therefore $AB = \set{11100110, 1110110, 111110}$

> [!def]  Defn 3.5
> Let $R, S$ be regex producing subsets $R, S \in \set{0,1}^*$
> $\epsilon$ produces $\set{\epsilon}$
> $0$ produces $\set{0}$
> $1$ produces $\set{1}$
> $RS$ produces concatenation product $RS$
> $R \cup S$ produces the union $R \cup S$ <- may not be disjoint
> $R^*$ produces $\cup_{k=0}^\infty RRRR...$ (k factor concat product)

Examples: $(\epsilon \cup 1 \cup 11)(0^*0(1 \cup 11))^*0^*$

- $(\epsilon \cup 1 \cup 11)$ produces $\set{\epsilon} \cup \set{1} \cup \set{11}$
- $0^*$ produces $\set{\epsilon, 0, 00, 000, 0000, ...}$
- $0^*0(1 \cup 11)$ produces all strings of the form $0^i1^j, i \ge 1, j = 1 \lor j = 2$
- $(0^*0(1\cup 11))^*$ produces all string that can be written in this form
-$$\sigma_1\sigma_2...\sigma_k, k \in \mathbb{N}, \sigma_i \text{is produced by } 0^*0(1 \cup 11)$$
In summary, the regex produces the set of all binary strings that do not contain 3 consecutive 1s

