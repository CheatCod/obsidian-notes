---
alias: []
---

# Polymorphism
## Object slicing
❌✔️✅📗
~~~c
class Book { // Super class
 	string title, author;
	int length;
public:
	Book(...);
	bool isHeavy() const;
}

class Text:public book { // derived/sub subclass
	string topic;
public:
	Text(...);
}

class Comic:public book { // derived/sub class
	string hero;
public:
	Comic(...);
}
~~~
From the previous example, we see that since `Comic` inherited from `Book`, a comic is technically a book, thus we can do ```Book b = c```. 

Since `Comic` is a bigger object (has an additional `string hero` field), we can't fit all the data to `Book`. So what we've performed is called **object slicing**, thus `b` only sees the `Book` portion of `c`.

If we use pointers, 
```c
Book *pb = pc;
```
Although no more slicing occurs, the compiler still treat pb as a book, so will call `Book`'s  method instead of `Comic`

The same object is behaving differently based on the type of the pointer used to access it.

To make a `Comic` behave like a Comic regardless of the type of pointer used to refer to it?

# `virtual, override`

If we declare the method as `virtual`

```c
class Book { // Super class
 	string title, author;
	int length;
public:
	Book(...);
	virtual bool isHeavy() const;
}
```
This allows us to have a collection of `Comic`, `Book` and `Text`:

```c
Book *myLibrary[20];
for (int i = 0; i < 20; ++i) {
	cout < myLibrary[i] -> isHeavy() << endl;
}
```

This code will use `Book::isHeavy`, `Comic::isHeavy` and `Text::isHeavy` respectively for each type of the objects that is pointed by each pointer in the array.

This code accommodates multiple types under one single abstraction - ***Polymorphism***

```ad-note
When we override a method, the method signature must match **excatly**. So if the method is const in the parent, it must be const in the child too.

We can use the keyword `override` into the signatures of the overriden methods to let compiler catch these kinds of errors. It **does not** change any behavior.
~~~c
class Text:public book { // derived/sub subclass
	string topic;
public:
	Text(...);
	bool isHeavy() const override;
}
~~~
```

```ad-warning
**DO NOT** use an array of objects polymorphically!

This could case data to be misaligned.

Always use an array of pointers 

**ALWAYS** make destructors virtual, even if they do nothing
```

We can stop a class from being inherited by using the `final` specifier
Relate: [[]]