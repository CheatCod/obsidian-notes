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







