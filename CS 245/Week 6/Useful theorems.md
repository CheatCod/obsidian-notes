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

