Date: September 19

# 2.

We want $\forall c \ge 0, \exists n$ s.t. $0\le c \cdot 2^{\sqrt{\log n}}$

We have $g(n) = 2^{\sqrt{\log n}}$
and $f(n) = n$

We can find an intermediate function:

(let epsilon = 1/2)
$$\begin{align*}
c \cdot 2^{\sqrt{\log n}} &< c \cdot n^{\epsilon} < n \\
c \cdot 2^{\sqrt{\log n}} &< c \cdot \sqrt{n} \\
\log(2^{\sqrt{\log n}} ) &< \log(\sqrt{n}) \\
\sqrt{\log n} &< \frac{1}{2}\log n \\
(\log n)^2 &< \frac{1}{2}(\log n) \\
2 &< \sqrt{\log n} \\
4 &< \log n \\
2^4 &< n\\
16 &< n
\end{align*}$$

# 3.

if $f(n) \in O\left(h_1(n)\right)$ and $g(n) \in \omega \left(h_2(n)\right)$, prove or disprove : $\frac{f(n)}{g(n)} \in O\left(\frac{h_1(n)}{h_2(n)}\right)$

By definition:

1. $\exists c_1,n_1 \ge 0$ s.t. $f(n) \le c_1(h_1(n)), \forall n \ge n_1$
2. $\forall c_1, \exists n_2 \ge 0$ s.t. $f(n) \le c_2(h_2(n)), \forall n \ge n_2$

divide (2):

3. $\frac{1}{g(n)} < \frac{1}{c_2(h_2n)}$

...

# 4.

```python
k ← 1
for i ← 1 to n do
	j ← 0
	while j ≤ n do
		j ← j + k
	end while
	k ← 2k
end for

```

let $t$ = # of iteration of the while loop

$j = k, 2k, 3k, ..., tk$
Terminates when $j > n$, or when $tk > n$

