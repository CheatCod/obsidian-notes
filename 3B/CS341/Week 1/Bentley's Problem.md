
Divide and Conquer

Divide an array into two equally-sized parts.

Our solution must either be entirely in the left part, or entirely in the right part, or it must be crossing the partition boundary.

If its entirely on the left or right then the solution is trivial

To find the maximum subarray going over the middle partition

We have converted the problem to find an arbitrary subarray ($O(n^2)$)to a prefix or a subfix or an array

## Bits model

- Use the biggest element of the array
- 