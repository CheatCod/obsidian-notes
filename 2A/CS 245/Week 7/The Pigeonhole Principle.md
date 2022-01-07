---
alias: []
---
# The Pigeonhole Principle
❌✔️✅📗
```ad-concept
The **Pigeonhole Principle $P_n$** says that one cannot put $n+1$ objects into $n$ slots
```
```ad-example
In any group of 367 people there must be at least two with the same birthday
```

## Pigeonhole Principle as Resolution
We can formulate the Pigeonhole Principle as a conjunction of formulas.

Choose propositional variables $p_{ij}$ for $1\leq 1 \leq n+1, 1 \leq j \leq n$.
$p_{ij}$ is true iff the ith pigeon goes into the jth slot

Construct clauses for:
1. Each pigeon $i$, $1 \leq i \leq n +1$, goes into some slot $k, 1 \leq k \leq n$:
 $$p_{i1} \lor p_{i2}... \lor p_{in}, \text{for  $1 \leq i \leq n +1$}$$
 2. Distinct pigeons $i\neq j, 1 \leq i, j \leq n+1$ cannot go into the same slot $k$:
 3. $$p_{ik} \to \neq p_{jk} |=| \neg p_{ik} \lor \neg p_{jk}, \text{for  $1 \leq i \le j \leq n +1, 1 \leq k \leq n$}$$


Any truth valuation that satifies the conditions (the ocnjunction of all the above clauses) would map $n+1$ pigeons one-to-one into $n$ slows.

Of course, this is impossible by the pigeonhole principle.

```ad-example
What is  the pigeonhole $P_2$ (3 pigeons and 2 slots) stated as a resolution problem?
- Every pigeon in at least one slot: $$p_{11}\lor p_{12},\ p_{21}\lor p_{22},\ p_{31}\lor p_{32}$$
- No two pigeons per slot: 

```
Relate: [[]]