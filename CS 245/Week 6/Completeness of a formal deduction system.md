---
alias: []
---
# Completeness of a formal deduction system
❌✔️✅📗
Consider a system of formal deducibility, denoted by $\vdash_*$, defined by a certain formal deduction rules.

Suppose that the statement "IF $\Sigma \vDash A$, THEN $\Sigma \vdash_* A$" is true for any set of formulas $\Sigma$ and formula $A$

This means that anything that holds by informal resoning can be prved using the system of forma deducibility $\vdash_*$. In other words, it means ==whatever is correct, can be formally proved using the system $\vdash_*$==

```ad-def
If this property  "IF $\Sigma \vDash A$, THEN $\Sigma \vdash_* A$" holds for a system of formal deducibility, the system is called **Complete**
```

```ad-thm
**Completeness Theorem**: if $\Sigma \vDash A$ then $\Sigma \vdash A$, where $\vdash$ means the formal deduction based on the 11 given rules.
```

Relate: [[]]