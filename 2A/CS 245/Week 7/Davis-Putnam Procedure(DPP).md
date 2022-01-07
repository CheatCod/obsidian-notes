---
alias: [DPP]
---
# Davis-Putnam Procedure (DPP)
❌✔️✅📗

Any clause corresponds to a *set of literals*, for example, the clause $p \lor \neg q \lor r$ corresponds to the set $\set{p, \neg q, r}$

Since the order of the literals in a disjunction is irrelevant, and since duplicates do not matter too, the *set associated with the clause completely determines the clause*.

This allows us to speak the *union of 2 clauses*

We can then write the resolvent on $p$, of two clauses $C \cup \set{p}$ and $D \cup \set{\neg p}$, when neither $C$ nor $D$ is empty, as 
$$[(C\cup\set{p}) \cup (D \cup \set{\neg p})] \textbackslash\set{p \neg p}$$

In other words, the resolvent is the union of all literals in the parents clauses *except*  that two literals involving $p$ are omitted.

## The procedure:
Given as input a *nonempty set of clauses* in the propositional variables 
**Eliminating the variable $p$**:
$p_1,p_2...p_n$, the DPP repeats the following steps until no variables left:
- Remove all clauses that have both a literal $p$ and its complement $\neg p$ in them, as $p \lor \neg p$ is a tautology, and will never lead to a contradiction
- **Choose a variable $p$** appearing in one the clauses.
- Add all possible resolvents using resolution on $p$ to the set of clauses.
- Discard all clauses with $p \lor \neg p$ in them
```ad-note
If in some step one resolves $\set{p}$ and $\set{\neg p}$ then one obtains the empty clause, and it will be the only clause at the end of procedure.

If one never has a pair $\set{p}$ and $\set{\neg p}$ to resolve, then all the clauses will be discarded and the output will be *no clauses*.

Thus, the output of DPP is either the empty clause or no clause

```
Relate: [[]]