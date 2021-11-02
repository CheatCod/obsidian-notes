---
alias: []
---
# Iterator
❌✔️✅📗

```ad-example
Linked List with an Iterator:

```c
class List {
    struct Node;
    Node *theList;

  public:
    // Implementation of the Iterator design pattern 
    class Iterator {
        Node *p;
        explicit Iterator(Node *p): p{p} {}  // Private constructor
       public:
        int &operator*() {
            // Access the current item  
            return p->data;
        }
        Iterator &operator++() {
            // Advance the pointer and return it
            p = p->next;
            return *this;
        }
        bool operator==(const Iterator &other) const {
            // An iterator is equal to another if their pointers are equal
            return p == other.p;
        }
        bool operator!=(const Iterator &other) const {
            // The reverse of the equals operator
            return !(*this == other);
        }
        friend class List; // List has access to all members of Iterator
    };

    // The client calls this method to obtain an Interator
    // that points to the first element in the list
    Iterator begin() {
        return Iterator{theList};
    }

    // The client calls this method to obtain an Interator
    // that points to the position after the end of the list
    // (i.e., a null pointer because a linked list ends when the 'next' pointer is null)
     Iterator end() {
        return Iterator{nullptr};
    }

    . . . // other list operations (addToFront, ith, etc.)
};
```
Relate: [[]]
