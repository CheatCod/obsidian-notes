---
aliases: [class]
---
# Classes
```ad-def
**Class**: Generic template for objects. Composed of data(attributes) and operations([[methods]])
```


```ad-example
```c
// student.h
#ifndef _STUDENT_H_
#define _STUDENT_H_

struct Student {
   int assns, mt, final;

   float grade();
};
#endif

// student.cc
#include "student.h"

float Student::grade() {
  return assns * 0.4 + mt * 0.2 + final * 0.4;
}
```



[[Methods]]