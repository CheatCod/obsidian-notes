# Partial Fractions

$$c_n = [x^n] \frac{1-2x+6x^2}{1-3x+4x^3}$$

Factor the denominator:

$1-3x+4x^3$ vanishes when $x = -1$, so $x+1$ is a factor

Polynomial division: $4x^2 - 4x + 1$

So $1-3x + 4x^3 = (1+x)(1-2x)^2$ 

Partial Fractions applys

$$\frac{1-2x+6x^2}{1-3x+4x^3} = \frac{A}{1+x} + \frac{B}{1-2x} + \frac{C}{(1-2x)^2}$$
for some $A, B, C \in \mathbb{C}$

How to find $A,B,C$ ?

- Clear denominator in fraction to get polynomials in $x$ in both sides
- Substitute convenient values for $x$ to get equation relating $A,B,C$
- Solve the system of linear equations

$$1-2x+6x^2 = A(1-2x)^2 + B(1+x)(1-2x) + C(1+x)$$

Sub $x=1$:

$$\begin{align*}
1 + 2 + 6 &= A*3^2 + B *0 + C* 0 \\
9 &= 9A
\end{align*}$$

Sub $x = \frac{1}{2}$

$$\begin{align*}
1 - 1 + 6/4 = A \cdot 0 + B \cdot 0 + C \cdot \frac{3}{2}
\end{align*}$$

We know the two unknowns, solve for $B$
..

--- 
General form for partial fractions

Each inverse root $\lambda$ of the denominator ocurs with some multiplicity $d \ge 1$

and contributes

$$\frac{k_1}{1-\lambda x} + \frac{k_2}{(1-\lambda x)^2} + ... + \frac{k_d}{(1-\lambda x)^d}$$

