---
alias: []
---
# Invariants and Encapsulation
❌✔️✅📗

## Invariants

Consider the following example

```ad-example
```c
struct Node {  
	int data;  
	Node *next;  
	Node (int data, Node *next): data{data}, next{next} {}  
	. . .  
	~Node() { delete next; }  
};  
  
int main() {  
	Node n1 {1, new Node{2, nullptr}};  
	Node n2 {3, nullptr};  
	Node n3 {4, &n2};  //!! DOUBLE FREE !!
}
```

^b2de56

```ad-def
**Invariant:** a statement that must hold true otherwise our program will not function correctly.
```
In this case, the class `Node` relies on the fact that all `next` is heap allocated, so ideally the following should be part of `Node`'s documentation.
```c
// Invariant
// - next must be heap allocated Node 
// - each Node is responsible for deleting the next one.
```
	
This solution is not ideal, as we cannot enforce this to the client. To enforce invariants, we use Encapsulation.


## Encapsulation
Encapsulation is the idea that treat a class as a black box, and hide the internal implementation details from the client, and provide only a public interface.

```c
struct Node {
private: 
    int data;  
    Node *next;
public: 
    Node (int data, Node *next): data{data}, next{next} {}  
    . . .  
    ~Node() { delete next; }  
};  
  
int main() {  
    Node n1 {1, new Node{2, nullptr}};  
    Node n2 {3, nullptr};  
    Node n3 {4, &n2};  //!! DOUBLE FREE !!
}
```

```private``` fields can only be accessed from within the object
```public``` fields can be accessed anywhere
```ad-note
In C++ struct, members are public by default.
In C++ class, memebrs are private by default.
```

We can then use [[Accessor and Mutator]] to enforce invariant. 

## Fixing the linked list with Encapsulation

We enforce the invariants by encapsulate the implementation of the nodes from the client.

`list.h`: 
```c
class List {    
	struct Node; // Private nested class; only accessible inside List    
	Node *theList = nullptr; // Must be nullptr or pointer to heap-allocated object
	public: void addToFront(int n); // Adds an element to the front of the list    
int ith(int i); // Retrieves the element in the ith position of the list   
~List();};
```

`list.cc`:
```c
struct List::Node {
	int data;
	Node *next;
	Node (int data, Node *next): data{data}, next{next} {}
	~Node() {delete next;}
}

List::~list() {delete theList;}

void List: addToFront(int n) { theList = new Node (n, theList);}

int List::ith(int i) {
	Node *cur = theList;
	for (int j = 0; j < i && cur; ++j, cur = cur->next);
	return cur->data;
}
```
Relate: [[]]