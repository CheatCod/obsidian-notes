# Triggers
- Does something when something is updated
- Similar to referential constraint:
![[Pasted image 20220927090032.png]]

> [!info] 
> A **trigger** is an event-condition-action(ECA) rule
> 
> When **event** occurs, test **condition**; if condition is satisified, execute **action**


## Trigger options
### events:
- **INSERT ON** table; **DELETE ON** table; **UPDATE** (OF column) **ON** table
![[Pasted image 20220927091116.png]]

### timings:
- Action can be executed:
	- **AFTER** or **BEFORE** triggering event 
	- **INSTEAD OF**
![[Pasted image 20220927091130.png]]

## Granularity
- **FOR EACH ROW** modified
- **FOR EACH STATEMENT** that performs modification 

![[Pasted image 20220927091329.png]]

## Transition variables/tables

- **OLD ROW**: the modified row before the triggering event
- **NEW ROW**: the modified row after the triggering event
- **OLD TABLE**: a hypothetical read-only table containing all the rows to be modified before the triggering event
- **NEW TABLE**: a hypothetical table containing all modified rows after the triggering event

## Statement vs row-level triggers
- Simple row-level triggers are easier to implement 
	- Statement-level triggers require significant amount of state to be maintained in OLD TABLE and NEW TABLE
- Certain triggers are only possible at statement level, e.g.
	- Aggregate condition on multiple modified rows

## System issues
- Recursive firing of triggers can get into an infinite loop
- Interaction with constraints
	- When to check if a triggering event violates constraints?
		- After a **BEFORE** trigger
		- Before an **AFTER** trigger

# Views

- A view is like a "virtual" table
	- Defined by a query, which describes how to compute the view contents on the fly
	- Stored by DBMS instead of view contents
	- Can be used in queries just like regular table
- Like an intermediate variable to store queries 
![[Pasted image 20220927093717.png]]

## Why use views?
- Hide complexity from users
- Hide data from users
- Logical data independence

## Modifying views
- Makes sense if we want users to really see views as tables
- Goal