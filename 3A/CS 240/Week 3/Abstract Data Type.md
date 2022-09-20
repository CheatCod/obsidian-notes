# ADT

## Stack:

2 operations:
- push
- pop

Items are removed in LIFO (last-in, first out) order.
Items enter the stak at the top and removed at the top.

## Queue

2 operations:
- enqueue
- dequeue
Items are removed in FIFO (first in first out) order

## Priority Queue

An ADT consisting of a collection of items each with a **priority** with 2 operations:

- insert: insert an item tagged with a priority
- deleteMax: removing the item of the highest priority

We can use priority queue to sort:

Insert all the element and pop them out one by one

```python
PQ-Sort(A[0..n − 1])
	initialize PQ to an empty priority queue
		for k ← 0 to n − 1 do
	PQ.insert(A[k])
		for k ← n − 1 down to 0 do
	A[k] ← PQ.deleteMax()
```

### Realizations for PQ

**Realization 1**: unsorted arrays:
- insert : $O(1)$
- deleteMax: $O(n)$

**Realization 2**: sorted arrays:
- insert: $O(n)$
- deleteMax: $O(1)$

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
3. 










