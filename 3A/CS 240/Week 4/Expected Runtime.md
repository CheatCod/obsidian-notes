...




## QuickSort Analysis

Define $T(n)$ to be the run-time for quicksort1 in a size-n array

- $T(n)$ depends again on the pivot-index $i$
- If we know $i: T(n) = \Theta(n) + T(i) + T(n-i-1)$
- **Worse-case analysis**: $i=0$ or $n-1$ always, then
$$T(n)= \begin{cases}T(n-1)+c n, & n \geq 2 \\ c, & n=1\end{cases}$$
- **Best-case**: $i = floor(n/2)$ or $ceil(n/2)$ always, then

$$T(n)= \begin{cases}T(floor(n/2)) + T(ceil(n/2))+c n, & n \geq 2 \\ c, & n=1\end{cases}$$

Prove that QuickSort best case is in $\Theta(n \log n)$

Prove $O$:

1. Consider instances with the pivot index roughtly in the middle
2. Then the size of the array is roughly cut in half each time. Thus each recursioin tree has height $\log n$
3. Each recursion needs a partition ($O(n))$
4. The upperbound is thus $O(n\log n )$

Prove $\Omega$
1. Consider the recursion tree
2. On the first level down, we still have $n-1$ items left (unknown split)
3. Second level down, $n-3$ items remain
4. Third level down, $n-7$ items remain
5. On level $l$, *at least\** $n-(2^l -1)$ items remain, pslit into $2^l$ subarray
6. Doing paritition takes at least $n-2^l+1$ key comparisons in total
7. Let $l = floor(\log n) -1$, then $2^l \le \frac{n}{2} \to n - 2^l + 1 \ge \frac{n}{2} + 1$
8. Therefore at least $n-2^l + 1 \ge \frac{n}{2} + 1$ comparison per level

*If the subtree is not as deep, we stop extracting pivot there*


**Average Case Analysis**

Let $T(n)$ to be the average case runtime for quicksort
![[Pasted image 20220929152330.png]]


Proof $O(n \log n)$
1. We simplify the bound provided on the slide 
$$\begin{align*}
T(n) &\le cn + \frac{1}{n} \sum_{i=0}^{n-1} (T(i) + T(n-i-1)) \\
&= cn +\frac{2}{n} \sum_{i=0}^{n-1} T(i) \tag{match pairs of sums} \\
&= cn + \frac{2}{n} \sum_{i=2}^{n-1} T(i) \tag{T(0) = T(1) = 0} \\
\end{align*}$$
2. Now claim that, the recursive relation $T(*), T(0) = T(1) = 0$ and $T(n) \le cn + \frac{2}{n} \sum_{i=2}^{n-1} T(i)$ satisify 

$$T(n) \le 2cn \ln n = 1.39cn \log (n) \in O(n \log n)$$

3. Prove $T(n) \le 2cn\ln n$ by induction on $n$
Base case (n = 1): $T(1) = 0$, and $2c(1) \ln(1) = 0$

Inductive ($n \ge 1$):

IH: for all $i < n$, $T(i) \le 2i \ln i$

$$\begin{align*}
T(n) &\le cn + \frac{2}{n} \sum_{i=2}^{n-1} T(i) \\
&\le cn + \frac{2}{n} \sum_{i=2}^{n-1} 2ci \ln i \tag{IH} \\
&= cn + \frac{4c}{n} \sum_{i=2}^{n-1} i \ln i \\ 
\end{align*}$$

Note that $f(x) = x \ln x$ is monotonically increasing for $x \ge 1$


Hence the sum $\sum_{i=2}^{n=1} i \ln i$ is bounded above by $\int_2^n x \ln x dx$


Compute the integral:

Intetgration by parts, $u  = \ln x, v = \frac{x^2}{2}$

...

This shows $T(n) \in O(n \log n)$

This bound must be tight, we already showed the best case $\in \Omega(n \log n)$
