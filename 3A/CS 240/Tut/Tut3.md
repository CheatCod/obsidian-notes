# Tut3

1.

Best case: $O(n)$

Expected:

```python
shuffle(A) <- Probability_of_running = 1
check if A is sorted <- Probability_of_running = 1
	return <- Probability_of_running = 1/n! 
return <- MonkeySort(A) <- 1 - 1/n!
```

$$\begin{align*}
T^{exp}n &\le c_1n \cdot 1 + c_2n \cdot n + \frac{1}{n!} + T^{exp}(1 - \frac{1}{n!}) \tag{Big-O}  \\
&\le c_1n \cdot 1 + c_2n \cdot n + \frac{1}{n!} + T^{exp} - T^{exp}\frac{1}{n!} \tag{Big-O}  \\
\end{align*}$$

2.

```python
MergeSort(A[n-n^e, ..., n-1])
Merge(A[0, ..., n-n^e - 1], A[n-n^e, ..., n-1])
```

For MergeSort:

3.



General Idea for average run time:

1. Calculate instance size
2. Find a relationship between instances and runtime
3. Find number of instances that have the same runtime
4. Simplify 
