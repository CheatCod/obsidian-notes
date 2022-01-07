---
alias: []
---
# Syntax of FOL
❌✔️✅📗

Recall from prpropositional logic that formulas are recursively built from atoms with the 5 formation rules.

Since FOL is more fine-grained and complicated, so is its syntax.

$\mathcal{L}$ is the language of FOL.
It consists of expressions using the following basic symbols:
**Logic symbols:**
- connectives: $\neg, \lor, \land, \to$
- free variable symbols: $u, v, w,u_1$ (global variables)
- bound variable symbols: $x,y,z,x_1$ (local variable for loops)
- quantifiers: $\forall, \exists$
- punctuation symbols: $()$
**Non-logical symbols:**
- individual symbols: $a,b,c,a_1...$ (constant symbols)
- relation symbols, $F,G,H,F_1$ (predicate symbols) [[First Order Logic#Relation]]
- function symbols: $f,g,h,f_1$) (returns a non-tf value)

```ad-note
$\mathcal{L}$ may or may not be associated to a mathematical structure, as it is not a single language, One is free to choose the meaning of individuals, relation and functions 
```

## Terms
"Term" is used to refer either an individual or a variable. 
A term is anything that can be used in place of an individual.
```ad-def
$Term(\mathcal{L})$ is the smallest class of expressions of $\mathcal{L}$ closed under the following formation rules:
1. Every individual symbol $a$ is a term in $Term(\mathcal{L})$
2. Every free variable symbol $u$ is a term in $Term(\mathcal{L})$
3. If $t_1...t_n, n\le1$ are terms in $Term(\mathcal{L})$, and $f$ is an n-ary function symbol, then $f(t_1...t_n)$ is a term in $Term(\mathcal{L})$
```
```ad-example
**FOOL of elementary number theory:**
- Equality relation: Yes
- Relation symbols: <
- Individual (constant) symbol: The symbol 0
- One 1-place function symbol: s (successor)
- Two 2-place function symbols: +, x

The expressions $+(u, 0), s(s(0))$ are terms
```
## Atomic formulas 
An atomic formula is the simplest formula expression a proposition, which takes on a value of true/false

```ad-def
An expression of $\mathcal{l}$ is an atom in $Atom(\mathcal{L})$ iff it is one of the following two forms:
1. $F(t_1,t_2,...t_n), n\ge1$, where $F$ is an n-ary relation symbol and $t_1...t_n$ are terms in $Term(\mathcal{L})$
2. $\approx (t_1, t_2)$ 
```

## Formulas
Formulas are built recursively from the atoms under formation rules
```ad-def
$Form(\mathcal{L})$, the set of formulas of $\mathcal{L}$, is the smallest class of expressions of $\mathcal{L}$ closed under the following formation rules:
1. Every atom in $Atom(\mathcal{L})$ is a formula
2. If $A$ is a formula then $(\neg A)$ is a formula
3. $(A \land B), (A \lor B), (A \to B), (A \leftrightarrow B )$ are formulas
4. If $A(u)$ is a formula, where $u$ is a free variable, and $x$ is a variable not occurring in $A(u)$, then $\forall x A(x), \exists x A(x)$ are formulas. 
```

Relate: [[]]r