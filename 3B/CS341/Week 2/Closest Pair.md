
Input: set of $n$ 2d points

![[Pasted image 20230921130723.png]]


Find the closest pairs


DnC:

sort by x-axis and divide in half and solve the problem recursively

![[Pasted image 20230921130856.png]]

It is trivial to see that:

1. $(p, q)$ both in $L$
2. $(p,q)$ both in $R$
3. One of $(p,q)$ in $L$ and one of $(p, q)$ in $R$

Observe:

Let $\sigma = min(dist(pair_L),dist(pair_R))$

![[Pasted image 20230921131208.png]]

Then the pair lies in the above $2\sigma$ wide green stripe

Only search for points above you - that is ok, we will search through every point eventually

# Core idea:

1. Start from lowest $y$ valued point in the strip
2. search for $\sigma \times \sigma$ square point on the opposite side
3. Repeat 1, 2 for the next lowest y-valued point

Optimization:

- Instead of doing it for both $L$ and $L$, search a $2 \times \sigma \times \sigma$ rectangle each time