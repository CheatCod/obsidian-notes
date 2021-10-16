---
alias: []
---
# Poisson Distribution
```ad-def
Suppose that $X$ represents the number of events of some type, occuring at a rate of $\mu > 0$. Then a [[Random Variables|random variable]] $X$ has a Poisson distribution if the probability function of $X$ is:
$$
f(x) = \frac{e^{-\mu}\mu^x}{x!}, \text{for }x =0,1,2...
$$

```
We wrtie $X \sim Poisson(\mu)$

Suppose $X$ has Binomial distribution, $n$ is large and $p$ is small.
Let $\mu = np$. Fix $u$, let $p = \frac{\mu}{n}$ and let $n$ grow large.

**Meaning of $\mu$**:
$\mu$ is called the **expected number**.
e.g., if n = 1000, p = 0.001, then np = 10 = "average number of success".
```ad-example
Suppose the average number of calls to a call center in an hour is 8. Find the probability that in a given hour, there are at least three calls.
```
If $X$ is the number of calls in an hour, then $X \sim Poisson(\mu), \mu = 8$ with probability Function
$$f(x) = \frac{e^{-8}8^x}{x!}, x = 0,1,2$$
We want $P(X \ge 3)$
$$\begin{align*} 
P(X \ge 3) &= 1-P(x \le 2) \\ 
&= 1-f(0)-f(1)-f(2) \\ 
&= 1-e^{-8}-8e^{-8}-\frac{e^{-8}8^2}{2}
\end{align*}
$$ 

##  Approximation to the Binomial Distribution

Relate: [[Random Variables]]