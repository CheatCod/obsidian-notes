---
alias: []
---
# Accessor and Mutator
Accessor methods are used to read attributes
Mutator methods are used to modify attributes.
```ad-example
```c
class Node {  
    int data;  
    Node *next;  
	public: 
    Node (int data, Node *next): data{data}, next{next} {}  
    . . .  
	// Accessor/getter methods
	int getData() const {
		return data;
	}
	
	// Mutator method
	int setData(const int data) {
		// More validations here
		this->data = data
	}
    ~Node() { delete next; }
};  
  
int main() {  
    Node n1 {1, new Node{2, nullptr}};  
    Node n2 {3, nullptr};  
    Node n3 {4, &n2};  //!! DOUBLE FREE !!
}

```

```ad-warning
DO NOT implement the following mutator method, as the client could use it to violate the invariants.

```c
void setNext(const Node *next) 
```


Relate: [[]]