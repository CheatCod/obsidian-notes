---
alias: [destructors]
---
# Destructor
✔️✅📗
The compiler implicitly provides a destructor for your class that does nothing except for invoking the destructors on object data fields.

Destructor is invoked automatically whenever an object on stack goes out of scope, or heap-allocated memory is freed.

The steps that occur when a destructor is run are:
```nomnoml
[1. Run the body of the destructor] -> [2. Invoke destructors for the object's data fields that are objects*]
[2. Invoke destructors for the object's data fields that are objects*] -> [3.  Deallocate the space associated with the object]
```
*This will occur in reverse declaration order
```ad-syx
```c
~class-name();
```

```ad-example
```c
~Node() { delete next; }
```



Relate: [[]]