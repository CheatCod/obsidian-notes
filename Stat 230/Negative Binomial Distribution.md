# Negative Binomial Distribution

Suppose we have a sequence of [[Bernouli trials]] with $P(S) = p$.
Let the [[Random Variables|random variable]] $X$ be the number of failures ($F$'s) observed before obtaining the $k$'th success ($S$) 

```ad-thm
The probability function of $X$ is $$f(x) = {x+k-1 \choose x}p^k(1-p)^x, \text{for }x=0,1,2,...$$
```
$p^k$ since p is the probability of success, which is raised to the number of success.
$(1-p)^x$ since (1-p) is the probability of failure, which is raised to number of failure.

We write $X \sim NB(k,p)$

```ad-note
Alternatively, the Negative Binomial can be defined to count the total number of **trials** needed to get the $k^{th}$ success.
```

```ad-example
The fraction of a large population of males that has a specific form of colourblindness is 0.02. Suppose men are randomly selected to be tested for colourblindness.

What is the probability that exactly 10 non-colourblind men will be tested before getting 4 colourblind men?
```
This is the probability that among the first 13 men tested, we have exactly 3 that are Colourblind and then the next person selected is colourblind or
$${13 \choose 10}(0.02)^3(0.98)^{10}\times 0.02 = {13 \choose 10}(0.02)^4(0.98)^{10}$$

First 10/13 man is colorblind, then the 14th is also colorblind

## Binomial vs Negative Binomial

**Binomial**:
1. The total number of trials is specified in advanced, as $n$
2. The number of successes is unknown and can only be determined after the experiment

**Negative Binomial**:
1. The total number of trials is not specified in advance because we don't know how many trials will be needed until after the experiment
2. The number of successes is known and specified to be $k$.

## Special case: Geometric Distribution

Geometric distribution is a special case of the Negative Binomial, where $k=1$, then the [[Random Variables|random variable]], $Y$, is the number of failures until the **First** success

```ad-thm
The probability function of Y is
$$f(y) = P(Y=y)=p(1-p)^y, \text{for y = 0,1..}$$
```
We write $Y \sim Geo(p$)

```ad-note
Recall: 
$$\sum_{n=0}^{\infty} r^n = \frac{1}{1-r}$$

Thus: 
$$\begin{align*}
P(Y > y) &= p \sum_{x=y+1}^{\infty}(1-p)^x 
\\ &=p\frac{{1-p}^{y+1}}{(1-(1-p))} \\ 
&=(1-p)^{y+1} \\ \\
P(Y \le y) &= 1 - P(Y > y) \\ 
&= 1 - (1 - p)^{y+1}, y=0,1,2...
\end{align*}
$$