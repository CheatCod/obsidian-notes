
Given two points $(x_1, y_1)$ and $(x_2,y_2)$ we say that .. dominates if $x_1 > x_2$ and $y_1 > y_2$

Input: a set $S$ of $n$ points with distinct x values

Output: all non-dominated points in $S$, all points in $S$ that are not dominated by any point in $S$

Divide and Conquer solution:

Suppose we pre-sort the points in $S$ with respect to their $x$ coordinates.

Decomposition:

Let the first $n/2$ points be denoted $S_1$ and let the last $n/2$ points be denoted $S_2$
![[Pasted image 20230914131456.png]]

Conquer:

Recursively solve the subproblem for $S_1$, $S_2$

Observe that **no point in $S_1$ dominates a point in $S_2$**

![[Pasted image 20230914131844.png]]
Therefore we only need to eliminate the points in $S_1$ that are dominated by a point in $S_2$, this can be done in $O(n)$.




