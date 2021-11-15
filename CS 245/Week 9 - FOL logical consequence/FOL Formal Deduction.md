---
alias: []
---
# FOL Formal Deduction
❌✔️✅📗


## Additional 

| Index, Notation                   | Rule                                                                                                                                                                                                                                                                      | Name                           |
| --------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------ |
| (1) (Ref)                         | $A \vdash A$ is a theorem                                                                                                                                                                                                                                                 | Reflexivity                    |
| (2) (+)                           | **IF** $\Sigma \vdash A$ is a theorem, <br /> **THEN** $\Sigma, \Sigma' \vdash A$ is a theorem                                                                                                                                                                            | Addition of premises           |
| (3) ($\neg \space -$)             | **IF** $\Sigma, \neg A \vdash B$ is a theorem and $\Sigma, \neg A \vdash \neg B$ is a theorem, <br />**THEN** $\Sigma \vdash A$ is a theorem                                                                                                                              | Negation elimination           |
| (4) ($\to \space -$)              | **IF** $\Sigma \vdash A \to B$ is a theorem and $\Sigma \vdash A$ is a theorem <br /> **THEN** $\Sigma \vdash B$ is a theorem                                                                                                                                             | Implies elimination            |
| (5) ($\to \space +$)              | **IF** $\Sigma, A \vdash B$ is a theorem, <br /> **THEN** $\Sigma \vdash A \to B$ is a theorem                                                                                                                                                                            | Implies introduction           |
| (6) ($\land \space -$)            | **IF** $\Sigma \vdash A \land B$ is a theorem, <br /> **THEN**   $\Sigma \vdash A$ is a theorem and $\Sigma \vdash B$ is a theorem.                                                                                                                                       | AND elimination                |
| (7) ($\land \space +$)            | **IF** $\Sigma \vdash A$ and $\Sigma \vdash B$ is a theorem, <br /> **THEN** $\Sigma \vdash A \land B$ is a theorem                                                                                                                                                       | AND introduction               |
| (8) ($\lor \space -$)             | **IF** $\Sigma, A \vdash C$ is a theorem and $\Sigma, B \vdash C$ is a theorem, <br /> **THEN** $\Sigma, A \lor B \vdash C$ is a theorem                                                                                                                                  | OR elimination                 |
| (9) ($\lor \space +$)             | **IF** $\Sigma \vdash A$ is a theorem <br />**THEN** $\Sigma \vdash A \lor B$ is a theorem and $\Sigma \vdash B  \lor A$ is a theorem                                                                                                                                     | OR introduction                |
| (10) ($\leftrightarrow \space -$) | **IF** $\Sigma \vdash A \leftrightarrow B$ is a theorem and $\Sigma \vdash A$ is a theorem, <br /> **THEN** $\Sigma \vdash B$ is a theorem                                                                                                                                |                                |
| ($\leftrightarrow \space -$)      | **IF** $\Sigma \vdash A \leftrightarrow B$ is a theorem and $\Sigma \vdash A$ is a theorem, <br /> **THEN** $\Sigma \vdash A$ is a theorem                                                                                                                                | $\leftrightarrow$ elimination  |
| (11) ($\leftrightarrow \space +$) | **IF** $\Sigma, A \vdash B$ is a theorem and $\Sigma, B \vdash A$ is a theorem <br /> **THEN** $\Sigma, \vdash A \leftrightarrow B$ is a theorem                                                                                                                          | $\leftrightarrow$ introduction |
| $(\neg \space +)$                 | **IF** $\Sigma, A \vdash B$ and $\Sigma, A \vdash \neg B$ <br />**THEN** $\Sigma \vdash \neg A$.                                                                                                                                                                          | Negation Plus                  |
| (12) ($\forall -$)                | **IF**  $\Sigma \vdash \forall x A(x)$ is a theorem<br /> **THEN** $\Sigma \vdash A(t)$, where $t$ is any term, is a theorem                                                                                                                                              | For all Minus                  |
| (13) ($\forall +$)*                | **IF** $\Sigma \vdash A(u)$ is a theorem, <br /> and *u does not occur in $\Sigma$*<br /> **THEN** $\Sigma \vdash \forall x A(x$ is a theorem                                                                                                                             | For all Plus                   |
| (14) ($\exists -$)                | **IF** $\Sigma, A(u) \vdash B$ is a theorem, <br /> and *u does not occur in $\Sigma$ or $B$* <br /> **THEN** $\Sigma, \exists x A(x) \vdash B$ is a theorem                                                                                                              | Exists minus                   |
| (15) ($\exists +$)                | **IF** $\Sigma \vdash A(t)$ is a theorem <br />**THEN** $\Sigma \vdash \exists x A(x)$ is a theorem, <br /> where $A(x)$ results from $A(t)$ by replacing some (not necessarily all) occurences of $t$ by $x$                                                             | Exists Plus                    |
| (16) ($\approx -$)                | **IF** $\Sigma \vdash A(t_1)$ is a theorem <br /> and $\Sigma \vdash t_1 \approx t_2$ is a theorem, <br /> **THEN** $\Sigma \vdash A(t_2)$ is a theorem, <br /> where $A(t_2)$ results from $A(t_1)$ by replacing some (not necessarily all) occurences of $t_1$ by $t_2$ |                                |
| (17) ($\approx +$)                | $\emptyset \vdash u \approx u$ is a theorem.                                                                                                                                                                                                                                                                          |                                |

```ad-note
In $(\forall -)$, $(\forall +)$, $(\exists -)$the formula $A(t)$ results from $A(x)$ by substituting all occurences of $x$ by $t$

In $(\exists +)$, the replacement allows us to either substitude all occurences or only some occurences
```

\*
The rule $(\forall +)$ means intuitively that from
"ANY element of a set has a certain property", we can deduce that 
"EVERY element of the set has this property"

This arugment only works since "any" means an arbitrary element, with no restriction whatsoever. The arbitrariness of $P$ means that the choices of $P$ is *independent* of the premises of the theorem. 

This is expressed syntactically in ($\forall +$) by *u not occuring in $\Sigma$*


Relate: [[]]