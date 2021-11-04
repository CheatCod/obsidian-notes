---
alias: []
---


# UML
❌✔️✅📗

The Unified Modeling Language, known as UML for short, is a visual modeling language that lets people design and document a software system. The standard for the latest version can be found at: https://www.omg.org/spec/UML/About-UML/

## Classes and Methods

```plantuml
!theme materia-outline
skinparam classAttributeIconSize 0

class a {
	+x : integer
	-y : integer
	+getx()
}

```

`+` means public
`-` means private 

## Composition
Embedding one object within another is called **composition**

```ad-example
~~~c
class Vec{
	int x,y;
public:
	Vec(int x, int y) : x{x}, y{y} {}
}

class Basis {
	Vec v1, v2;
	Basis() : v1{1,0}, v2{0,1} {}
}
~~~

```

In this case, a `Basis` object *owns* a `Vec` object.

Generally, if `A` owns `B`, then:
- `B` has no identity outside of `A` (no independent existence) (The 2 Vecs in basis has no existence outside of Basis)
- If `A` is destroyed, `B` is destroyed
- If `A` is copied, `B` is copied

```plantuml
!theme materia-outline
skinparam classAttributeIconSize 0

class Vec {
} 

class Basis {
}

Basis "2" *--|> Vec
```

## Aggregation

`A` "has-a" relationship

If `A` "has-a" `B` then typically:
- `B` exists apart from its association `A`
- If `A` is destroyed then B lives on
- If `A` is copied, `B` is not (shallow copy)
	- Copies of `A` share the same `B`
```ad-example
Parts in a catalogue for a car
~~~plantuml
!theme materia-outline
skinparam classAttributeIconSize 0

class Part{
}
class Catalogue{}

Catalogue "1...*" o-->Part
~~~

The "1..*" is read as "a catalogue can have 1 to many Parts"
```

## Specialization ([[Inheritance]])

"is-a" 
A rectangle is a shape

```plantuml
!theme materia-outline
skinparam classAttributeIconSize 0

class Book{}

class Text{}

class Comic{}

Book <|-- Comic
Book <|-- Text
```

## Abstract classes 
italicize the name

Relate: [[]]