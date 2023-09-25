# Translating entity sets

- An entity set translates direcly to a table
	- Attributes $\to$ columns
	- Key attributes $\to$ key columns

# Translating weak entity sets

Need to include the “borrowed” key attributes

Watch out for arributes name conflicts

# Translating relationship sets

- Keys of connecte entity sets $\to$ columns
- Attributes of relationship set (if any) $\to$ columns
- Multipliciy of the relationship set determines the key of the table

![[Pasted image 20221006170516.png]]

- If we can deduce the general cardinality constraint (0,1) for a componenet entity set $E$, then take the primary key attributes for $E$
- Otherwise, choose primary key attributes of each componenets entity 

# Translate double diamonds (supporting relationship sets)


# Translating subclasses & ISA

**Entity-in-all-superclasses** approach:

- An entity is represented in the table for each subclass to which it belongs
- A table only includes the attributes directly attached to the corresponding entity set, plus the inherited key

**All-entities-in-one-table**:

