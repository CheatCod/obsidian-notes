---
alias: [single argument constructors]
---
# Single Argument Constructor
❌✔️✅📗
```ad-example
```c
Student(int id);
...
Student s3{123}; // <- this is ok!
Student s4 = 123; // !! 
```

Compiler will guess you are trying to pass an int as the parameter to the [[constructor]], implicit conversion from int to Student.

Uses ```explict``` to prevent this behavior.


Relate: [[]]