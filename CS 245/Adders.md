---
alias: [Adder]
---
# Adders
[[Logic circuits]] can be used to carry out addition of two positive integer from their binary expansion.

- First we build a circuit that can be used to find x + y when x and y are each a single bit (0 or 1)

- The *input* to our circuit will be two bits, x and y

- The *output* will consist of two bits, s and c, where s is the sum bit and c is the carry bit

## Half Adder

- The circuit is a *multiple output circuit*
- It has two input bits, x and y, and it adds up producing two outputs: *s* (the sum bit) and *c* (the carry bit)
- The circuit we are desining is called the **half-adder** since it adds two bits, without considering a carry from the previous addition 

**Truth table:**

| x   | y   | s   | c   |
| --- | --- | --- | --- |
| 1   | 1   | 0   | 1   |
| 1   | 0   | 1   | 0   |
| 0   | 1   | 1   | 0   |
| 0   | 0   | 0   | 0   |

- From the truth table we see that $c = xy$ and $s = x\bar{y} + \bar{x}y$
- We use the fact that $x\bar{y}+\bar{x}y = (x+y)\bar{(xy)}$ to simplify the logic gate

![[Pasted image 20211013102153.png]]

## The Full Adder
The *full-adder* is used to add two numbers $(x_nx_{n-1}...x_0)$ and $(y_ny_{n-1}...y_0)$, in their *binary representation*, $x_1, y_1 \in \{0, 1\}$ for all $0 \leq i \leq n$.

| $x_n$ | $x_{n-1}$ | ... | $x$ | ... | $x_0$ | +   |
| ----- | --------- | --- | --- | --- | ----- | --- |
| $y_n$ | $y_{n-1}$ | ... | $y$ | ... | $y_0$ |     |
|       |           | ... | $s$   | ... |       |     |

The addition proceeds from right to left. To add $x_0, y_0$ one uses a [[#half adder]], Subsequently, at each step, a full-adder takes three bits as input ($x, y$, and the carry bit $c_i$ from the previous addition), and it adds them up (in binary), producting two outputs: the sum bit $s$, and the next carry bit $c_{i+1}$,

**Truth table**:
Input: Bits $x, y$ and the carry bit $c_1$
Output: The sum bit $s$ and the carry bit $c_{i+1}$

| $x$ | $y$ | $c_i$ |     | $s$ | $c_{i_1}$ |
| --- | --- | ----- | --- | --- | --------- |
| 1   | 1   | 1     |     | 1   | 1         |
| 1   | 1   | 0     |     | 0   | 1         |
| 1   | 0   | 1     |     | 0   | 1         |
| 1   | 0   | 0     |     | 1   | 0         |
| 0   | 1   | 1     |     | 0   | 1         |
| 0   | 1   | 0     |     | 1   | 0         |
| 0   | 0   | 1     |     | 1   | 0         |
| 0   | 0   | 0     |     | 0   | 0          |

- Obtain the following formulas in DNF
$$s=xyc_i+x\bar{y}\bar{c_i}+\bar{x}y\bar{c_i}+\bar{x}\bar{y}c_i$$

$$c_{i+1} = xyc_i+xy\bar{c_i}+x\bar{y}c_i+\bar{x}yc_i$$

Instead of building the full-adder circuit from AND, OR and NOT gates, we can use half-adders to produce the desire outputs:
![[Pasted image 20211013135058.png]]

## Adding Three-bit Integers

We can combine half adders and full adders to produce the sum of a three-bit integer.
$$(x_2x_1x_0)_2 + (y_2y_1y_0)_2 = (s_3s_2s_1s_0)_2$$

```ad-note
$s_3$, the highest-order bit in the sum is given by the carry $c_2$.
```
![[Pasted image 20211013144700.png]]