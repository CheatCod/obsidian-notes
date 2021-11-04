---
alias: []
---
# Inheritance and copy/move operations
❌✔️✅📗

If no constructor is provided, the default behavior of the constructor would be to call its superclass's constructor, and copy the reset of the fields of the subclass field fields-by-fields.

If we want to mimic this behavior with our own implementation:
```ad-example
~~~c
// Copy ctor:
Text::Text(const Text &other): Book{other}, topic{other.topic} {}

// Copy assignment:
Text &Text::operator=(const Text &other) {
    Book::operator=(other);
    topic = other.topic;
    return *this;
}

// Move ctor:
Text::Text(Text &&other): Book{std::move(other)}, topic{std::move(other.topic)} {}

// Move assignment:
Text &Text::operator=(Text &&other) {
    Book::operator=(std::move(other));
    topic = std::move(other.topic);
    return *this;
}
~~~
```

Note, we called one of `Book`'s constructor/operator first, and then continuing the implementation.
```ad-obs
Even though in the move ctors the `other` "points" at an rvalue, `other` itself is an lvalue, therefore we must use `move()` to force it to be treated as an rvalue. If we don't do so, the copy version of the operations would run.
```

## Partial Assignment

If we were to use pointers to be base class for assignment of an object to another, for ex.

```ad-example
~~~c
Text t1{...}, t2{...}
Book *pb1 = &t1, *pb2 =&t2;

// Copy assign to what pb1 points at to be whatever pb2 points at
*pb1 = *pb2;
~~~
```

Since the assignment op is non-virtual, the base class's implementation is called.
`Book:operator=` is called.

This is called a **partial assignment**, as only the `Book`'s component is copied.

**Potential solution #1**. Make the `operator=` virtual:
```c
class Book {
    . . .
  public:
    virtual Book &operator=(const Book &other);
    virtual Book &operator=(Book &&other);
 };

class Text: public Book {
    . . .
  public:
    Text &operator=(const Book &other) override;
    Text &operator=(Book &&other) override;
 };
```

We can now assign a `Text` object to another one using two pointers of type `Book`.

However, this introduces **mixed assignment**, as now we can assign a `Book` into a `Text`, or a `Comic` into a `Text` and vice-versa. Also, we can't correctly implement the operator since `Book` does not have the fields for `Text`.

**Good solution:** All superclasses should be abstract. To implement this we should restructure the hierarchy. 

![[Pasted image 20211104022821.png]]


Relate: [[]]