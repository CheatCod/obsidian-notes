---
alias: []
---
# Variance
❌✔️✅📗

Although the following 3 graphs have the same mean ($E(X) = 70$), the distributions are massively different.
![[Pasted image 20211030021413.png]]
**Top figure:**
-	Average distance from mean of 20
-	distance squared of $20^2$

**Middle figure**
- avg distance of 0
- avg distance squared of 0

**Bottom  figure**
- avg distance of 11
- avg distance squared of 210
```ad-note
The average distance by itself is not very tractable mathematically, so we typically use the **squared** or square root
```

```ad-def
If a random variable $X$ has an expected value of $E(X) = \mu$, then the average squared distance between $X$ and $\mu$ is $E[(X-\mu)^2]$ and is called the **variance** of $X$, or $Var(X)$
```
```ad-def
The square root of variance is called the **standard deviation**, denoted $\sigma$ or $SD(X)$
```

## Simpler Formulas For Var(x)
$Var(X) = E(X^2)-\mu^2$
```ad-thm
For many standard distributions, with $E(X) = \mu$, we can use 
$$Var(x=E[X(X-1)]+\mu-\mu^2$$
```

## Properties of Var and STD
```ad-thm
If $X$ is a random variable and $a, b$ are some constants, then
1. $Var(aX+b) = a^2Var(x)$
2. $SD(aX+b) = |a| \times SD(X)$
```
This means that adding a constant to the variance DOES NOT affect anything
Relate: [[]]