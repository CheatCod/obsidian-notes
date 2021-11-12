---
alias: []
---
# Distributions of Transformed Random Variable
❌✔️✅📗
```ad-example
Suppose $X$ is a continuous r.v. with probability density function $f(x) = 1$, for $0 < x < 1$ and 0 else where.

Find the c.d.f. of $Y= X^2$
```

Note that we cannot just square the density.

First we identify the c.d.f. of X
$$
F_x(x) = \int^{x}_{0} 1dz=x, \text{for $0 < x < 1$}
$$
Find the c.d.f. of $Y$

From the definition we know the c.d.f. is
$$
P(Y \leq y)
$$

We then substitute $Y$ with $X^2$


$$\begin{align*}
P(X^{2}\leq y)  &= P(0 < X \leq \sqrt{y})\\
&= F_{x}(\sqrt{y})\\
&= \sqrt{y}
\end{align*}$$

Therefore, the c.d.f is:
$$
\begin{equation}
  F_{y}(y) =
    \begin{cases}
      0 & \text{for $y < 0$ }\\
      \sqrt{y} & \text{for all }0 < y < 1\\
	  1 & \text{for }y > 1
    \end{cases}       
\end{equation}
$$

```ad-example
Suppose $X$ is a continuous random variable with probability density function $f(x) = \frac{1}{(1+x)^{2}}$, for $x > 0$ and $0$ elsewhere.

Let $Y = F(X)$, where $F$, the c.d.f. of $X$ is 
$$F(x)=\int_{0}^{x} \frac{1}{(1+z)^{2}} d z=1-\frac{1}{1+x} \text { for } 0<x<\infty$$

Find the distribution of $Y = F(X) = 1 - \frac{1}{1+x}$
$$
```

First note that the function $F(x) = 1 - \frac{1}{1+x}$ has an inverse function defined on $0 < x < \infty$

The inverse function $F^{-1}(z) = \frac{z}{1-z}$, for $0 < z < 1$

Now find the c.d.f. of $Y$.
$$
P(Y \leq y) = P(F(X) \leq y)
$$

Since $F^{-1}$ is an increasing function, we can apply it to both sides of the inequality

$$\begin{align*}
P(Y \leq y) &= P(F(X) \leq y)\\
&= P(F^{-1}(F(X)) \leq F^{-1}(y))\\
&= P(X \leq F^{-1}(y))\\
&= F(F^{-1}(y))\\
&= y
\end{align*}$$

Since $P(Y \leq y) = y$ for all $0 < y < 1$, the random variable $Y$ must have a uniform $U(0,1)$ distribution.

```ad-obs
This means that if $X$ is a continuous random variable with c.d.f., then define a random variable $Y = F(X)$ where $F$ is c.d.f. of X, $Y$ has the $U(0, 1)$ distribution
```

## Generating a R.V with c.d.f. $F(X)$ using a $U[0,1]$

```ad-thm
If $Y$ is $U(0,1)$ and $F(x)$ is any (continuous increasing) c.d.f. with inverse function $F^{-1}$, then $X = F^{-1}(Y)$ has c.d.f. $F(x)$
```

Relate: [[]]