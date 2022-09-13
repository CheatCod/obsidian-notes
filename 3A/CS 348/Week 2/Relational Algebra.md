# Relational Algebra

A language for querying relational data based on *operators*

Core operators:
	todo!

## Selection

Input: a table $R$
Notation: $\sigma_p R$ ($p$ is the predicate)
Purpose: filter row according to some criteria
Output: same columns as $R$, but only rows of $R$ that satisify $p$

> [!example] 
> Users with popularity higher than 0.5
$\sigma_{pop>0.5} User$
![[Pasted image 20220913093259.png]]

**You must be able to evaluate the condition over each single row of the input table**

Ex. $\sigma_{pop \ge \text{every pop in User}} User$ 
*not allowed ^^^^^^^

## Projection

Input: a table $R$
Notation: $\pi_{L}R$, $L$ is a list of columns in $R$
Purpose: output chosen columns
Output: the same rows, but only the columns in $L$
![[Pasted image 20220913094416.png]]


## Cross product

Input: two tables $R$ an $S$
Notation: $R \times S$
Purpose: join rows from two tables
![[Pasted image 20220913094402.png]]

Ordering of column is unimportant as far as the contents are concerned

## Derived operator: join

## Derived operator: natural join
