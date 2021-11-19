---
alias: []
---
# Computer Generation of Random Variables
❌✔️✅📗

## Invertible C.D.F
Suppose we have a random variable, $X$, with a non-uniform distribution with given c.d.f. $F(x)$

Assumes the c.d.f. is continouse strictly increasing, then it has an *inverse function* $F^{-1}(y)$ such that $F(F^{-1}(y)) = y$

if $U$ has a $U(0,1)$ distribution and $X = F^{-1}(U)$, then 
$$
P(X \leq x) = F(x)
$$

Therefore, $X = F^{-1}(U)$ has the desired c.f.d. $F(X)$

We've discovered a method for producing a random variable with a given c.d.f., provided that the c.d.f. is continuous and strictly increasing.

## Generalized inverse C.D.F.

```ad-def
For arbitrary c.d.f. $F(x)$, define $F^{-}(y) = min\{x;F(x)\ge y\}$
```

This is a real inverse iff the c.d.f. is continuous and strictly inreasing.

For $F(x)$ possibly discontinuous or non-decreasing, $F^-$ is similar but not exactly same to inverse.

## Computer Generation of Random Variables: General Case

```ad-thm
if $F$ is an arbitrary c.d.f. and $U$ is uniform on $[0,1]$, then the random variable defined by $X = F^-(U)$ has c.d.f. $F(x)$
```

Relate: [[]]