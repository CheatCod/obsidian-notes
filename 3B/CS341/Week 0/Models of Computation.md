
# Unit Cost Model

- Each variable (or array entry) is a word
- Words can contain unlimited bits
- Basic operations on words take $O(1)$ time
	- Read/write a word in $O(1)$
- **Space complexity** is the number of words used (excluding input)

Sometimes we care about word size. Supposed we want to limit the size of words, we must consider how many bits are needed to represent a number $n$

# Word Ram Model
- Care about size of words
- Words can contain $O(\log n)$ bits, where $n$ is the number of words in the input
	- Word size depends on input ize
	- Intuition: if the input is an array of $n$ words, a word is large enoug to store an array index

# Bit Complexity Model
- Everything stored is treated as an array of bits
- Size of a variable $x$ is the number of bits it need
	- It takes $O(\log v)$ bits to represent a value v
	- So if $v$ is stored in $x$, the size of $x$ must be $\Omega(\log v)$ bits