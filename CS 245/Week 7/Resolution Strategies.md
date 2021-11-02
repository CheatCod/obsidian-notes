---
alias: []
---
# Resolution strategies
✔️✅📗
## Set-of-support strategy
- One paritions all clauses into two sets, the *set of support* and the *auxiliary set*
- The auxiliary set is formed in such a way that the formulas in it are *not contradictory*
- For instance, the premises are usually not contradictory. The contradiction will only arise after one adds the negation of the conclusion
- One often uses the set of premises as the "auxiliary set", and the negation of the conclusion as the initial "set of support"
- Since one cannot derive contradiction by resolving the auxiliary set, we avoid such resolutions
- Each resolution takes at least one clause from the set of support, the resolvent is then added to the set of support

```ad-example
Prove $p_4$ from $p_{1} \rightarrow p_{2}, \neg p_{2}, \neg p_{1} \rightarrow p_{3} \vee p_{4}, p_{3} \rightarrow p_{5}, p_{6} \rightarrow \neg p_{5}$ and $p_{6}$ by using the set-of-support strat

The aux set consists of the clauses obtained from $p_{1} \rightarrow p_{2}, \neg p_{2}, \neg p_{1} \rightarrow p_{3} \vee p_{4}, p_{3} \rightarrow p_{5}, p_{6} \rightarrow \neg p_{5}$

The set of support $\Sigma$ is given by $\Sigma = \set{\neg p_4}$

We then perform all the possible resolutions involving $\neg p_4$, then all possible resolutions involving the resulting resolvents
![[Pasted image 20211024234655.png]]

We see that only clause 4 contains $p_4$, so we resolve that with 7
![[Pasted image 20211024235045.png]]
cont:
![[Pasted image 20211024235238.png]]
```
Relate: [[]]