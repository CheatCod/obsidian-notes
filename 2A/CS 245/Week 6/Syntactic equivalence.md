---
alias: []
---
# Syntactic equivalance
❌✔️✅📗
```ad-def
For tow formulas $A$ and $B$ we write 
$$ A \vdash \dashv$$ to mean $A \vdash B$ and $B \vdash A$. See [[Formal Deduction in Propositional Logic]]
```

```ad-thm
title: Lemma

If $A \vdash \dashv A'$ and $B \vdash \dashv B'$, then 
1. $\neg A \vdash \dashv A'$
2. $A \lor B \vdash \dashv A' \lor B'$
3. $A \land B \vdash \dashv A' \land B'$
4. $A \to B \vdash \dashv A' \to B'$
5. $A \leftrightarrow B \vdash \dashv A' \leftrightarrow B'$

```

# Replaceability of syntactically equivalant formulas 

```ad-thm
**Replaceability of syntactically equivalant formulas (Repl.):**
Let $B \vdash \dashv C$. For any $A$, let $A'$ be constructed from $A$ by replacing some *(not necessarily all)* occurences of $B$ by $C$, then $A \vdash \dashv A'$
```

more theorems on 38/62

Relate: [[Formal Deduction in Propositional Logic]]

