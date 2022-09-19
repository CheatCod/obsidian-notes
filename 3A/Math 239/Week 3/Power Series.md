# Calculation with power series

let $A(x) = \sum_{i -> \inf} a_ix^i$ and $B(x) = \sum_{j -> inf} b_jx^j$

## Sum.

$$\begin{align*}
A(x) + B(x) &= \sum_{i -> \inf} a_ix^i + \sum_{j -> \inf} a_jx^j \\
&= \sum_{n -> \inf} a_nx^n + \sum_{n -> \inf} a_nx^n = \sum_{n -> \inf} (a_n + b_n)x^n
\end{align*}$$


## Product:
$$\begin{align*}
A(x)B(x) &= \sum_{i -> \inf} a_ix^i \sum_{j -> \inf} a_jx^j \\
&= \sum_{i -> \inf} \sum_{j -> \inf}  a_ix^i \cdot a_jx^j \\ 
&= \sum_{i -> \inf} \sum_{j -> \inf}  a_i a_j x^{i+j} \\ 
\end{align*}$$

Reindex this to collect all terms which give the same exponenet of x:
$$\sum_{k -> \inf}(?)x^k$$
Set $k= i+j$

Here $i \ge 0, j \ge 0$ so $k \ ge 0 $ and $0 \le i \le k$
![[Pasted image 20220919143957.png]]

So $$A(x)B(x) = \sum_{i -> \inf} \sum_{j -> \inf}  (a_i a_j) x^{i+j} = \sum_{k -> \inf} (\sum_{i -> k} a_ib_{k-1}) x^k$$

## Extracting Coeffcient

> [!def] 
For $n \in \mathbb{N}$ $[x^n]A(x) = a_n$ is the coeffecient of $x^n$ in$A(x)$

> [!example] 
> $[x^k](1+x)^n = {n \choose k}$ (Binomial Theorem)
> $[x^n]\frac{1}{1-x}^t = {n + t - 1 \choose t - 1}$ (Binomial Series)

For any $a,b \in \mathbb{N}$, note that:

$$(1+x)^{a+b} = (1+x)^a(1+x)^b$$
LHS:
$$[x^k] (1+x)^{a+b} = {a+b \choose k } \tag{Binomial Theorem}$$
RHS:
$$\begin{align*}
 [x^k](1+x)^a(1+x)^b \\
&= [x^k](\sum_{i=0}^a {a \choose i}x^i)(\sum_{j=0}^b {b \choose j}x^j) \\
\end{align*}$$
reindex with $p = i + j$ 
so $0 \le p \le a + b$
and $0 \le  i \le min(p,a)$
