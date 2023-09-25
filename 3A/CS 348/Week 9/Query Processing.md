# Table Scan
- Scan the table $R$ and process the query
- IO: $B(R)$
	- Trick for selection:
		- stop early if it is a lookup by key
- Memory requirement:  2 blocks
	- 1 for input, 1 for buffer output 
	- Increase memory does NOT improve IO
- Not counting the cost of writing the result out (same for any algorithm)
	- Maybe not needed – results maybe piped into another algorithm

# Nested-loop join

$R \bowtie_p S$

- For each block of $R$, and for each $r$ in t
