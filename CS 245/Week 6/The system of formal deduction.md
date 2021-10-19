---
alias: []
---
# The system of formal deduction
❌✔️✅📗
## Why do we need formal deduction?
Recall that tautological consequence, $\vDash$ is defined in terms of the truth values and truth valuations, corresponds to **informal deducibility** and involves **semantics**, whereas [[Formal Deduction in Propositional Logic|formal deducibility]] is concerned with the syntactical structures of formulas and involves syntax.

we wish to define something called **formal deduction**, based on the 11 axioms of formal deduction rules, where which we could prove formally, everything that is correct semantically.

For one system to be "good", it has to be connected to *informal reasoning*  in the following sense:
1. **We should not be able to prove incorrect statement** (soundness)
2. **We should be able to prove every correct statement from first principles (the deduction rules** (completeness)

## Soudness
```ad-def
**Soundness**:

A system of formal deducibility, denoted by $\vdash_*$ is defined yb listing its formal deduction rules. We say that the system is **sound**, that is, what can be proved formally, also holds in informal reasoning. In other words, it means we **cannot prove incorrect statements** in the system $\vdash_*$.
$$\text{if } \Sigma \vdash_* A, \text{THEN } \Sigma \vDash A, \text{is true for any } \Sigma, A$$
```

```ad-thm
**Soundness Theorem:** The formal deduction  $\vdash$based on 11 given rules is sound

**Proof by structural induction:**
Base case (Ref): if $A \vdash A$, then $A \vDash A$, obvious

**Inductive Case: **
**Subcase of $(\neg -)$**
We prove by replacing all $\vdash$ by $\vDash$ in 

if $\Sigma, \neg A \vdash B$, and
$\Sigma, \neg A \vdash \neg B$, 
then $\Sigma \vdash A$

and the resulting statement holds

Suppose $\Sigma, \neg A \vDash B$, and $\Sigma, \neg A \vdash \neg B$.

Assume $\Sigma \nvDash A$, that is, there is a truth valuation $t$ such that $\Sigma^{t}=1$, and $A^{t}= 0$, then, $(\neg A)^{t}= 1$

Since $\Sigma, \neg A \vDash B$ and $\Sigma, \neg A \vDash \neg B$, this implies $B^{t}= 1$ and $\neg B^{t}= 0$, which is a contradiction $\Box$

**Subcase of $(\lor -)$**:
...Replace...

Suppose $\Sigma, A \vDash C$ and $\Sigma, B \vDash C$.

Let $t$ by an arbitrary truth valuation such that $\Sigma^t=1$ and $(A\lor B)^t=1$. Then either $A^{t}=1$ or $B^t=1$.

Case (a): If $A^{t}=1$, then by $\Sigma, A \vDash C$, we have $C^{t}= 1$
Case (b): If $B^{t}=1$, then by $\Sigma, B \vDash C$, we have $C^t=1$
Hence $C^t$ = 1, which implies that $\Sigma A \lor B \vDash C$
```

## Completeness
Consider a system of formal deducibility, denoted by $\vdash_*$, defined by a certain formal deduction rules.

Suppose that the statement "IF $\Sigma \vDash A$, THEN $\Sigma \vdash_* A$" is true for any set of formulas $\Sigma$ and formula $A$

This means that anything that holds by informal resoning can be prved using the system of forma deducibility $\vdash_*$. In other words, it means ==whatever is correct, can be formally proved using the system $\vdash_*$==

```ad-def
If this property  "IF $\Sigma \vDash A$, THEN $\Sigma \vdash_* A$" holds for a system of formal deducibility, the system is called **Complete**
```

```ad-thm
**Completeness Theorem**: if $\Sigma \vDash A$ then $\Sigma \vdash A$, where $\vdash$ means the formal deduction based on the 11 given rules.

Proof: wtf?
```

## Connection between syntax and semantics 
Te Soundness and Completeness Theorems associate the syntactic notion of a formal deduction, based on the 11 rules, with the semantic notion of tautological consequence, and establish the equivalence between them

The two theorems say that with formal deduction (11 rules), we can prove 

**The truth,
The whole truth, ** (completeness)
**and nothing but the truth** (soudness)

```ad-warning
Formal deduction cannot be used to prove an argument is invalid! 
```
Relate: [[]]