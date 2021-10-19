
| Index, Notation                   | Rule                                                                                                                                             | Name                           |
| --------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------ |
| (1) (Ref)                         | $A \vdash A$ is a theorem                                                                                                                        | Reflexivity                    |
| (2) (+)                           | **IF** $\Sigma \vdash A$ is a theorem, <br /> **THEN** $\Sigma, \Sigma' \vdash A$ is a theorem                                                   | Addition of premises           |
| (3) ($\neg \space -$)             | **IF** $\Sigma, \neg A \vdash B$ is a theorem and $\Sigma, \neg A \vdash \neg B$ is a theorem, <br />**THEN** $\Sigma \vdash A$ is a theorem     | Negation elimination           |
| (4) ($\to \space -$)              | **IF** $\Sigma \vdash A \to B$ is a theorem and $\Sigma \vdash A$ is a theorem <br /> **THEN** $\Sigma \vdash B$ is a theorem                    | Implies elimination            |
| (5) ($\to \space +$)              | **IF** $\Sigma, A \vdash B$ is a theorem, <br /> **THEN** $\Sigma \vdash A \to B$ is a theorem                                                   | Implies introduction           |
| (6) ($\land \space -$)            | **IF** $\Sigma \vdash A \land B$ is a theorem, <br /> **THEN**   $\Sigma \vdash A$ is a theorem and $\Sigma \vdash B$ is a theorem.              | AND elimination                |
| (7) ($\land \space +$)            | **IF** $\Sigma \vdash A$ and $\Sigma \vdash B$ is a theorem, <br /> **THEN** $\Sigma \vdash A \land B$ is a theorem                              | AND introduction               |
| (8) ($\lor \space -$)             | **IF** $\Sigma, A \vdash C$ is a theorem and $\Sigma, B \vdash C$ is a theorem, <br /> **THEN** $\Sigma, A \lor B \vdash C$ is a theorem         | OR elimination                 |
| (9) ($\lor \space +$)             | **IF** $\Sigma \vdash A$ is a theorem <br />**THEN** $\Sigma \vdash A \lor B$ is a theorem and $\Sigma B \vdash \lor A$ is a theorem             | OR introduction                |
| (10) ($\leftrightarrow \space -$) | **IF** $\Sigma \vdash A \leftrightarrow B$ is a theorem and $\Sigma \vdash A$ is a theorem, <br /> **THEN** $\Sigma \vdash B$ is a theorem       |                                |
| ($\leftrightarrow \space -$)      | **IF** $\Sigma \vdash A \leftrightarrow B$ is a theorem and $\Sigma \vdash A$ is a theorem, <br /> **THEN** $\Sigma \vdash A$ is a theorem       | $\leftrightarrow$ elimination  |
| (11) ($\leftrightarrow \space +$) | **IF** $\Sigma, A \vdash B$ is a theorem and $\Sigma, B \vdash A$ is a theorem <br /> **THEN** $\Sigma, \vdash A \leftrightarrow B$ is a theorem | $\leftrightarrow$ introduction |
| $(\neg \space +)$                 | **IF** $\Sigma, A \vdash B$ and $\Sigma, A \vdash \neg B$ <br />**THEN** $\Sigma \vdash \neg A$.                                                 | Negation Plus                               |




# Double negation
```ad-thm
$\neg \neg A \vdash A$

Proof: 
1. $\neg \neg A, \neg A \vdash \neg A$ by $(\in)$
2. $\neg \neg A, \neg A \vdash \neg \neg A$ by $(\in)$
3. $\neg \neg A \vdash A$
```

# Negation Plus
```ad-thm
$(\neg+)$: If $\Sigma, A \vdash B$ and $\Sigma, A \vdash \neg B$, then $\Sigma \vdash \neg A$.

Proof: 
1. $\Sigma, A \vdash B$ (given)
2. $\Sigma, \neg \neg A \vdash \Sigma$ (by $\in$)
3. $\neg \neg A \vdash A$ (previously proved theorem)
4. $\Sigma, \neg \neg A \vdash A$ by (+), (3)
5. $\Sigma, \neg \neg A \vdash B$ by (Tr),(2),(4),(1)
6. $\Sigma, \neg \neg A \vdash \neg B$ anologous to (5)
7. $\Sigma \vdash \neg A$ by $(\neg -)$, (5), (6)
```

