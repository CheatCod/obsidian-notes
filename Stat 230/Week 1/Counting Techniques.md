---
alias: []
---
# Counting Techniques
❌✔️✅📗

## Useful Combinatorial Symbols

- $n^{(k)}$, $n$ to $k$ factors, number of arrangements of $n$ different element taken $k$ at a time.
```ad-example
How many permutations of 26 letters are possible if we take 10 letters at a time without replacement?
$$26^{10}$$
```

- $n!$, $n$ factorial, number of arrangements (permutations) of $n$ different elements taken $n$ at a time
- $n^k$, number of arrangements of $n$ elements taken $k$ at a time allowing repeats

```ad-def
$$
{n \choose k} = \frac{n^{(k)}}{k!}
$$

$n$ choose $k$
```

If $n$ is a positive integer and $k$ is a non-negative integer such that $k \le n$ then ${n \choose k}$ is the number of subsets(combinations) of $k$ elements which may be selected from a set containing $n$ elements.

```ad-def
$${n \choose n_1,n_2,...n_k} = \frac{n!}{n_1!n_2!..n_k!}$$

is the number of arrangements(permutations) of $n$ elements of $k$ different types, there being $n_1$ number of the first type, $n_2$ number of second type...etc
```

```ad-example
Suppose the letters of "STROUMBOULOOULOS" are arranged at random to form a string.

Find the probabilities of 
1. the string being "STROUMBOULOOULOS"

The total number of permutation is $\frac{17!}{2!5!2!3!}$, so the probability is $$\frac{1}{\frac{17!}{2!5!2!3!}}$$

2. The name starts with a T

With the first letter fixed to T, there are $\frac{16!}{2!5!2!3!}$ permutations of the remaining letters.
Therefore the probability is $$\frac{{\frac{16!}{2!5!2!3!}}}{\frac{17!}{2!5!2!3!}}$$

We can also argue that since there are 17 letters and T is only one of them, the probability is $\frac{1}{17}$.

3. The name ends with an O.
There are 17 choices for the letter which 5 are O's
$\frac{5}{17}$

4. The O's occur together in the name.

We can imagine the O's forming a single block of letters "OOOOO"
With this symbol plus the remaining 12 non-Os there are 13 symbols in total, 
$\frac{13!}{2!2!3!}$
Therefore the probability is 
$$
\frac{\frac{13!}{2!2!3!}}{\frac{17!}{2!5!2!3!}}
$$
```

Permutation: order DOES matter 
Combination: order DOES NOT matter, we are counting the number of distinct subsets 
Relate: [[]]