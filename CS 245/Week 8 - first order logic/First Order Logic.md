---
alias: [predicate logic, predicate calculus, elementary logic, restricted predicate calculus]
---
# First Order Logic
❌✔️✅📗
**Some alterntive names:**
predicate logic, predicate calculus, elementary logic, restricted predicate calculus

Why do we need First Order Logic?
For all and there exists?

## Elements of first order logic
First order logic is used to describe mathematical theories (number theory, group theory, etc). Such a theory comprises certain conceps specific to the structure/theory 
- A domain of objects, called individuals (ex. the set of natural numbers)
- Designted individuals (zero)
- Relations (equality)
- Functions(successor function, addition, multiplication)
Additionally, to make statements about individuals in the domain we use **first order logic concepts**:
-	Variables ranging over the domain
-	Logical connectives
-	Quantifiers(for all, there exists)
-	Punctuation (brackets)
### Domain:
```ad-example

1. Joan is Paul's mother.
2. Joan is Mary's mother.
3. Any two persons having the same mother are siblings.
---
4. Paul and Mary are siblings
```

This is ambiguous as there are many *Paul*s and *Mary*s in this world, thus we introduce the concept of **Domain**

```ad-def
The **Domain** (or **universe of discourse**) is the collection of all persons, ideas, symbols, data structures... etc, that affect the logical argument under consideration.


```

**The truth of a statement is depedent on the domain selected**
For ex, the statement "*there is a smallest number*" is true in the domain of natural numbers, but false in the domain of ints.
 
```ad-note
 - The elements of the domain are called *individuals* or *objects* or **
- We always assume that every domain must be **non-empty**, that is, it contains at least one individual. Hence, the set of all natural numbers less than 0 does **not** constitute a domain. 
- To refer to an object, we use **identifiers**, for ex, when we refer a group of humans, we use their names as identifiers.
```

### Relations
Generally, relations make statements about individuals
```ad-example
Marry and Paul **are siblings**
Joan **is the mother of** Mary
Socrates **is human**
**The sum of** 2 and 3 is 5 
```
In the statement "May and Paul are siblings", the arugment list is given by Mary and Paul, and the relation is described by the phrase "are siblings"

In each of these statements, there is a list of individuals, called **argument list**, with phrases which describe certain *relation* between the individuals in the list

To express "Joan is the mother of Mary", we can write `Mother(Joan, Mary)` or `M(j, m)`

Note that the **order of arugments is important**

### Arity
The number of elements in the argument list of a relation is called the **arity** of the relation
For ex, `mother(Joan, Mary)` has arity 2
The arity of a relationship is fixed. So if the arity differs, the two relations are different

A relationship with arity *n* is called an *n*-ary relation symbol.
A one-place relationship is called a **property**: `Human(Socrates), Mortal(Socrates)` are properties

### 	Variables

If we want to have an argument of a relation with all the individuals, we can use **variables**, which range over the domain.

Ex. `Human(u)` may denote "*u* is a human", `mother(u, w)` may denote "*u* is the mother of *w*"

## Atomic formulas

Atomic formulas in FOL is a relation name, followed by an argument list in parenthese

Atomic formulas take true/false values 

Atomic formulas can be combined by logical connectives.
```ad-example
$$
\begin{equation}
  Human(u) =
    \begin{cases}
      1 & \text{if $u$ is human}\\
      0 & \text{otherwise}\\

    \end{cases}       
\end{equation}
$$
```
Relate: [[]]