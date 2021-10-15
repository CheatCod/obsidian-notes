---
alias: [constructors]
---
# Constructor

A special type of [[Methods|method]] in C++ to initialize object upon creation.

```ad-note
title: Syntax
```c
Name-of-Class-Type( parameter-list ) {
   // necessary code
}
```

```ad-note
-   There is no return type, since you're building the actual object. The constructor does not return the object it builds.
-   The method name is the type name.
-   The parameter list may be empty.
-   Constructors can be overloaded!
-   The method body may be empty, but must be present.
```

Example: 
```student.h```:
```c 
#ifndef _STUDENT_H_  
#define _STUDENT_H_  
  
struct Student {
   int assns, mt, final;

   Student( int assns, int mt, int final );
   float grade();
};  
  
#endif
```

```student.cc```:
```c
#include "student.h"  
  
int capGrade( int grade ) {  
   if ( grade < 0 ) return 0;  
   if ( grade > 100 ) return 100;  
   return grade;  
}  
  
Student::Student( int assns, int mt, int final ) {  
   this->assns = capGrade( assns );  
   this->mt = capGrade( mt );  
   this->final = capGrade( final );  
}  
  
float Student::grade() {
  return assns * 0.4 + mt * 0.2 + final * 0.4;
}
```

```ad-note
we use ```this->``` notation since the parameter names are the same as our data field names.
```
```ad-warning
If I don't use `this`, the compiler assumes that I want to use the local parameters, and will assign them to themselves, i.e., `assns` to `assns`, `mt` to `mt`, and `final` to `final`. This leaves my data fields uninitialized (or at least, not initialized with the values I want). The same problem occurs if you initialize local variables rather than the object's data fields.
```

## Overloading constructors
We can also overload the constructor just like a method. This means we can use default parameters in the constructors.

 ```ad-warning
 Default parameter on constructors must only go on the *interface* and **NOT** the implementation.
 ```
 
 ```ad-example
 ```c
 struct Student {
      int assns, mt, final;

      Student( int assns = 0, int mt = 0, int final = 0 );
      float grade();
   };
```

Now 
```c
Student s1{ 60, 70, 80 }, s2, s3{60}, s4{60, 70};
```
are all valid initializations.

## Default constructor 
```ad-note 
title: Definition
**Default constructor**: a constructor that has 0 parameter
```

If you do not provide any constructor to a class, then the compiler automatically generates a default constructor. All it will do is call the default constructor on any data fields in your object that are themselves objects. This will only work if those objects also have a default constructor defined in their class type.

```ad-note
The "default" default constructor is no longer available as soon as you declare (and define) any other constructor
```
See the following example:
```c
struct Vec{
   int x, y;
   Vec( int x, int y ) {
      this->x = x;
      this->y = y;
   }
};

Vec v1{ 5, 6 }; // this is okay
Vec v2; // **this will not compile!**
```
If you remove the constructor, then `v2` will become valid and `v1` invalid. To make both valid, you would need to write two constructors.


## Initializing constants and references
If we want to initialize an object with a constant or a reference, but not all objects will use the same value. 

We can't initialize it in the constructor body since the data fields have already been created and initialized. Constants _have_ to be initialized when their space is allocated.

The steps invovled in creating an object are:
```nomnoml
[1. allocate space] -> [2. construct the data fields]
[2. construct the data fields] -> [3.  run the constructor body]
```

To insert values at the second step, we use a special form of syntax called the [[#Member initialization lists MIL]] (MIL).

## Member initialization lists (MIL)
```ad-example
```c
Student::Student( const int id, int assns, int mt, int final ) 
   : id{ id },  
     assns{ capGrade(assns) },   
     mt{ capGrade(mt) },   
     final{ capGrade(final) }  
{}

```

```ad-note
-   The name _outside_ of the "`{}`" in the MIL is the data field, while the name _inside_ of the "`{}`" is the parameter name. 
-   The MIL can be used to initialize other data fields, not just constants or references.
-   Fields in the MIL are initialized _in the order in which they are declared in the class_, **not** in the order that they are listed in the MIL!
- ```ad-note 
  Using the MIL can be **more efficient** than initializing in the body of the constructor. This is particularly true when the data field is an object that has a default constructor. The object will be first initialized with the default constructor when it is created, and then initialized again in the body of the constructor using the assignment operator. In other words, you've just initialized it twice!  
      
    Consider the following example:
    ```c
    struct Student {
       string name;
       Student( const string & name ) {
          this->name = name;
       }
    };
    ```
    The data field `name` is initialized with the `std::string` default constructor, and then reassigned in the constructor body.
- MIL initialization **takes precedence** over initialization in the class.
  ```ad-example
  ```c
  struct Vec {
    int x = 0, y = 0;
    Vec() {}
    Vec( int x ) : x{x} {}
    Vec( int x, int y ) : x{x}, y{y} {}
};
Vec{5} // the data field `x` will contain the value 5 but the data field `y` will contain the value 0

- MIL can **only** be used on constructors, not on any other method!

- It is quite common for constructors to have a MIL and an empty body, and it is usually considered *poor practice* to use the body to do anything that the MIL could have done.

- if you need sophisticated logic, such as loops or conditions, to initialize your fields, use the body, but otherwise use the MIL
```

Relate: [[]]