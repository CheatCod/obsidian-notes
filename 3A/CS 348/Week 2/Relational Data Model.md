# Relational Data Model

A data

# Schema vs. Instance

## Schema (metadata)
- specifies the logical structure of data
- defined at setup time, rarely changes

## Instance
- represents the data content
- always conforms to the schema


# Integrity Constraints
A set of rules the database instances should follow.
> [!example]- 
> age cannot be negative
> uid should be unique
> uid in Member must refer to a row in user

An instance is only valid if it satisfies all the integrity constraints.

## Types of Integrity Constraints

- Tuple-level
	- Domain restriction, attribute comparison
	- E.g. age cannot be negative
- Relation-level
	- Key constraints
	- E.g. uid should be unique in the User relation
- Database-level
	- Referential integrity
	- E.g. uid must refer to a row in User with the same id

# Key (candidate)

> [!def] 
> **Candidate Key**: A set of attributes $K$ for a relation $R$ if
> 1. In no instance of $R$ will two different tuples agree on all attributes of $K$
> 	- that is, $K$ can serve as a "*tuple identifier*"
> 2. No proper subset of $K$ satisfies the above condition
> 	- that is, $K$ is minimal

> [!example] 
> User (uid, name, age, pop)
> - uid is a key of the user
> - age is not a key (not an identifier)
> - {uid, name} is not a key (not minimal), but a superkey

Key declarations are part of the schema.

**A key can contain multiple attributes:**
![[Pasted image 20220913091021.png]]
- a student can be in multiple groups, and a group can contain multiple student
- must use {uid, gid}

**A relation can have multiple keys**
- Address (street_address, city, state, zip)
- Key 1: {street_address, city, state}
- Key 2: {street_address, zip}

Both are minimal.

> [!def] Primary Key
>A designated candidate key in the schema declaration

## Use of keys

