# Recursive Decomposition

Like a regex, but usnig letters on both sides of the equation

E.g.

$$L = \epsilon \cup (0 \cup 1) L$$

leads to 

$$L(x) = 1 + (2x)L(x)$$

E.g.

$$S = \set{\epsilon, 01,0011,000111,..}$$
can not be produced by a regex, since
$$S = \bigcup_{j=0}^\infty 0^j1^j$$
doesn't follow the pattern
$$R^* = \bigcup_{k=0}^\infty R ^k$$

## Excluded Substrings

Excluded substring $k$, 

Recall sets $A$ and $B$,

Always have 

$$\epsilon \cup A(0 \cup 1) = A \cup B$$
for any $k$ we get another equation.

E.g. (4.23)

$$W = \epsilon \cup 0 w1w$$