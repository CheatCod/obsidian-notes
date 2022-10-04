# Non-Comparison-Based sorting

- Assume key are numbers in base $R$ ($R$: radix)
	- $R = 2, 10, 128. 256$ are the most common
- Assume all keys have the same number $m$ of digits
	- Can achieve after padding with leading 0s

## Single digit Bucket Sort

Make 1 bucket per digit, 3 digit $\to$ 3 buckets. 