# Run Time Analysis

To simplfy analysis, we use the **Random Access Machine (RAM)** computing model

>[!info] RAM Model
>Assumption:
> - Any access to memory location takes constant time
> - Any primitive operation takes constant time
> - The **running time**  of a program is propotional to the number of memory access plus the number of primitive operation

This is an idealized model of computation, so these assumptions may not be valid for a “real” computer.

## Analyze an algorithm
- Count one unit per primitive operation
- **Loop:** count steps for each iteration and sum up inside out
```python
for c = 1 to n
	for j = 1 to i 
		print "hello"
```
$$\Sigma_{j=1}1 = i$$
## Asymptotic Analysis

> [!def]  Big-O ()
> Let $f(n)$ and $g(n)$ be functions we say $f(n) \in O(g(n))$
> if there exists constant $C > 0$ and $n_0 > 0$ s.t. $0 \le f(n) \le cg(n)$ for all $n \ge n_0$

> [!example] 
> $f(n) = 2n^2 + 3n+11, g(n) = n^2$, show that $f(n) \in O(g(n))$
> 
> $$\begin{align*}
> 2n^2 + 3n + 11 &\le 2n^2 +3n^2 + 11n^2, n \ge 1 \\
> &= 16n^2
> \end{align*}$$
> let $c = 16$, $n_0 = 1$
> 

We know that $2n^2 + 3n + 11 \in O(n^2)$, but also that $\in O(n^{100})$


> [!info] Tight O-bounds ($\Omega$)
> Let $f(n)$ and $g(n)$ be functions
> We say that $f(n) \in \Omega(g(n))$ if there exists constants $c > 0$ and $n_0 > 0$ s.t. $0 \le c g(n) \le f(n)$ for all $n \ge n_0$

> [!example] 
> $\frac{1}{2}n^2 - 5n \in \Omega(n^2)$
> $$\begin{align*}
> \frac{1}{2}n^2 &= \frac{1}{4}n^2 + \frac{1}{4}n^2 - 5n \\
> & \ge \frac{1}{4}n^2
> \end{align*}$$

> [!info] $\Theta$ Bound
> Big O and Big Omega
> 

## Strictly Smaller Aymptotic Notation

e.g. $2n^2$ is strictly smaller tan $n^3$

> [!info] Small-O
> $f(n) \le o(g(n))$ : $f(n)$ grows much smaller than $g(n)$
> For **any** constant $c>0$ we have $0 \le f(n) \le cg(n)$ for all $n \ge n_0$

> [!example] 
> $f(n) = n, g(n) = n^2$, show $f(n) \in o(g(n))$
> Let $c > 0$ be given
> $$\begin{align*}
> f(n) &= n \\
> &= n \cdot c \cdot \frac{1}{c} \\
> &< cn^2, n_0 \ge \frac{1}{c} \\
> \end{align*}$$


## Limit-rule

Let $f(n), g(n)$ be two positive functions
If $L = \lim_{n\rightarrow \inf} \frac{f(n)}{g(n)}$ exists, then
$$
\begin{equation}
  f(n) \in
    \begin{cases}
      o(g(n)) & \text{if $L = 0$ }\\
      \Theta(g(n)) & \text{if $0 < L < \inf$}\\
      \omega(g(n)) & \text{if $L=\inf$}
    \end{cases}       
\end{equation}
$$
## Rules for polynomial

If $f(n)$ is a polynomial of degree $d$, then $f(n) \in \Theta(n^d)$

## More rules
I