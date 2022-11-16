
# Logical Plan

- Nodes are logical operator (often relational algebra operator)
- There are many equivalent logical plans

# Physical (execution) Plan

- A complex query may involve multiple tables and various query processing algorithms 
- A physical plan for a query tells the DBMS query processor how to execute the query 
	- A tree of physical plan operators
	- Each operator implements a query processing algorithm 

## How to pick the "best" physical plan
- Often the goal is not getting the optimum plan, but instead avoiding the horrible ones


## Cost Estimation
- We need to estimate the size of intermediate result

## Selections with equality predicates
- $Q: \sigma_{A =v}R$
- Suppose the following information is available
	- Size of $R: |R|$
	- Number of distinct $A$ values in $R : |\pi_AR|$
- Assumptions:
	- Values of $A$ are uniformly distributed in $R$
	- Values of $v$ in $Q$ are uniformly distributed over all $R.A$ values
- $|Q| \approx \frac{|R|}{|\pi_AR|}$ 

## Range Predicates
- $Q: \sigma_{A \ge v}R$
- Not enough information
	- Just pick, say, $|Q| = |R| \cdot \frac{1}{3}$
- With more info:
	- Largest $R.A$ value: $high(R.A)$
	- Smallest $R.A$ value: $low(R.A)$
	- $|Q| \approx |R| \cdot \frac{high(R.A) - v}{high(R.A) - low(R.A)}$
	- In practice: sometimes use the **second highest and lowest values**

## Two-way equi-join

- $Q:R(A,B) \bowtie S(A,C)$
  