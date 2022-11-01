
A Functional Dependency (FD) has the form $X \to Y$, where $X$ and $Y$ are sets of attributes in a relation $R$

# Closure of FD Sets

A set of FDs $F$ *logically implies* a FD $X \to Y$ if $X \to Y$ holds in *all instance* of $R$ that satisfy $F$

The *closure* of a FD set $F$ (denoted $F^+$) is the set of all FDs that are logically implied by $F$


# Attribute Closure

The closure of attributes $Z$ in a relation $R$ (denoted $Z^+$) with respect to a set of FDs, $F$, is the set of all attributes $\set{A_1, A_2,...}$ functionally determined by $Z$

Algorithm for computing the closure:

1. Start with closure $Z$
2. If $X \to Y$ is in $F$ and $X$ is already in the closure, then also add $Y$ to the closure
3. Repeat until no new attributes can be added


## Using Attribute Closure

Given a relation $R$ and set of FD's $F$,

Does another FD $X \to Y$ follow from $F$?
-  Compute $X^+$ with respect to $F$
- If $Y \subseteq X^+$, then $X \to Y$ follows from $F$

Is $K$ a key of $R$
- Compute $K^+$ with respect to $F$
- if $K^+$ contains all attributes of $R$, $K$ is a super key