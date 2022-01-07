---
alias: []
---
# Templates
If we want to implement a linked list with multiple data types: 

```c
class IntList {
    struct Node {
      int data;
      Node *next;
     . . .
    };
    Node *theList;
  public:
    . . .
};

class FloatList {
    struct Node {
      float data;
      Node *next;
     . . .
    };
    Node *theList;
  public:
    . . .
};
```

We can create a `List` **templates** :
```c
template <typename T> class List {
    struct Node {
      T data;
      Node *next;
     . . .
    };
    Node *theList;
  public:
    . . .
};
```

Now we can do:
```c
List<int> li;  // int is the value of the template parameter T.
               // So, each T in the List's code will be replaced with int.
li.addToFront(1);

List<string> ls;  // string is the value of the template parameter T.
                  // So, each T in the List's code will be replaced with string.
ls.addToFront("hello");
```
Relate: [[]]