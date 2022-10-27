# How to Analyze an Algo

- Count $\Theta(1)$ per line of code unless it does major work
- Sum over loops
- Use upper/lower bound early, prove $O$ bound and $\Omega$ bound seperately

```python
for i = 1 to n
	for j = i to n
		for k = i to j
			print("hello")
```

	Upper bound:

Lower bound:


# Handling Conditional

InsertionSort(A)

```python
for i = 1 to n-1 do
	j = i
	while j > 0 and A[j-1] > A[j] # between 0 and i times
		swap A[j] and A[j-1]
```

## Worst-case analysis
Assume the worst possible input:

$$T_{\mathcal{A}}(n)=\max \left\{T_{\mathcal{A}}(I): \operatorname{Size}(I)=n\right\} .$$
Worst for insertion sort: $O(n^2)$
Best case: $O(n)$

## Average-case analysis
Take the average over all possible input

$$T_{\mathcal{A}}^{a v g}(n)=\frac{1}{|\{I: \operatorname{Size}(I)=n\}|} \sum_{\{I: \operatorname{Size}(I)=n\}} T_{\mathcal{A}}(I)$$
Average case for insertion sort: $\Theta(n^2)$

# How to Compare 2 Algorithms 

Assume two algorithm $A_1, A_2$ have worse case runtime $f_1, f_2$
- if $f_1(n) \in o(f_2(n))$ usually think of $A_1$ as better. 
	Note: could be false for small n, could be false if worst-case is rarely achieved for $A_2$
- if $f_1(n) \in \Theta(f_2(n))$ then they appear equally as good on paper

# Recursive Algorithm

```python
mergeSort(A[0...n-1])
	if n = 1 then return
	m = floor(m/2)
	A[0..m] = mergeSort(A[0..m-1]) # size floor(n/2)
	A[m+1..n-1] = mergeSort(A[m..n-1]) # size ceil(n/2)
	A[0..n-1] = merge(A,m,n-1)
```

Facts:
if $n \ge 2$ then
floor(n/2), ceil(n/2) < n
floor(n/2) + ceil(n/2) = n

Analyze runtime:

merge take $\Theta(n)$ time

Recall: $T(n)$ is worse case

$$\begin{align*}
T(n) &= T(floor(n/2)) + T(ceil(n/2)) + \Theta(n) \\
&\approx T(n/2) + T(n/2) + \Theta(n) \\
&= 2T(n/2) + \Theta(n)
\end{align*}$$
Dont forget base case 
base case is an integer

