---
alias: [copy assignment operator]
---
# Copy Assignment Operators
✔️✅📗

Similar to [[Copy Constructor]], default only performs shallow copying of data fields. 

Overwrite if we want deep copy such as fo ```Node``` object
```ad-syx
```c
[_class-type_] & operator=( const [_class-type_] & [_parameter-name_] );
```

```ad-example
```c
Node & operator=( const Node & other) {
   if ( this == &other ) return *this;
   Node * tmp = other.next? new Node{ *other.next } : nullptr;
   data = other.data;  
   delete next;
   next = tmp;
   return *this;
}
```

By definition, it takes a constant reference of the class type as its single parameter, and returns a reference of the class type, since it needs to be able to modify the object on the left-hand side of the assignment if it's part of a cascade/sequence of assignment operations. 
```ad-example
```c
jane = bill = fatima;
```
would copy the contents of the `fatima` object into the `bill` object, then copy the contents of the `bill` object into the `jane` object.

##  Copy-swap idiom

We can use the fact that locally-created object to the copy-assignment operator will be automatically destroyed when the routine terminates, so, we can use the local object to make a deep copy, if that's successful, we can just swap the data field of `this` with the local object.
```c
#include <utility>
struct Node {
   ...
   void swap( Node & other ) {
      std::swap( data, other.data );
      std::swap( next, other.next );
   }
   
   Node & operator=( const Node & other) {
      Node tmp{ other };
      swap( tmp );
      return *this;
   }
   ...
};
```

Since `tmp` now is a proper deep copy, we can swap the fields of `tmp` and `this` so that `tmp` now has the linked pointers of `this`, and `this` now have a proper deep copy of `tmp`. When the routine finish, since `tmp` is a local variable, compiler will call destructor on `tmp`, which frees up all the old memory of `this`

```ad-warning
This method requires the proper implementations of destructor to ensure proper clean up.
```
```ad-digm
collapse:
![[Drawing 2021-10-20 23.33.24.excalidraw]]
```
Relate: [[]]