---
alias: [friend class, friend function]
---
# Friend Classes

Although we reinforced the invariant in [[Invariants and Encapsulation#^b2de56|here]], the clients cannot traverse this list from node to node. The only way to do so is to call `ith()` repeatedly, which cost $n^2$ time. One possible solution is to make `Node` a public nested class so the clients can retrive nodes and follow the pointers to the next node in the list, but make the `Node` constructor private, so clients can never create nodes that break the invariant. 

But if the constructor is private, `List` won't be able to create `Node` either. 

We can solve this by giving `List` privillage to access `Node` by making it a friend.

```c
class List { 
	public: 
	class Node {
		int data;
		Node *next;
		Node (int data, Node *next);
		public:
			~Node()
			int getData() const;
			Node *getNext() const;
			friend class List; // List has access to all members
	} // Private nested class; only accessible inside List    
	private: 
		Node *theList = nullptr; // Must be nullptr or pointer to heap-allocated object
	public:
		void addToFront(int n); // Adds an element to the front of the list    
		int ith(int i) const; // Retrieves the element in the ith position of the list   
		Node *getNodeAt(int i) const; // Retrieves the Node in the ith position of the list
		~List();

~List();};
```

Now the client can use `List`'s method `getNodeAt()` to retrieve a pointer to the `Node`, then, `Node`'s `getData()` method can be used to retreive the value of the element and `getNext()` can be used to traverse to the next node.

Since the `Node`'s constructor is private, client cannot directly create a `Node` object

```ad-warning
In general, you should give your classes as few friends as possible. Friendships weaken encapsulation and thus should be used only if really necessary.
```
Relate: [[]]