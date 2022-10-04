# Database Design

- Step 1 : Understand the real-world domain being modeled
	- Specify it using a *database design model*
- Step 2: translate specification to the data model of DBMS

## ORM
- Automatic object-relational mappers are made popular by rapid web development framework
- Still need designer discretion in all but simple cases
- Each language/library has its own syntax for creating schema and for querying modifying data
	- Quicks and limitations cause portability problems
	- Not neccessarily easier to learn than SQL

## Entity-relationship (E/R) model

- Historically and still very popular 
- Primarily a **design model**
- Represented by E/R diagrams 

## E/R basics
- Entity: a "thing", like an object
- Entity set: a collection of things of the same type
- Relationship: an association among entities
- Relationship set: a set of relationships of the same type 
- Attributes: properties of entities or relationships

Ex.
![[Pasted image 20221004085704.png]]

A key of an entity set is represented by underlining all attributes in the key

- There could be multiple relationship sets between the same entity set
		- Ex. Users isMemberOf Groups, Users Likes Group
- In a relationship set, each relationship is *uniquely* idenfied by the entities it connects

![[Pasted image 20221004090747.png]]

## Multiplicity of relationships

Let $E$ and $F$ be entity sets

- **Many-many**: each entity in $E$ is related to 0 or more entities in $F$ and vice versa
![[Pasted image 20221004091200.png]]
- **Many-one**: each entity in $E$ to 0 or 1 entity in $F$, but each entity in $F$ is related to 0 or more in $E$
![[Pasted image 20221004091209.png]]
- **One-one**  each entity in $R$ is related to 0 or 1 entity in $F$ and vice versa
![[Pasted image 20221004091221.png]]

## General cardinality constraints

- General cardinality constraints determine lower and upper bound on the number of relationships of a given relationship
![[Pasted image 20221004091409.png]]

## Role in relationships
- an entity set may participate more than once in a relationship set
	- May need to label edges to distinguish roles

## Weak entity sets
- If entity $E$ 's existence depend on entity $F$, then
	- F is the **dominant entity**
	- $E$ is the **subordinate entity**
	- Example: Rooms inside Buildings are partly identified by builder's name
- Weak entity set: containing subordinate entities 
	- Drawn as a double rectangle 
	- The relationship sets are called **supporting relationship sets**

> [!note]
> A weak entity set must have a *many-to-one* or *one-to-one* relationship to a distinct entity set

![[Pasted image 20221004092400.png]]


- Attributes of weak entity sets only form key relative to a given dominant entity → **discriminator**

> [!def] 
> **Discriminator**: set of attributes that distinguish subordinate entities of the set for a particular dominant entity 

## ISA Relationships
- Similar to the idea of subclasses in OO
- A specialization, ewer entities, an dpossibly more properties
- Ex. paid uers are users but they also get avatars
![[Pasted image 20221004093219.png]]
(direction of triangle is important!!)

## Other extensions to E/R modesl
- Generalizations: serveral entity sets can be abstracted by a more general entit set
	- Ex. a vehicle abstract the notion of truck and car
![[Pasted image 20221004093448.png]]

