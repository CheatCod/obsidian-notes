---
alias: [quantifier]
---
# Universal Quantifier
❌✔️✅📗

Let $A(u)$ represents a formla, and let *u* be a variable.

$\forall x A(x)$ indicates that $A(u)$ is true for all possible values of $u$ in the [[First Order Logic#Domain|Domain]]

The $\forall x$ is called universal quantifier, and $A(x)$ is called the **scope** of the quantifier 

The variable $x$ is said to be **bound** by the quantifier
```ad-note
The meaning of universal quantifier **changes** with the domain

The quantifier and the bound variable that follows have to be treated as a unit, and this unit acts somehwat like a unary connective
```

```ad-example
**Everyone needs a break**:

Let the domain $D$ be the set of all people.

Define $B(u)$ to mean *u needs a break*.
$$
\begin{equation}
  B(u) =
    \begin{cases}
      1 & \text{if $u$ needs a break}\\
      0 & \text{otherwise}\\

    \end{cases}       
\end{equation}
$$

$\forall x B(x)$
```

# Existential Quantifier
Let $A(u)$ represents a formla, and let *u* be a variable.

$\exists x A(x)$ indicates that $A(u)$ is true for at least one value of $u$ in the [[First Order Logic#Domain|Domain]]

The $\forall x$ is called the existential quantifier, and $A(x)$ is called the **scope** of the quantifier 

## Negation:
for all, not


# Bound and free variables

The variable appearing in the quantifier is said to be 	**bound**, any variable that is not bound is said to be **free**

The bound variables are local to the scope of the quantifier, which means that if serveral quantifiers use the same bound variable for quantification, all these variables are local to their scope and are all distinct.

The quantifiers are given a **higher precedence** than all binary connectives:
Let $P(u)$ be "$u$ is living, and $Q(u)$ be $u$ is dead.
We write $\forall x(P(u) \lor Q(x))$

Whereas $forall xP(x) \lor Q(x)$ means "Everything is living, or $x$ is dead"

Since the bound variable is just a placeholder, thus it can be replaced by any other symbol not appearing elsewhere in the formula.
# Quantifying over a subset 

Sometimes we'd need quantification over a *subset* of the domain.

If the domain is the set of all animals, 

## Restricting the universal quantifier
```ad-example	
To say "All dogs are mammals", it's equivalence to "If $u$ is a dog, then $u$ is a mammal", which leads to the formula 

$$\forall x(dog(x) \to mammal(x)))$$
```


## Restricting the existential quantifier
```ad-example	
To say "Some dogs are brown", it's equivalence to saying that some animals are dogs that are brown. "$u$ is a dog and $u$ is brown", which leads to the formula 

$$\forall x(dog(x)\land brown(x))$$
```

# Nested Quantifier

We can nest quantifier, but they don't commute

a good analogy is nest loop


Relate: [[]]