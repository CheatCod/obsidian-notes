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

