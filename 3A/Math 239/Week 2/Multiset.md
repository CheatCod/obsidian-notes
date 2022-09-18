# Multiset

> [!def] 
> $M(n,t)$: set of all multiset of size $n$ with elements of $t$ types
> $$\mu = (m_1,m_2,...,m_t) \in \mathbb{N}^T$$
> such that $|\mu| = m_1 + m_2 ... + m_t = n$
> 

Recall $B(m,k)$, set of all k-element subsets of ${1,2,...,m}$

A bijection $f: B(n+t-1, t-1) \implies M(n,t)$

To define $f$, consider an arbitrary $s \in B(n+t-1, t-1)$

That is a subset $S = \{S_1, 2_2,...,,S_{t-1}\} \in \{1,2,3,...n+t-1\}$

Sort $S$ by increasing order.

For convenience, let $s_0 = 0,  s_t = n+t$

For each $1 \le i \le t$, let $m_1 = s_1 - s_{i-1} - 1$

Then $f(s) =(m_1, m_2, ..., m_t)$

For the inverse: $g : M(n,t) \implies B(n+t-1, t-1)$

Given $\mu = (m_1, m_2, ..., m_t)$

For $1 \le j \le t - 1$, let $q_j = m_1 + m_2 + ... + m_j + j$
Let $g(\mu) = \{q_1, q_2, ..., q_k-1\}$

Still need to check that this is a bijection:

1. $\forall s \in B(n+t-1, t-1), g(f(s)) = s$
2. $\forall \mu \in M(n,t), f(g(\mu)) = \mu$

Ex. check condition 1

Let $S \subseteq \{1,2,...,n+t-1\}$ with $|S| = t- 1$
sort $S$
Let $f(S) = \mu =(m_1,m_2,...,m_t)$
Let $g(\mu) = Q = \{q_1, q_2, ..., q_t\}$

Check that $Q=S$
Check that $\forall 1\le j \le t -1$ we have $q_j = s_j$


