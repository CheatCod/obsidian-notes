# 2.3 Compositions

> [!def] 
> A composition is a sequence of finitely many positive integers
> $$ \gamma = (c_1, c_2, ...., c_k)$$
> $k \in \mathbb{N}$ is the length of $\gamma$
> The weight of $\gamma$ is $|\gamma| = c_1 + c_2 + ... + c_k$

> [!example] 
> Composition of weight 4.
> (4)
> (3,1), (1,3)
> (2,2), (2,1,1), (1,2,1), (1,1,2)
> (1,1,1,1)

Let $\Gamma$ be the set of all compositions

Let $P = \{1,2,3,...\}$ be positive integers.

$$\Phi_p(x) = \sum_{c=1}^{\infty}x^c = x + x^2 + x^3... = \frac{x}{1-x}$$
The set of all composition is 

$$\Gamma = \cup_{k=0}^{\infty}p^k$$
By string lemma:

$$\begin{align*}
\Phi_\Gamma(x) = \frac{1}{1-\Phi_p(x)} = \frac{1}{1-\frac{x}{1-x}} &= \frac{1-x}{1-2x} \\
&= \frac{1-x}{1-2x} \\
&= \frac{1-2x+x}{1-2x} \\
&= 1 + \frac{x}{1-2x} \\

\end{align*}$$


## Examples with sets of compositions (Fri, Sep. 23)

Prototype example:

Let $P= \set{1,2,3,...}$ be the set of positive integers

So $P^k = P \times P \times ... P$ ($k$ times)

The set of all compositions is 

$$
\gamma = \cup_{k=0}^\infty P^k
$$

The union is disjoint $\to$ Sum Lemma applies
The weight function is the sum of weights of the coordinate on $P^k$ $\to$ Product Lemma applies

The generating series for $P$ is 

$$\begin{align*}
\Phi_P(x) = x^1 + x^2 + x^3... = \frac{x}{1-x}
\end{align*}$$

By Product Lemma, the generating series of $P^k$ is:

$$\begin{align*}
\Phi_{P^k}(x) = (\Phi_P)^k = (\frac{x}{1-x})^k
\end{align*}$$

By Sum Lemma:
$$\begin{align*}
\Phi_{\gamma}(x) &= \sum_{k=0}^\infty (\frac{x}{1-x})^k = \frac{1}{1-\frac{x}{1-x}} \\
&= \frac{1-x}{1-2x} \\
&=1 + \frac{x}{1-2x}\\
&= 1 + \sum_{n=1}^\infty 2^{n-1} \cdot x^n
\end{align*}$$
So for all $n\in \mathbb{N}$:

$$
\begin{equation}
  |\gamma| = [x^n]\Phi_\gamma(x) =
    \begin{cases}
      1 & \text{if $n=0$ }\\
      2^{n-1} & \text{if $n \ge 1$}\\
    \end{cases}       
\end{equation}
$$


**General Method**:

1. Identify the set of allowed values for each part in $\gamma = (c_1, c_2, ... c_k)$
2. Identify any constraints on the length of $\gamma$.
3. Describe the set $K$ using disjoint unions and cartesian pproducts.
4. Apply Sum and Product Lemmas and calculate. 

> [!example] 
> $A$: every part is $\ge 2$
> Each part is in the set $P = \set{2,3,4,...}$
> Which has generating series:
> $$\Phi_A(x) = \frac{x^2}{1-x}$$
> 
> There is no contraints on length.
> Thus by the Product Lemma, the generating series for $P^k = \frac{x^2}{1-x}^k$
> Since $k \in \mathbb{N}$ is arbitrary
> $$K = \cup_{k=0}^\infty P^k \tag{disjoint union}$$
> Sum Lemma applies and so
> $$\Phi_k(x) = \sum_{k=0}^\infty(\frac{x^2}{1-x})^k = \frac{1}{1-\frac{x^2}{1-x}} = \frac{1-x}{1-x-x^2}$$

> [!example] 
> Let $L$ be the set of compositions in which each part is odd. 
> 1. Allowed parts: $P = \set{1,3,5,7,9..}$
>  $Phi_P(x) = c \sum_{j=0}^\infty(x^2)j = \frac{x}{1-x^2}$
>2. The length has no constraint, $P^k$ has generating series $(\frac{x}{1-x^2})^k$
>3. $L = \cup_{k=0}^\infty P^k = P^*$ (String lemma)
>4. $$\Phi_L(x) = \frac{1}{1-\frac{x}{1-x^2}} = \frac{1-x^2}{1-x-x^2}$$

Even length is odd and every part is $1 (\mod 3)$
> [!example]
> 1. Allowed parts $P = \set{1,4,7,10,13, ..}$
> 2. Length $k=2j+1$ foor some $j \in \mathbb{N}$
> 3. $H = \cup_{j=0}^\infty P^{2j+1} = P \cup P^3 \cup P^5..$
> 4. Apply sum, string, product lemma, calculate:
> 5. $$\begin{align*}
> \Phi_H(x) &= \Phi_{j=0}^\infty(\frac{x}{1-x^3})^{2j+1}) \\
> &= (\frac{x}{1-x^3})^{2j+1}) \sum_{j=0}^{\infty}((\frac{x}{1-x^3})^2)^j \\
> &= \frac{x}{1-x^3} \frac{1}{1-(\frac{x}{1-x^3})^{2}} \\
> &= \frac{x}{(1-x^3)-\frac{x^2}{1-x^3}} \\
> &= \frac{x(1-x^3)}{(1-x^3)^2-x^2} \\
> \end{align*}$$

Every part is either 1 or 2
> [!example] 
> Allowed parts = $F = \set{1,2}, \Phi = (x + x^2)$
> No condition on length
> $\Phi = \frac{1}{1-x-x^2}$ (Geo Series)
> Now 
> $F(x) = \Phi_F(x) = \sum_{n=0}^\infty f_nx^n$, so $f_n = |F_n|$

$$\begin{align*}

F(x) &= \frac{1}{1-x-x^2} \\
(1-x-x^2) \sum_{n=0}^{\infty} f_nx^n &= 1 \\
\sum_{n=0}^{\infty} f_nx^n - x\sum_{n=0}^{\infty} f_nx^n - x^2\sum_{n=0}^{\infty} f_nx^n &= 1 \\
\sum_{n=0}^{\infty} f_nx^n - \sum_{n=0}^{\infty} f_nx^{n+1} - \sum_{n=0}^{\infty} f_nx^{n+2} &= 1 \\
\sum_{n=0}^{\infty} f_nx^n - \sum_{i=1}^{\infty} f_{j-1}x^{i} - \sum_{j=2}^{\infty} f_{j-2}x^{j} &= 1 \\
\sum_{n=0}^{\infty} f_nx^n - \sum_{n=1}^{\infty} f_{n-1}x^{n} - \sum_{n=2}^{\infty} f_{n-2}x^{n} &= 1 \\
f_0x^0 + (f_1-f_0)x + (f_2-f_1-f_0)x^2 + \sum_{n=3}^\infty(f_n - f_{n-1} - f_{n-2}) &= 1
\end{align*}$$


> 
> 






