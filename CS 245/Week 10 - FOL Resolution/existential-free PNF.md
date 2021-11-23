---
alias: []
---
# $\exists$-free PNF
❌✔️✅📗
```ad-def
A sentence is said to be in $\exists$-free PNF if it does not contain the existential quantifier symbol.
```

## Skolem Functions for removal of $\exists$
```ad-example
Let the domain be $Z$ and consider $\forall x \exists y(x+y =0)$, for each x, there is a corresponding $y$ that makes the formula true.

If we define $f(x) = -x$ then we have the skolemized version of the formula $\forall x (x + f(x) = 0)$
```

More generally, in $\forall x \exists y P(x, y)$, one has a different value of $y$ generated for each value of $x$.

The skolemized version of $\forall x \exists y P(x, y)$ is $\forall x P(x, g(x))$, where $g(x)$ is the Skolem function "generating" a value.

```ad-note
The sentence obtained by using Skolem function is in general *not logically equivalent* to the original sentence. This happens because it is possible that there is more than one individual from the exstential quantifier.
```

```ad-note
It is convenient to consider individual symbols as functions of zero arguments. With this convention, the skolemized sentence remains valid even if an existential quantifier is not preceded by any universal quantifier.
```
Relate: [[]]