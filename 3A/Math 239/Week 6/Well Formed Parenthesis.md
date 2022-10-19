How many ways can one write $n$ opening parentheses ( and $n$ closing parentheses ) in such a way that the parentheses match as usualy

Use 0 for "("
Use 1 for ")"

A WSP always beings with a "(" which matches with exactly one ")" later on

$$\sigma = 0 a1b$$
if $\sigma$ is a WFPs then $a, b$ are also WFPs, the converse also holds.

$W \subseteq \set{0,1}^*$ is the set of WFPs, we have described a bijection:

$$W \leftrightarrow 0 W1W \cup \set{\epsilon}$$
Recursive decomposition:

$$W = \epsilon \cup 0 W 1W$$
Enumerate w.r.t length:

$$\begin{align*}
W(x) &= \Phi_w(x) = \sum_{\sigma \in W} x^{l(\sigma)} \\
W(x) &= 1 + xW(x)xW(x) \\
0 &= 1 - W(x) + x^2W(x)^2
\end{align*}$$
By the quadratic formula.

$$W(x) = \frac{1+-\sqrt{1-4x^2}}{2x^2}$$

Enumerate WFPs by half the length

Let $z = x^2$

The exponent of $z$ is half the length.

$w_n = |W_n| = [z^n] \frac{1+-\sqrt{1-4z}}{z}$


## General Binomial Series