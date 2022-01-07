---
alias: [copy constructors]
---
# Copy Constructor
❌✔️✅📗
The copy constructor is a [[Constructor]]. 
The copy constructor's parameter is a constant reference to an object of the **same type**
The default copy constructor just copies each field to the object.
```ad-example
```c
Student( const Student & other ) 
      : id{other.id} assns{other.assns}, mt{other.mt}, final{other.final} {}
```

Althought, it makes sense to not copy the student's id as they should be unique.
```ad-example
```c
Student( const Student & other ) 
      : assns{other.assns}, mt{other.mt}, final{other.final} {}
```

For something like a vector, we would want to copy every data field:
```ad-example
```c
Vec( const Vec & other ) 
      : x{other.x}, y{other.y} {}
```

### When to **NOT** use the default behavior?
Consider linked list:
```c
struct Node {
   int data;
   Node * next;
  
   Node( int data = 0, Node * next = nullptr ) : data{data}, next{next} {}
};  
  
ostream &operator<<(ostream &out, const Node &n) {
  out << n.data;
  if (n.next) {
    out << ",";
    out << *(n.next);
  }
  return out;
}
```
The default constructor will only copy the contents of the data field. So we end up only with a copy of the first node and made a **shallow copy** of the rest. If we'd want the list to be independent of each other, we should make a **deep copy**:
```c
Node(const Node &n) {  
   data = n.data;  
   if ( n.next != nullptr ) {  
      next = new Node{ *n.next };  
   } else {  
      next = nullptr;  
   }  
}
```

Relate: [[]]