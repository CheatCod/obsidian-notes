---
alias: []
---
# Logical Consequence
❌✔️✅📗
```ad-def
Suppose $\Sigma$ is a set of formulas in $Form(L)$ and $A$ is a formula in $Form(L)$. $A$ is a logical consequence of $\Sigma$, written as $\Sigma \vDash A$, iff for any valuation $v$ with $\Sigma^{v}= 1$, we have $A^{v}= 1$
```

## Prove an argument in FOL is valid
```ad-example
Prove that 
$$\forall x \neg A(x) \vDash \neg \exists x A(x)$$
```

Note we cannot prove it directly for ALL possible valuations and domains, so we use proof by contradiction.

Suppose the contrary, that is, suppose that there is some valuation $v$ over domain $D$ s.t.
$$
1. (\forall x \neg A(x))^{v}= 1 
$$

$$
2. (\neg \exists x A(x))^{v}= 0
$$

By negating equation (2), it follows:
$$
3. (\exists x A(x))^{v}=1
$$
This implies that 
$$
4. A(d)^{v}= 1, \text{for some $d \in D$}
$$

Negate equation 4:
$$
5.(\neg A(d))^{v}= 0
$$

On the other hand, recall (1), which implies that for the individual $d \in D$ that we identified in (4), we have 

$$
6.(\neg A(d))^{v}= 1
$$

We have reached a contradiction, therefore our assumption was false.
df
Relate: [[]]