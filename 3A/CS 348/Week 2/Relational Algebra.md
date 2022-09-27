# Relational Algebra

A language for querying relational data based on *operators*

Core operators:
	todo!

## Selection

- Input: a table $R$
- Notation: $\sigma_p R$ ($p$ is the predicate)
- Purpose: filter row according to some criteria
- Output: same columns as $R$, but only rows of $R$ that satisify $p$

> [!example] 
> Users with popularity higher than 0.5
$\sigma_{pop>0.5} User$
![[Pasted image 20220913093259.png]]

**You must be able to evaluate the condition over each single row of the input table**

Ex. $\sigma_{pop \ge \text{every pop in User}} User$ 
*not allowed ^^^^^^^

## Projection

- Input: a table $R$
- Notation: $\pi_{L}R$, $L$ is a list of columns in $R$
- Purpose: output chosen columns
- Output: the same rows, but only the columns in $L$
![[Pasted image 20220913094416.png]]


## Cross product

- Input: two tables $R$ an $S$
- Notation: $R \times S$
- Purpose: join rows from two tables
![[Pasted image 20220913094402.png]]

Ordering of column is unimportant as far as the contents are concerned.
![[Pasted image 20220927014524.png]]

## Derived operator: join

- Input: two tables $R$ and $S$
- Notation: $R \bowtie_p S$
	- $p$ is called the *join condition (predicate)*
- Purpose: relate rows from two tables according to some criteria
- Output: for each row $r \in R$ and $s \in S$, output a row $rs$ if $r$ and $s$ satisfy $p$
- Shorthand for $\sigma_p(R \times S)$


## Derived operator: natural join

- Input: two tables $R$ and $S$
- Notation: $R \bowtie S$
- Purpose: relate rows from two tables, and
	- Enforce equality between identically named columns
	- Eliminate one copy of identically named columns
- Shorthand for $\pi_L (R \bowtie_P S)$, where
	- $p$ equates each pair of columns common to $R$ and $S$
	- $L$ is the union of the column names from $R$ and $S$ (with duplicate columns removed)

## Core operator: Union

- Input: two tables $R$ and $S$
- Notation: $R \cup S$
	- $R$ and $S$ must have identical schema
- Output:
	- Has the same schema as $R$ and $S$
	- Contains all rows in $R$ and all rows in $S$, with duplicate rows removed
![[Pasted image 20220927020128.png]]

## Core operator: Difference

- Input: two tables $R$ and $S$
- Notation: $R - S$
	- $R$ and $S$ must have identical schema
- Output:
	- Has the same schema as $R$ and $S$
	- Contains all rows in $R$ that are not in $S$
![[Pasted image 20220927020212.png]]

## Derived operator 3: Intersection