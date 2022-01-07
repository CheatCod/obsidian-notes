---
alias: [cdf, c.d.f., c.d.f]
---
# Cumulative Distribution Function (c.d.f.)
```ad-def
A cumulative distribution function (c.d.f.) is defined as the function $F(x) = P(X \le x)$, for all real numbers x

```
```ad-example
$X$ = number of heads in three tosses of a coin:

```

| x=   | less than 0 | 0             | 1             | 2             | 3 or more |
| ---- | ----------- | ------------- | ------------- | ------------- | --------- |
| F(x) | 0           | $\frac{1}{8}$ | $\frac{4}{8}$ | $\frac{7}{8}$ | 1         | 

```ad-note
$F(x)$ is defined at all real values of $x$, not just the integers.
```ad-example
$F(1.2) = P(X \le 1.2) = \frac{4}{8}$, $F(-1) = 0, F(3.2) = 1$, etc
```

## Plot of Cumulative Distribution Function 
![[Pasted image 20211015171826.png]]

## Properties of a c.d.f.
1. $F(x)$ is non-decreasing function of x for all $x\in\mathbb{R}$
2. $0 \le F(x) \le 1$ for all $x\in\mathbb{R}$
3. $\lim_{x \to -\infty}{F(x)} = 0$ and  $\lim_{x \to \infty}{F(x)} = 1$

## Relation between $F(x)$ and $f(x)$ ([[Probability Function]])
1. If a [[Random Variables|random variable]], $X$, takes only non-negative integer values, then $F(x)$ is the probability of the values **less than or equal to $x$**
2. $f(x) = F(x) - F(x - 1)$ is the size of the **jump in** $F$ at the point x
3. $F(x) = \sum_{z \le x}{f(z)})$

Relate: [[]]