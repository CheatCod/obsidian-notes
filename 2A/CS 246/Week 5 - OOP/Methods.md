---
aliases: [method, class methods, class method]
---

# Methods

**All** class methods have a hidden, extra first parameter called ```this``` that is a pointer of the class type.

Declariation: (```student.h```):

```c 
struct Student {
	int assignments;
	int midterm;
	int final;
	float grade();
}

```
Implementation: (```student.cc```):

```c
#include "student.h"  
float Student::grade(Student this) {
     return this->assns * 0.4 + this -> mt * 0.2 + this -> final * 0.4;
   }
```

obj.method() -> method(Class* obj)