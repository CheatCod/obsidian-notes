...


# Independent Hash Functions

- Some hashing methods require two hash functions $h_0, h_1$
- These hash functions should be *independent* in the sense that the random variable $P(h_0(k)=i)$ and $P(h_1(k) = j)$ are indepedent
- Modular hash functions are often dependent
- Use multiplicative method for second hash function
