# ```extern```

Variable is going to be declared in the current file but defined somewhere else. 

```ad-example
```c
//vec.h
struct vec {
	int x, y;
};

Vec operator+(const Vec&, const Vec &);

extern Vec Origin;
```
No space is allocated during declaration
