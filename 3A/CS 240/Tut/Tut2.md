# Tut2, Sept 26


## 1.

## 2.

Idea: start at priority 0, assign each element the priority that is 1 more than the current max prioirty.

Stack using heap:

```python
S.push(v):

if S is empty 
	create item x with key 0, value v
	S.insert(x)
else 
	cur_max = S.root.key
	create item x with key (cur_max+1), value v
	S.insert(x)
```

Time complexity:

$O \log(n)$ - only insert takes non constant time


```python
S.pop(v)
return S.deleteMax().value
```
Time complexity:

$O \log(n)$

