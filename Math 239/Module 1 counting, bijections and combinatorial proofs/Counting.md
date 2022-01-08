# Subsets

Given an n-element set $S$, how many subsets $X$ does $S$ have?

We can make a binary choice for each element in $S$, whether it's in the subset $X$ or not.

This translates to choosing an element out of the set $\set{IN, OUT}$ $n$ times, which is $2^n$

```ad-example
for $S = \set{a,b,c}$, it has $2^3 = 8$ subsets

$$X = \set{a,b,c} \leftrightarrow (IN, IN, OUT)$$
$$X = \emptyset \leftrightarrow (OUT, OUT,OUT)$$

```
```ad-note
This idea of mapping objects of one type uniquely to an object of another type is very important
```

# Lists

```ad-def
Lists are sets but **ordered**
```
How many ways are there to put the elements of an $n$-element set $S$ in order?

If $|S| = n$, to construct a list $(S_1, S_2...S_n)$ of $S$, we have

$n$ choices for $S_1$
$n-1$ choices for $S_2$
...
$1$ choices for $S_n$

Thus this gives $n!$ possible lists.

# Partial Lists
A length-$k$ partial list of a set $S$ is a $k$-tuple $(S_1, S_2...S_k)$ of **distinct** elements of $S$

If $|S| = n$, to construct a partial list of length $k$ $(S_1, S_2...S_k)$ of $S$, we have

$n$ choices for $S_1$
$n-1$ choices for $S_2$
...
$n-k+1$ choices for $S_k$

```ad-note
- If $k > n$, then 0
- $n(n-1)...(n-k+1) = \frac{n(n-1)(n-2)...1}{(n-k)(n-k-1)...1} = \frac{n!}{(n-k)!}$, if $n \le k$
- It is important that our method of constructing partial lists via choices constructs each partial list **only once**
```

# k-element subsets

Let $n \choose k$ denote the number of k-element subsets of an n-element set $S$, or "n choose k"

```ad-note
Some properties:
- ${n \choose 0}  = 1 = {n \choose n}$ for all $n \ge 0$
- ${n \choose 1} = n$ for all $n$
- ${n \choose k} = 0$ if $k>n$
```

```ad-thm
<u>Theorem 1.5:</u>
$${n \choose k} = \frac{n!}{k!(n-k)!}$$ for all $0 \le k \le n$
```

```ad-proof
Suppose that $|S| = n$, thus there are $\frac{n!}{(n-k)!}$ partial lists of $S$ if length $k$ 

Another way to describe a length-k partial list of $S$ is to choose
- a k-element subset $X$ of $S$ AND
- a list of the elements of $X$

Thus the number of length-k partial lists of $S$ is
$$\text{(\# of k-element subsets of s) (\# of lists of a k-element set)}$$
which is ${n \choose k} \cdot k!$

Since ${n \choose k} \cdot k!$ and $\frac{n!}{(n-k)!}$ are both counting the same thing, they must be equal.
```

```ad-example
<u>Example 1.6</u>

$${n \choose 0} + {n \choose 1} ... {n \choose n} = 2^n$$
```

~~~ad-proof
RHS $2^n$ is the number of subsets of an n-element set $S$
LHS is the number of ways to choose a single subset of $S$

${n \choose 0}$ 0-element subsets OR
${n \choose 1}$ 1-element subsets
...

~~~

```ad-example
<u>Example 1.7:</u>

If $k, n \ge 1$, then ${n \choose k} = {n - 1 \choose k} + {n-1 \choose k-1}$


```



