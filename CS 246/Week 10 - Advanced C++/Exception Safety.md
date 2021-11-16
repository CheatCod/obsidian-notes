---
alias: []
---
# Exception Safety
❌✔️✅📗
```ad-example
~~~c
void f() {
	MyClass mc;
	MyClass *p = new myClass();
	g();
	delete p;
}
~~~
If line 5 `g()` throws an exception, then we have a memory leak. Therefore the function is **not exception safe**.
```

## Basic Guarantee
If an exception occurs, the program will be in some valid state, no memory leak, class invariants maintained.

```ad-example
~~~c
void calculateGrades(vector<Student> & students) {
	for (auto & s : students) {
		s.calcuateGrade();
		// assumes this code only work for the fisrt 10 students
		// and throws exception on the 11th
	}
}
~~~
```

This function offers a **basic exception guarantee**, but if an exception if thrown, the first 10 students in the vector are modified.

## Strong Guarantee
If `f` throws or propagate an exception, the state of the program will be as if `f` had never been called.
Relate: [[]]