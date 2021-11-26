---
alias: []
---
# Multinomial Distribution
❌✔️✅📗

Suppose on each trial of an experienment there are $k$ possible outcomes, where $k \ge 3$

Recall from [[Bernouli trials]], where $k = 2$.

Experiements are repeated independently $n$ times with $k$ distinct types of outcome each time, and let the probabilities of these $k$ types be $p_1, p_2, ... p_k$ each times.

Count $$X_1 = \text{Number of times the 1st type occurs}$$
$$X_2 = \text{Number of times the 2nd type occurrs}$$
$$X_k = \text{Number of times the kth type occurrs}$$

Then $(X_1...X_k)$ has a multinomial distribution 

```ad-note
- $p_1 + p_2...p_k = 1$
- $X_1 + X_2 ... X_k = n$ 

```


# Multinomial Joint Probability Function
```ad-def
The join probability function of $(X_1,...X_k)$ for the multinomial is given by
$$\begin{align*}
P(X_1 = x_1, X_2 = x_2... X_k = x_k) =& f(x_1, x_2...x_k)\\
=& \frac{n !}{x_{1} ! x_{2} ! \cdots x_{k} !} p_{1}^{x_{1}} p_{2}^{x_{2}} \cdots p_{k}^{x_{k}}
\end{align*}$$

The restriction on the $x_is$ are $x_i=0,1,...n$ and $\Sigma_{i=1}^{k}x_i=n$
```

Generally, there are $\frac{n !}{x_{1} ! x_{2} ! \cdots x_{k} !}$ different arrangements, and each of these arrangements has probability $p_{1}^{x_{1}} p_{2}^{x_{2}}\cdots p_{k}^{x_{k}}$
Relate: [[]]