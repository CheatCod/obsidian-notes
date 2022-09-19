# Generating Series

## Ideas of Generating Series
- Encode some counting problem to the coefficient of a power series
- Use some combinatorics to get a formula for the series
- Use some algebra to determine the coefficient of the series

## Definition of generating series:

Let $A$ be a set and let $\omega : A \to \mathbb{N}$ be a function
Interpretation: for any $a \in A$, $\omega(a)$ is the weight of $a$, ie, it's size

E.g:

Take $A = \mathbb{N}^t$ be the set of multisets with $t$ types of element.

for $\mu = (m_1, m_2,...,m_t) \in \mathbb{N}^t$, its weight is 
$\omega(\mu) = |\mu| = m_1 + m_2 ... + m_t$

Let $A_n$ be the set of objects of weight $n$ 

Note $A = A_0 \cup A_1...$ is an infinite disjoint union

For each $n \in \mathbb{N}$ we want to determine $|A_n|$.

This only makes sense if its finite, so we assume each of these sets $A_n$ is finite 


> [!def] Weight Function
> A function $\omega : A \to \mathbb{N}$ is a **weight function**
> iff for all $n \in \mathbb{N}: A_n$ is finite

> [!def] Generating Series
> Let $A$ be a set with a weight function $\omega : A \to \mathbb{N}$
> The generating series of $A$ with respect to $\omega$ is 
> $$\Phi_A(x) = \sum_{a \in A} x^{\omega(a)}$$

> [!info]  Proposition:
> let $A$ be a set with a weight function, then for all $n \in \mathbb{N}$, 
> $$[x^n]\Phi_A(x) = |A_n|$$
> >[!proof]
> $$\begin{align*}
> [x^n]\Phi_A(x) &= [x^n]\sum_{a \in A} x^{\omega(a)} = [x^n] \sum_{k=0}^\inf \sum_{a \in A_k}x^{\omega(a)}
> \end{align*}$$








