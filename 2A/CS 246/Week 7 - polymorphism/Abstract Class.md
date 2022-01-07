---
alias: []
---
# Abstract class
❌✔️✅📗

Sometimes, the implementation of logic is completely dependent on it's inherited classes, so we don't have anything to write in the implementation of a virtual method in a base class.
```ad-example
~~~c
class Student {
  protected:
    int numCourses;
  public:
    virtual int fees() const; // What should this do?
    . . .
};


// There are two kinds of student: regular and co-op.


class Regular: public Student {
  public:
    int fees() const override; // Computes regular student fees
};


class CoOp: public Student {
  public:
    int fees() const override; // Computes co-op student fees
};
~~~
```

In this case, we can make the `Student` an **abstract** class. An abstract class **cannot be instantiated** and has at least one PV method that is not implemented. Its purpose is to organize subclasses.

```ad-warning
Subclasses of an abstract class are also abstract unless they implement all pure virtual methods.
``` 

Non-abstract classes are called **concrete** in OOP

Relate: [[]]