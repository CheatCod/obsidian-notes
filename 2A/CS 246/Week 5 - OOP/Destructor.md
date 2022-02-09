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


$$
 \begin{algorithme}
    $\alg{HalfSort}(A)$\\
    $A$: an array of size $n\geq 2$ storing distinct numbers\\
     \lign    $i \gets 1$\\
     \lign \pc{while} $i < n $ \\
     \lign  \hspace{5ex} \pc{if} $A[i-1] > A[i]$\\
      \lign \hspace{10ex} \pc{return} false\\
      \lign  \hspace{5ex}  $i \gets i+2$\\
        \lign  \pc{return} true\\
   \end{algorithme}
$$

Relate: [[]]