---
alias: []
---
# Copy&Move Elission
✔️✅📗
The compiler is allowed to optimize constructor calls when there is a temporary object.

Where optimization means directly initializes the fields of an object without calling the constructor 

```ad-example
```c
#includec<iostream>

struct Node {
    int data;
    Node *next;

    Node( int data, Node * next = nullptr );
    Node( const Node & other);
    ~Node() { delete next; }
};

std::ostream &operator<<(std::ostream &out, const Node &n);
  
Node plusOne( Node n ) {
    for ( Node *p{&n}; p ; p = p->next ) {
        ++p->data;
    }
    return n;
}

int main() {
    Node n{ 1, new Node{2} };
    Node n2{ plusOne(n) };
    std::cout << n << std::endl << n2 << std::endl;
}

// _implementations follow_
```

```nomnoml
[line 21 executes with 2 calls of ctor] -> [plusOne(n) is called, n is copied to stack frame with 2 calls of ctor]
[plusOne(n) is called, n is copied to stack frame with 2 calls of ctor] -> [plusOne() returns, 2 calls of ctor for return value] 
[plusOne() returns, 2 calls of ctor for return value] -> [return value is stored in a temp object in main]
[return value is stored in a temp object in main] -> [2 calls to n2's ctor to copy the temp object into n2]
[2 calls to n2's ctor to copy the temp object into n2] -> [Destruct the temp object]
```
With elision, the `Node` returned by `plusOne` is copied directly into the space allocated for `n2`.

```ad-warning
As of C++11, the compiler is **required to omit move/copy constructor calls** in favour of building the information directly into the memory space where it would have been moved/copied, even if **omitting these calls changes the behaviour of the program!**

E.x, if the constructors have side effect such as printing or incrementing a counter, etc.

**Not all copy or move constructor calls** are removed!! The compiler just remove the ones where **copying/moving into/from an rvalue**. Since an rvalue has no accessible address it is a temporary object designed to be thrown away, so the information may as well be written directly into the final destination.
```

We can disable this behavior with `-fno-elide-constructors`
Relate: [[]]