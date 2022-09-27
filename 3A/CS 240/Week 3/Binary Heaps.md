# Binary Heap

## Heaps

A **binary heap** is a certain type of binary tree

Any binary tree with $n$ nodes has height at least 
$$\log(n+1) - 1 \in \Omega(\log n)$$
> [!proof] 
> Let $T$ be a binary tree, with $n(T)$ be its # of nodes, and $h(T)$ be its height.
> Rewrite the given condition:
> $$\begin{align*}
> h(T) &\ge \log (n(T) + 1) - 1 \\
> h(T) + 1 &\ge log (n(T) + 1) \\
> 2^{h(T) + 1} &\ge n(T) + 1 \\
> 2^{h(T) + 1} - 1 &\ge n(T)
> \end{align*}$$
> ^^^ prove this with structural induction on T
> **Base case**: (empty tree)
> $n(T)=0$
> $h(T) = 0$
> $2^1 - 1 \ge 0$
> 
> **Inductive case:**
> Assume we have binary trees $T_1, T_2$ such that
> $n(T_1) \le 2^{h(T_1) + 1} - 1$ and $n(T_2) \le 2^{h(T_2) + 1} - 1$ (IH)
> Construct $T = T_1 + T_2$
> then $n(T) = 1 + n(T_1) + n(T_2)$
> and $h(T) = 1 + max(h(T_1), h(T_2))$
> 
> So 
> $$\begin{align*}
> n(T) &= 1 + n(T_1) + n(T_2) \\
> &\le 1 + 2^{h(T_1) + 1} - 1 + 2^{h(T_2) + 1} - 1 \\
> &\le 2 \cdot max(2^{h(T_1) + 1} - 1, 2^{h(T_2) + 1} - 1) - 1 \\
> &= 2 \cdot 2^{(max (h(T_1)+1, h(T_2) + 1))} \\
> &= 2 \cdot 2^{(max (h(T_1)+1, h(T_2)) + 1)} \\
> &= 2 \cdot 2^{h(T)} - 1 \ tag{by def of h(T)} \\
> &= 2^{h(T) + 1} - 1
> \end{align*}$$

> [!def]  Heap
> A **heap** is a binary tree with the following properties
> -**Structure Property:** All the levels of a heap are completely filled, except (possibly) for the last level The filled in items are *left-justified*
> -**Heap Order Property**: for any node $i$, the key of the parent of $i$ is larger than or equal to the key of $i$

> [!info]  Lemma
> The height of a heap with $n$ nodes is $\Theta(\log n)$ 
> > [!proof] 
> > Let $h$ be the height of the heap, so we have levels $0,1,2,...,h$, and all levels except possible $h$ are full
> > 
> > Therefore we have $2^l$ nodes on each level $l, 0 \le l < h$, and at least one node on level $h$
> >
> > Thus:
> > 
>>$$\begin{align*}
 n &= \sum_{l=0}^h \tag{num of nodes on level l} \\
 &\le \sum_{l=0}^{h-1}2^l  + 1 \\
 &= \frac{1(2^h-1)}{2-1} + 1 \tag{Geo series} \\
 &= (2^h - 1) + 1 \\
 &= 2^h \\
>> \end{align*}$$
> > This established that $2^h \le n \iff h \le \log(n)$
> > From this it follows that $h \ in O(\log n)$
> > The earlier teorem esbalished that $h \in \Omega (\log n)$
> > 


Example heap: 
![[Pasted image 20220920152227.png]]

We shouldn't store a binary heap with a binary tree, why?

1. Array uses less space – no pointers
2. Maintaining the heap structure is more straight forward with an array

## Operations of Heaps

### Insert
- Place the new key at the first free leaf
- The heap-order property might be violated: perform a **fix-up**

```python
fixup(A,k)
k: an index corresponding to a node of the heap
while parent(k) exists and A[parent(k)] < A[k] 
	swap A[k] and A[parent(k)]
	k <- parent(k)
```


### deleteMax

- The maximum item of a heap is just the root node
- We replace root by the last leaf (last leaf is taken out)
- The heap-order property might be violated, perform a **fix-down**

```python
fixDown(A,n,k)
A: an arrray that stores a heap of size n
k: an index corresponding to a node of the heap
while k is not a leaf do
	# Find the child with the larger key
	j <- left child of k
	if (j is not last(n) and A[j+1] > A[j])
		j <- j + 1
	if A[k] >= A[j] break
	swap A[j] and A[k]
	k <- j
```



## Building Heaps with Fix-down

Given an array of $n$ items, build a heap containing all of them.

Using **fix-down**: ($\Theta(n))$

```python
heapify(A)
A: an array
	n ← A.size()
	for i ← parent(last(n)) downto 0 do
		fix-down(A, n, i)
```

Why is fix-down linear?

- The lower bound should be clear: for loop goes from $floor(\frac{n}{2})$ down to 0
- Upper bound needs mote work
- First observation: we can count the key-comparisons:
(# of other operations will be proportional to # of key comparison)
- let $h$ be the height of the heap
- Consider any node $v$, on level $l$, for $0 \le l \le h$
- *How many key comparisons are needed for fix-down(v)?*
	- 1st step: compare the 2 children of $v$, then compare $v$ to the larger child, $\le 2$ comparisons at 1st level
	- Then: (maybe) go down and repeat (interested in the worst case)
	- There are at most $(h-l)$ levels below $v$
	- Thus total # of key comparisons in `fix-down(v)` is at most $2(h-l)$
	- Total # of node on level $l: \le 2^l$
	- → All nodes on level $l$ contribute at most $2(h-l)2^l$ key comparisons during all their fix-downs
	- Thus
$$\begin{align*}
\text{\# key comp} &\le \sum_{l=0}^{h} 2(h-l)2^l\\
&=\sum_{l=0}^{h} l\cdot2^{h-l+1} \tag{sum in reverse order} \\
&=2^{h+1} \sum_{l=0}^{h}\frac{l}{2^l} \\
&\le2^{h+1} \sum_{l=0}^{\infty}\frac{l}{2^l} \\
\end{align*}$$
Claim that $\sum_{l=0}^{\infty}\frac{l}{2^l} = 2$

(proof):



Then the upper bound is $2^{h+2} = 2^h+4$, and the height of heap is $h \le \log (n)$, so the upper bound is $4n$



