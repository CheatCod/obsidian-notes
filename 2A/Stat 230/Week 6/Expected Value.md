---
alias: []
---
# Expected Value
❌✔️✅📗

## Average of a Sample

Consider a sample of $n = 1,000,000$ [[Random Variables]] $X_i, i = 1,2,...n$ obtained from a distribution with [[Probability Function]] $f(x)$, for example the Poisson random variables.

In a sample of $n$ values of the random variable $X$, relative frequencies:
$$
freq(x) = \frac{\text{\# of times }X = x}{n}
$$
In other words if we count how many times $X = 0$, then divide that by $n$, we get an approximation of the probability of $X = 0$.

Similar to probabilities, $P(X = x) = f(x)$ is $n$ is large.

The average of all the $X$'s is:
$$
\frac{0 \cdot (\text{\# of times} X = 0) + 1 \cdot (\text{\# of times} X = 1)...+ x \cdot (\text{\# of times} X = x)}{n}
$$

## Expected Value
Since $n$ is large, $freq(x) \approx P(X = x) = f(x)$
```ad-def
If a discrete random variable $X$ has the p.f. $f(x)$, then the number $E(X) = \sum_\text{all x}{x \cdot f(x)}$ is the **expected value**  of $X$, denoted $E(X)$ (also referred to as **mean** or **expectation**). 
```
That is, $\sum_{\text{all x}}{\text{value of x} \cdot \text{probability of this value}}$

```ad-note
If there are infinitely many values of $X$, we require the series $\sum_\text{all x}{|x| \cdot f(x)}$ to be convergent. Otherwise we say the expected value DNE
```

```ad-example
Supposed $X$ is $Bi(5, 0.5)$ with probability function
![[Pasted image 20211030003454.png]]
Then 
![[Pasted image 20211030003514.png]]
```

We don't really expect to get 2.5 heads when we toss a coin 5 times. 
2.5 heads is the approximate long-run average when we repeat the experiment many times and average the result.

## Significant of Expected Value
$E(X) =$ The sum of (Values of $X \times$ Probability of these values)
$E(X) =$The 'fair' price to pay to play a game whose payoff is $X$
$E(X) =$The 'ceneter of gravity' of the distribution of $X$
```ad-example

![[Pasted image 20211030004118.png]]
```

The center of gravity of this triangle would be on 2

Relate: [[]]