
Input: two $k$-bit positive integers $X$ and $Y$
- With binary representations:
$$X = [X[k-1, .., Y[0]]$$
$$X = [Y[k-1, .., Y[0]]$$
Output: The $2k$-bit positive integer 

Brute force:

- One row per digit of $Y$
- For each row copy the $k$ bits of $X$
- Add the $k$ rows together
	- $\Theta(k)$ binary additions of $\Theta(k)$ bit numbers
- TOtal runtime is $\Theta(k^2)$ 

Divide-and-Conquer:

- Divide into four $k/2$ bit multiplication subproblems
- Conquer with recursive calls
- Combine with $k$-bit addition and bit shifting

In this case, a primitive DnC algorithm is the same runtime as brute force

To get speedup, must reduce the number of subproblems or their size, think binary search.

## Karatsuba's Algorithm

Key takeaway: reduce 4 multiplications to 3

