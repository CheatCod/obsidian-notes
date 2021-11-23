---
alias: []
---
# Turing Machine
❌✔️✅📗
```ad-def
A Turing Machine $T = (S, I, F, s_0)$ consists of:
- $S$ - a finite set of states
- $I$ - an input alphabet (finite set of symbols/letters) containing the blank symbol $B$
- $s_0 \in S$ - the start state
- $f : S \times I \to S \times I \times \set{L,R}$ - the transition function, where $L$ and $R$ stand for the direction "left" and "right"
```

## How a TM works 
- Each step the symbol $x$ is read. If the control unit is in state $s$ and the partial function is defined for the pair $(s, x)$, by $f(s,x) = (s',x',d)$, the control unit 
	1. Enters the state $s'$
	2. Writes the symbol $x'$ in the current cell, erasing $x$, and 
	3. Moves right one cell if $d = R$ or moves left one cell if $d = L$
- We write this step as a five-tuple $(s, x, s', x', d)$ and call it a **transition rule** of the TM
- If the transition function is undefined for the pair $(s, x)$, then the TM will **halt**
- The **initial position** $s_0$ of a TM is to be positioned over the leftmost noblank symbol on the tape. If the tape is all blank, the control head can be placed over any cell.

## Using TMs to accept/recognize languages
- An alphabet $\Sigma$ is a finite non-empty set of symbols, also called letters. Ex. $\Sigma = \set{0,1}$ is an alphabet
- By $\Sigma^*$ we denote the set of all possible strings written with letters from $\Sigma$, including the empty string $\lambda$
-  A **language** $L$ over $\Sigma$ is a subset of $\Sigma*$. If $\Sigma = \set{0,1}$ then $$L = \set{w \in \set{0,1}^{*} | w \text{ is a string with equally many 0s}}$$ is a language over $\Sigma$
```ad-def
A TM $T$ accepts a string $x \in V^{*}$, where $V\subseteq I$ if and only if $T$ starting in the initial position when $x$ is written on the tape, halts in a **final state**. $T$ is said to accept a language $L$ over $V$, if $x$ is accepted by $T$ iff $x$ belongs to $L$.

A string $x \in V^{*} \subseteq I^{*}$ is not accepted if either
- $T$ does not halt or
- $T$ halts in a non-final state
```
```ad-def
A **final state** of a TM $T = (S,I,f,s_0)$ is any state $s_f \in S$ that is not the first state in any five-tuple in the description of $T$ using five-tuples
```
Relate: [[]]