---
alias: [PNF]
---
# Prenex Normal Form 
❌✔️✅📗
```ad-def
A formula is in PNF if it is of the form 
$$
Q_1x_1Q_2x_2...Q_nx_nB
$$
where $n\leq1$, $Q_i$ is $\forall$ or $\exists$, for $1 \leq i \leq n$, and the expression $B$ is quantifier tree.
```

The string $Q_1x_1Q_2x_2...Q_nx_nB$ is called the prefix and $B$ is called the matrix.

```ad-note
A formula with no quantifierrs is regarded as a trivial case of the PNF
```


## Algorithm to convert a formula into PNF

1. Eliminate all occurences of $\to$ $\leftrightarrow$ 
2. Move all negations inward, such that, negtions only appear as part of literals
3. Standardize the variables apart, when necessary
4. The PNF can now be obtained by moving all quantifiers to the front of the formula

To accomplish Step 2, use the logical equivalences:
- De Morgan's Laws
- Double negation
- $\neg \exists x A(x) \vDash \vdash  \forall X \neg A(x)$

To accomplish Step 3, replace all duplicate occurences of bound variable by a unique name.

To accomplish Step 4, use the logical equivalences:
- $A \land \exists x B(x) = \exists x (A \land B(x))$
- $A \land \forall B(x) = \exists x (A \land B(x)))$
- $A \lor \exists B(x) = \exists x (A \lor B(x)))$
- $A \lor \forall B(x) = \forall x (A \lor B(x)))$

$x$ not occuring in $A$.

These equivalences essentially show that if a formula $A$ has a truth value that does not depend on $x$, then one is allowed to quantify, using any quantifier over $x$

More logical equv for Step 4:
- $\forall x A(x) \land \forall x B(x) = \forall x (A(x) \land B(x))$
- $\exists  x A(x) \lor \exists x B(x) = \exists x (A(x) \lor B(x))$
- $\forall x \forall y A(x, y) = \forall y \forall x A(x, y)$
Relate: [[]]