# SQL

...

## INSERT
- Insert one row
	- User 789 joins Dead Putting Society:
	![[Pasted image 20220927084204.png]]

## DELETE
- Delete **everything** from a table 
```sql
DELETE FROM Member;
```
- Delete according to a **WHERE** condition:
```sql
DELETE FROM Member WHERE uid=789 AND gid='DPS'
```

## UPDATE
..



## Referential Integrity
- Referenced columns(s) must be **PRIMARY KEY**

### Enforcing Referential Integrity
- Reject Insert or Update a member row that contains invalid referential key

- Delete or update a User row whose uid is referenced by some member row:
	- Reject or
	- cascade delete


## Tuple and attribute based CHECKS
- Associated with a single table
- Only checked when a tuple/attribute is inserted/updated
	- Reject if condition evaluates to FALSE
- Examples:
```sql
CREATE TABLE User(...
age INTEGER CHECK(age IS NULL OR age > 0),
...);
```

