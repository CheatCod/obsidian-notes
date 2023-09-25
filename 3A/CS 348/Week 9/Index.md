**Dense:** one index entry for each search key value
- One entry may "point" to multiple records
**Sparse:** one index entry for each block
- Records must be clustered according to the search key

**Primary index:**
- Created for the primary key of the table
**Secondary index**:
- Created for the UNIQUE keys

# ISAM (Index Sequential Access Method)

- If an index is too big, we can put another (sparse) index on top of it.

Problem: may become unbalanced after deletion and insertion

# B+ Tree

- Balanced
- Very good for range queries
- Dynamic 
	- If a node becomes too full, must split into 2 nodes
- Performance similar to a balance binary tree


Use ISAM if the data isn't going to change a lot


# B Tree

- B+ tree does not store ??? in non leaf node??
- Prefer a flatter tree than a tall tree


# Other approaches:
- Hash-based indexes 
- ...


# Multi-attribute indices
- Index on several attributes of the same relation.
	- CREATE INDEX NameIndex ON User(LastName, FirstName)
	- ^^ Tuple are organized first by Lastname, tuples with a common surname are then organized by first name
- This index would be helpful for these queries:
	- SELECT * FROM User WHERE Lastname = 'Smith'
	- SELECT * FROM User WHERE Lastname = 'Smith' and Firstname = 'John'
- This index will **not be useful** for this query:
	- SELECT * FROM User WHERE Firstname  = 'John'

# Index-only Plan
- Some queries can be answered by only looking at the index structure
- For examples:
	- SELECT COUNT(\*) FROM User WHERE pop > 0.8 and Firstname = 'Bob';
	- Non-clustering index on (firstname, pop)
- A non-clustered index contain alll the columns needed to answer the query without having to access the tuple in the base relation
	- Avoid one disk IO per tuple
	- The index is much smaller 

# Physical Design Guidelines for Indices
- Don't index unless the performance increase outweighs the update overhead
- Attributes mentioned in WHERE clauses are candidates for index search keys
- Multi-attribute search keys should be considered when
- Choose indexes that benefit as many queries as possible
- Each relation can have at most one clustering scheme, therefore choose it wisely
	- Target important queries that would benefit the most
		- Range queries benefit the most from clustering
	- A mult-attribute inde that enables an index-only plan does not benefit from being clustered 

# Case Study:
1. Build index over age, build clustering index because it benefits range queries 
2. Build index over name, build a non-clustering since 
3. Build index over User(age, pop), uses index-only plan
4. Build index over starting date, build clustering index
5. a
An index can be clustered and unclustered at the same time
