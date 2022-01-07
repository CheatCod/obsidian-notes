---
alias: []
---
# Inhertiance
❌✔️✅📗
```ad-example
~~~c
class Book { // Super class
 	string title, author;
	int length;
public:
	Book(...);
}

class Text:public book { // derived/sub subclass
	string topic;
public:
	Text(...);
}

class Comic:public book { // derived/sub class
	string hero;
public:
	Comic(...);
}
~~~
```

Derived classes inherit the fields from the parent. So `Text` and `Comic` each has the `title, author, length` fields.

```ad-note
Even though `Comic` and `Text` are inheriting `Book`, `Book`'s private fields are still inaccessiable to them. 

Subclasses cannot access private fields of their parent
```

```ad-note
The public in `class Text:public book {` means to let the *maximum* visibility of all fields and method from book to be public.
```

With introduction of superclasses, the procedure in which an object is initialized has changed: 
```nomnoml	
[1. allocate space] -> [2. construct the data fields]
[2. construct the data fields] -> [3. Invoke the superclass constructor to build the superclass portion of the object]
[3. Invoke the superclass constructor to build the superclass portion of the object] -> [4.  run the constructor body]
```

Similarly, the steps in which objects are destroyed are changed too:

```nomnoml
[1. Run the body of the destructor] -> [2. Invoke destructors for the object's data fields that are objects*]
[2. Invoke destructors for the object's data fields that are objects*] -> [3. The superclass component is destroyed]
[3. The superclass component is destroyed] -> [4.  Deallocate the space associated with the object]
```

So the following attempt at initializing `Text` is wrong for 2 reasons
```c
Text(string title, string author, int length, string topic) : title{title}, author{author}, length{length}, topic{topic} {}
```

1. We can't access `title, author length` since they are private to `Book`
2. `Book` doesn't have a default constructor, and running the `Book`'s constructor in `Text`'s constructor is too late, thus we resort to [[Constructor#Member initialization lists MIL|MIL]]
```c
 : Book{title, author, length}, topic{topic} {}
```

```ad-note
If a class has no default constructor, then the subclass **must** invoke a superclass constructor in its MIL
```

## Protected
`protected` fields are accessiable to its subclass, although it's generally not a good idea since we want to maintain the superclass invariants



Relate: [[]]