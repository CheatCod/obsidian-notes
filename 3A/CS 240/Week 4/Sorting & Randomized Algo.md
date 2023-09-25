# Selection 

> [!info] 
> The **selection problem**: Given an array $A$ of $n$ umbers, and $0 \le k \le n$, find the element that would be at position $k$ of the sorted array.
> Special case: median finding = Selection with $k = floor(\frac{n}{2})$

![[Pasted image 20220927144119.png]]

Selection can be done with heaps in time $\Theta(n + k \log n)$
Median finding with this takes time $\Theta(n \log n)$

Can we do selection in linear time?

The *quick-select* algorithm can

## quick-select

The quick select and related algorithm quick-sort rely on two subroutines.

- *choose-pivot(A)*: Return an index $p$ in $A$, we will use the pivot-value to rearrange the array.
	- Simplest idea: selected the right most element in an array
- *partition(A, p)*: Rearrange $A$ and return **pivot-index** $i$ so that 
	- the pivot value is in $A[i]$
	- everything bigger is to the right
	- everything smaller is to the left


### Efficient In-Place partition (Hoare)

Keep swapping wrongly placed indexes 

![[Pasted image 20220927150238.png]]

```python
quick-select1(A, k)
A: array of size n, k: integer s.t. 0 ≤ k < n
1. p ← choose-pivot1(A)
2. i ← partition(A, p)
3. if i = k then
4. return A[i]
5. else if i > k then
6. return quick-select1(A[0, 1, . . . , i − 1], k)
7. else if i < k then
8. return quick-select1(A[i + 1, i + 2, . . . , n − 1], k − i − 1)

```

### Analysis of quick-select1

Define $T(n)$ to be the run time for selecting from size-n array, presuming we use choose-pivot1$(A)$

- $T(n)$ depends on the pivot-index $i$
- If we know $i : T(n) = \Theta(n) + \max(T(i), T(n-i-1))$ <-- why max?? Worse case?

**Worse-case analysis**: $i=0$ or $n-1$ always:
$$
T(n)= \begin{cases}T(n-1)+c n, & n \geq 2 \\ c, & n=1\end{cases}
$$

for some constant $c > 0 \to \Theta(n^2)$

> [!proof] 
> Prove $T(n) \in O(n)$
> First, claim that, for all $n \ge 1, T(n) \le \frac{cn(n+1)}{2} \in O(n^2)$ <- chosen arbitrary
> Proof by induction on $n$
> Base case: $n=1$
> 	$\frac{c(1)(1+1)}{2} = c$
> Induction: $n>1$ 
> IH: $T(n-1) \le \frac{c(n-1)(n)}{2}$
> Then we have
> $$\begin{align*}
> T(n) &= T(n-1) + n \\
> & \le \frac{c(n-1)n}{2} + cn \\
> &= \frac{c}{2} ((n+1)n + 2n) \\
> &= \frac{c}{2} (n^2 + n) 
> \end{align*}$$
> 
> Worse case $T(n) \in \Omega(n^2)$
> If $A$ is sorted, and we use $k=0$, thten the right hand sub-array always has size $n-1$
> Hence a lower bound for worst-case runtime is for some $d > 0$
> $[d(n-1) + cn] + [d(n-2) + c(n-1)] + ... + [d+c \cdot 2] + [0 + c\cdot 1]$

 **Best-case**: first pivot value is the desired element(last value), no recursive call. Hence we choose it as our pivot, so that after the first partition call, we have $i=l$, and we immediately stop.

Parition is $\Theta(n)$

**Average-case**:

- How to characterize input of size $n$?
- Simplifying assumption: All input numbers are distinct.

> [!obs] 
> The actual numbers do not matter, only their *relative order*
> quick-select acts the same on inputs [1,2,3] and [4,5,6] the same

- Characterize input via **sorting permutation**

**Analysis:**

- Fix one $0 \le i \le n -1$, there are $(n-1)!$ permutations for which the pivot-index is $i$

$$\begin{align*}
\begin{aligned}
T(n) &=\frac{1}{n !} \sum_{\text {l:size }(I)=n} \text { running time for instance } I \\
&=\frac{1}{n !} \sum_{i=0}^{n-1} \sum_{\substack{\text { l:size }(I)=n \\
\text { has pivot-index } i}} \text { running time for instance } I \\
& \leq \frac{1}{n !} \sum_{i=0}^{n-1}(n-1) ! \quad(c \cdot n+\max \{T(i), T(n-i-1)\}) \\
&=c \cdot n+\frac{1}{n} \sum_{i=0}^{n-1} \max \{T(i), T(n-i-1)\}
\end{aligned}
\end{align*}$$

Claim that $T(n) \in \Theta(n)$

Proof:

Prove that $T(n) \in O(n)$:

Prove by induction that $T(n) \le 8cn$

Base case $n = 1$;

$T(1) = c, c \le 8c$

Inductive: n > 1:

- For ease of writing, assume $n$ is divisble by 4
- Call an index $i \in [0,..., n-1\}$ good if $i \in [\frac{1}{4}n, \frac{1}{4}n\}$ and bad otherwise (half the indices are good)
- If $i$ is good, then $\max(i, n-i-1) \le \frac{3}{4}n$
- If $i$ is bad, then weak upper bound is $max(i, n-i-1) \le n$

 This gives the following upper bound:

$$\begin{align*}
T(n) &\le c \cdot n+\frac{1}{n} \sum_{i=0}^{n-1} \max \{T(i), T(n-i-1)\} \\
&\le c \cdot n+\frac{1}{n} \sum_{i=0}^{n-1} \max \{8ci, 8c(n-i-1\} \\
&\le c \cdot n+\frac{1}{n} (\sum_{i \text{ good}} 8 \cdot \frac{3}{4}n + \sum_{i \text{ bad}} 8 cn) \\
&\le c \cdot n+\frac{1}{n} (\text{\# of good indices }\cdot 8 \cdot \frac{3}{4}n + \text{\# of good indices } \cdot 8 cn) \\
&\le ... \\
&\le 8cn
\end{align*}$$

Omega bound:

This bound is tight, because we perform at least one call to parition, which takes $\Omega(n)$

Remark:

The proof for $O(n)$ gives some intuition about why $T(n)$ is linear.

- half the indices are good
- the bad indices can be controlled, possibly by different choices that we made here, in the end, vanishingly small


