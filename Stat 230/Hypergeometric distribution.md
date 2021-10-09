## <u>Theorem</u>

We have a collection of N objects which can be classified into two distinct types. r of type 1 and N -r of type 2.

Pick a sample of n < N objects at random **wthout replacement**
Let X be the number of type 1 in the sample

Then X has a hypergeometric distribution with **probability function**

$$\begin{align*}
f(x) &= \frac{\text{way to choose x type 1} \times \text{way to choose n -x type 2}}{\text {way to choose sample of n}} \\
&=\frac{{r \choose x}{N - r \choose n -x}}{{N \choose n}} 
\end{align*}$$

