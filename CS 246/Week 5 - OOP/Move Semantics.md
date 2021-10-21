---
alias: []
---
# Move Semantics
❌✔️✅📗

Recall **lvalues** and **rvalues**
```ad-def
If you can take the address of an expression, it's a **lvalue**; otherwise, it's a **rvalue**. **lvalue** is something that can appear on the left hand side of an assignment, and **rvalue** can only appear on the right side of assignment, they are usually temporary objects.
```

Why should we care for move semantics? Consider the following example:
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

We note that `plusOne()` is pass-by-value, and return `n` by value. 
So, on line `23`, the compiler creates a *temporary*  `Node` object as the return value of `plusOne()`, then the [[copy constructor]] of `n2` runs, copying everything over from the temporary object, then the temporary object is discarded.

```nomnoml
[line 21 executes with 2 calls of ctor] -> [plusOne(n) is called, n is copied to stack frame with 2 calls of ctor]
[plusOne(n) is called, n is copied to stack frame with 2 calls of ctor] -> [plusOne() returns, 2 calls of ctor for return value] 
[plusOne() returns, 2 calls of ctor for return value] -> [return value is stored in a temp object in main]
[return value is stored in a temp object in main] -> [2 calls to n2's ctor to copy the temp object into n2]
[2 calls to n2's ctor to copy the temp object into n2] -> [Destruct the temp object]
```

We see that the second last and last steps are doing duplicated work, as the return value of discarded. If we can find a way to *Move* the temp object to `n2`, we won't need to make an additional copy, and save some ctor calls.

## Move Constructor

When a constructor is called that received a rvalue reference instead of a lvalue reference, the move constructor is called instead of the ctor.

```ad-syx
```c
class-type( class-type && parameter-name ) {...}
```

```ad-note
Since we are creating a new object, we don't care about the old object, thus no `const`
`&&` means a rvalue reference
```

```ad-example
```c
Node( Node && other );
...
Node::Node(Node && other)
	: data(other.data), next{other.next}
{
	other.next = nullptr;
}
```

```ad-digm
collapse:
![[Attachments/Move Semantics_2021-10-20 18.26.58.excalidraw.md]]
![[Attachments/Move Semantics_2021-10-20 18.43.14.excalidraw.md]]
![[Attachments/Move Semantics_2021-10-20 18.46.59.excalidraw.md]]
```
Relate: [[]]