---
alias: []
---
# Asymptotic Notation
❌✔️✅📗

## Order Notation

### O-Notation
```ad-def
$f(n) \in O(g(n))$ if there exist constants $c>0$ and $n_0 > 0$ such that $|f(n) \le c |g(n)|$ for all $n \ge n_0$
```
```ad-example
for $f(n) = 75n + 500$ and $g(n) = 5n^2$, choose $c=1,n_0=20$
```
```ad-obs
Be careful with the definitions of order notation.

$g(n)$ does NOT always dominates $f(n)$.

Ex.
$(n+1)^5 \in n^5$, but $n^5$ never dominates $(n+1)^5$, clearly we need a value of $c > 1$
```
In this case we see that
$$n + 1 \le 2n $$
$$(n + 1)^5 \le (2n)^5 = 2^5n^5 $$
thus $c=32n^5$ would suffice for all $n \ge 1$

---

From "First principles" means explicity find $c$ and $n_0$,

Sometimes we can just prove they exists with the following properties:

Assumes $f(n) \ge 0, g(n) \ge 0, \forall n \ge 0$

1. $af(n) \in O(f(n))$ for any constants $a > 0$
2. If $f(n) \in O(g(n))$ and $g(n) \in O(h(n))$, then $f(n) \in O(h(n))$
3. $max(f(n), g(n)) \in O(f(n) + g(n))$
4. $a_0 + a_1n + ... + a_kn^k \in O(n^k), a_i > 0$
5. $n^x \in O(a^n), x > 0, a > 1$
e.g. $n^{100000} \in O(1.0000001^n)$
6. $(log n)^x \in O(n^y), x, y > 0$
e.g. $(log n)^100000000 \in O(n^{0.00000000001})$

## Asymptotic Lower Bound

By order notation, we have $2n^2 + 3n + 11 \in O(n^2)$ but also $O(n^{10})$

We would really like a tight asymptotic bound.


Relate: [[]]