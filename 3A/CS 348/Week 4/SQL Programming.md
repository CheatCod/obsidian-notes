# SQL Programming

## Pros and Cons of SQL
- Very high level, possible to optimize
- Not intended for general purpose computation

## Solutions:
- Augument SQL with construct from general-purpose programming languages
	- E.g., SQL/PSM


SQL operates on *a set of records at a time*, whereas a typical low level general purpose language operate on one record at a time

Solution: **cursor**
- Open a table, Get next, Close

