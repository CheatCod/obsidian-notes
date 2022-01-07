---
alias: []
---
# Smart Pointers
❌✔️✅📗

Smart pointers manage the memory automatically by deleting the dynamic memory when the pointer itself goes out of scope.

## `unique_ptr`

You can only have one `unique_ptr` pointing to each address in the heap. When the `unique_ptr` is deleted, it automatically deletes the memory that it's managing in the heap.

```ad-syx
~~~c
std::unique_ptr<Type> p = std::make_unique<Type>(CTOR);
~~~
or we can use auto for less typing
~~~c
auto p = std::make_unique<Type>(CTOR);
~~~
```

We can use `p.get()` to get the wrapped pointer inside.

```ad-warning
A `unique_ptr` cannot be copied!
Use `move()` to transfer the ownership
```

## `shared_ptr`

You can have as many `shared_ptr` pointing to each address in the heap.

Shared pointers do reference counting.

```ad-warning
Shared pointer is not perfect in every situation, like in the case of **Cyclic references**
```



Relate: [[]]