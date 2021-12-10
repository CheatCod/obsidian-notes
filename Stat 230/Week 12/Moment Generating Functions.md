---
alias: []
---
# Moment Generating Functions
❌✔️✅📗

Moments generating functions are another method for uniquely describing a distribution, it is motivated by the common use of transforms such as Laplace transforms in mathematics.

```ad-def
The moment generating function of the random variable $X$ is the function of $t$ defined by $M(t) = E(e^{Xt})$.
```

We assume that this expected finite in some interval $t \in [-a, a]$

```ad-thm
Suppose the moment generating function of the random variable $X$ is $M(t)=E(e^{Xt}).

Then

$$\begin{align*}
E(X) &= M'(0), \\
E(X^2) &= M''(0),\\
\vdots\\
E(X^k) &= M^{(k)}(0), \text{for $k = 0,1,2,...$, where $M^{(k)}(t)$ is the k'th derivative of $M(t)$}
\end{align*}$$
```

Relate: [[]]