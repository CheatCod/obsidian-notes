---
alias: []
---
# Include Cycles
❌✔️✅📗

If one declaration includes another declaration which uses the first declaration, we have a 
**include cycle**

```ad-example
`student.h`:
~~~c
#include "course.h"
class Student {
	Course course;
	int grade;
}
~~~
`course.h`
~~~c
#include 'student.h'
class Course {
	Student student;
}
~~~

```

To break this cycle, we can use pointers and **forward declaration**

`student.h`:
~~~c
class Course;
class Student {
	Course *course;
	int grade;
}
~~~
`course.h`
~~~c
class Student;
class Course {
	Student *student;
}
~~~


https://learn.uwaterloo.ca/d2l/le/content/709713/viewContent/3837963/View

Relate: [[]]