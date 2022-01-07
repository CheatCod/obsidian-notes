---
alias: []
---
# Resolution
✔️✅📗
Resolution theorem proving is a method of [[Formal Deduction in Propositional Logic|formal deduction]] that has the following features.
-	The only formulas allowed in resolution theorem proving are *disjunction of literals*, such as $(p \lor q \lor \neg r)$
-	Recall that such a disjunction of literals is called a *disjunctive clause*. Hence, all formulas involved in resolution theorem proving must be disjunctive clauses.
-	There is only one rule of formal deduction, **resolution**


To prove the argument $A_1, A_2, A_3...A_n \vDash C$ is valid, we show that the set $$\set{A_1, A_2, A_3...A_n, \neg C}$$

is *not satifisable* 

Recall that  $A_1, A_2, A_3...A_n \vDash C$ means that when all the argument is true, the conclusion is true, thus the negation of the conclusion is always false, thus it for all truth valuation.

For the resolution algorithem, the formula must be converted into a CNF

```ad-def
Resolution is the formal deduction rule
$$C \lor p, D \lor \neg p \vdash_r C \lor D$$
where $C, D$ are disjunctive clauses, and $p$ is a literal.

- $C \lor p$ and $D \lor \neg p$ are called parent clauses, and we say that we are *resolving the two parent clauses over p*
- $C \lor D$ is called the resolvent
- The resolvent of $p$ and $\neg p$ is called the *empty clause* ad is denoted by $\set{}$:
$$p, \neg p \vdash_r \set{}$$
- A **(resolution) derivation** from a set of clauses $S$ is a finite sequence of clauses such that each clause is either in $S$ or results from previous clauses in sequence by resolution
```

```ad-note
- We can only resolve two clauses if and only if they contain **two complementary literals**, say $p, \neg p$
- If the complementary literals are $p$ and $\neg p$, one say we **resolve over $p$**, or that **the resolution is on $p$**
- The result of resolution on $p$ is the **resolvent**, which is the **disjunction of all literals of the parent clauses**, except that **$p$ and $\neg p$ are omitted**
- If the two parent clauses are $p$ and $\neg p$,  their resolvent is called the *empty clause* and is denoted by $\set{}$. This signifies that the contradiction $p \land \neg p$ was reached. 
- **By definition, the empty clause is not satifisable**
```

```ad-example
Find the resolvent of $p \lor \neg q \lor r$ and $\neg s \lor q$.

Sol: The two parent clauses  $p \lor \neg q \lor r$ and $\neg s \lor q$ can be resolved over $q$, because $q$ is negative in the first clause and positive in the second.

The reolvent is the disjunction of $p \lor r$ with $\neg s$, which yields $p \lor r \lor \neg s$
```

## Proving argument validity with resolution
- To prove the argument $A_1, A_2, A_3...A_n \vDash C$ is valid, we show that from the set $$\set{A_1, A_2, A_3...A_n, \neg C}$$ we can derive, by $\vdash_r$, the empty cluase $\set{}$ (a contradiction), as follows:	
	- Preprocess the input by transforming each of the formulas into *conjunctive normal form*
	- Make each disjunctive clause a distinct clause. These clauses are the input of the [[#resolution procedure]]
	- If the resolution procedure outputs  the empty clause, $\set{}$, this impleis the set is not satifisable, hence the argument is valid
## Resolution procedure
INPUT: Set of disjunctive clauses $S = \set{D_1, D_2,..., D_m}$
REPEAT: trying to get the empty clause $\set{}$:
- Choose two clauses, one with $p$ one with $\neg p$
- Resolve and call the resolvent $D$
- if $D=\set{}$, then output "empty clause"
- else add $D$ to $S$
```ad-example
Prove that $$p, p \to q \vdash_r q$$
Proof: 
![[Pasted image 20211024211830.png]]
```

```ad-warning
- Remember the **negation** of the conclusion
- **DO NOT** apply resolution to more than one literal.
```



Relate: [[]]