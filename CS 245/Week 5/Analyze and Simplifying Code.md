# Analyze and Simplifying Code

✅ 


We can use logic formuila simplification to find dead code and simplify it.

```ad-example
Consider the code fragment

```c
if (C1 or not C2) then 
	if (not (C2 and C3)) then 
	P1 
	else
		if (C2 and not C3) then 
			P2 
			else P3
else
	P4
```

**Analyze the code: **

We can write a truth table for the conditions for each of the if-statements. This truth table can then determine for each truth valuation $C_1,C_2,C_3$, which code $P_1,P_2,P_3,P_4$ is executed

**Prove that $P_2$ is dead code:**
Determine the propositional logic formula involving proposition symbols $C_1,C_2,C_3$ that would lead to the execution of $P_2$. If such a formula is a contradiction, then $P_2$ is dead code. Otherwise, it's not dead code

## Simplifying Code
We can calaim the following simplfied code is equivalent to the original:
```c
if (C1 and C2 and C3) then 
	P3 
else
	if (not C1 and C2) then 
		P4 
		else 
		P1
```
By showing that the formula with propositional symbols $C_1,C_2,C_3$ that leades to the execution of $P_1$ in the original code is logically equivalent to the formula that leads to the execution of $P_1$ in the simplfied code.