---
alias: []
---
# Continuous Distribution
✔️📗

Choose a random point under the graph
![[Pasted image 20211103152234.png]]
Let $X$ be the x-coordinate of the random point, and assume for convenience that the totla area under graphi is 1, that is.
$$
\int_{-\infty}^{\infty} f(x)dx = 1
$$

![[Pasted image 20211103153525.png]]

Then we have some properties of $X$:
1. $P(a < X < b) = \int_{a}^{b}f(x)dx$ 
2. $P(a \leq X \leq b) = \int_{a}^{b}f(x)dx$ (the same)
3. $P(X = a) = \int_a^{a}f(x)dx = 0$

```ad-note
This is very different from discrete distribution, as in discrete distributions it makes a difference if we include the boundry points or not

Every single point has the probability of 0, since $P(X = a)$ means the probability at EXACTLY $a$, and there are uncountable number of $a$, and by adding an unacountable number of $a$ by integrating, we get a number.
```

## The Cumulative Distribution Function

1. $P(-\infty < X \leq b) = \int_{- \infty} ^{b}f(x)d(x)$
2. The fumulative distribution function $F(X)$ of $X$ is 
$$F(X) = P(X \leq x) = \int_{-\infty}^{x}f(z)dz$$
3. By the fundamental theorem of calculus,
$$F'(x) = \frac{d}{dx} \int_{-\infty}^x{f(z)dz}= f(x)$$

## Continuous Random Variable
```ad-def
A random variable $X$, is continuous if there is a function $f(x)$ called the **probability density function (p.d.f.)** of $X$ such that for any $a < b$,
$$
P(a < X < b) = \int_a^{b}{f(x)dx}= \text{area under graph of f between a and b}
$$
```
In this case, $f(x)$ is the derivative of the cumulative distribution function $F(x)$ of $X$

## Rounding Continuous Random Variable

Suppose $F(x)$ is the c.f.g. of $X$, a continuous random variable $X$.

Suppose we don't actually observer $X$, but observe 

$Y =$ the value of $X$ rounded to the nearest $\frac{\Delta}{2}$ units, with $\Delta$ being very small, then we have

$$\begin{align*}
P[Y=y] &= P\left[y-\frac{\Delta}{2} < X \leq y + \frac{\Delta}{2}\right]\\\\
&= F\left(y+\frac{\Delta}{2}\right)- F(y-\frac{\Delta}{2})\\
&\approx f(y)\Delta
\end{align*}$$
![[Pasted image 20211103160448.png]]
This is to say that the probability at $Y$ is approximately the height ($f(y$) times the width of the interval $\Delta$

## General Properties of a P.D.F.
1. $P(A \leq X \leq b) = F(b) - F(a) = \int^b_af(x)dx$ (follows from the definition of $f(x)$)
2.  $f(x) \ge 0$ (since $F(X) is non-decreasing$)
3. $\int_{-\infty}^{\infty}f(X)dx = 1$
4. $F(y) = \int_{-\infty}^{y}f(x)dx$ and $F'(y)= f(y)$
Relate: [[]]