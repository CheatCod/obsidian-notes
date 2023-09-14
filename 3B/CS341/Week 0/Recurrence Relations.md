
Techniques to solve recurrence relations:

## Recursion Tree


## Guess and Check

- Expand out the recurrence relationship by substitute terms
- Identify patterns and guess what happens in the limit
- "Unroll" the recursion

Note: needs to prove that the guess

Can also directly guess a complexity, i.e. quadratic

If so then it should have the form:

$an^2 + bn + c$ for some unknown constant $a,b,c$

So you can carry the unknowns into the proof, the unknowns complete the proof

**Note:** need to take care of floor and ceilings, since the +1 and -1 happens at every level of the recurrence.

If can't assume power of 2, we can do analysis on the closest power of 2 smaller and power of 2 bigger and find a $\Theta$ bound that way.


## Master Theorem

Master theorem provides a formula for solving many recurrence relations

Simplified version:

Consider recurrence:

$$T(1)=d, T(n) = aT(\frac{n}{b}) + \Theta(n^y)$$
where $a \ge 1, b \ge 2$ and $n$ is a power of $b$ (i.e., $n=b^j$ for some integer $j$)

Simplified Master Theorem
$$
T(n) \in \begin{cases}\Theta\left(n^x\right) & \text { if } y<x \\ \Theta\left(n^x \log n\right) & \text { if } y=x \\ \Theta\left(n^y\right) & \text { if } y>x\end{cases}
$$
where  $x = \log_b{a}$
