---
alias: [Member operator]
---
# Member operators
Some functions _must_ be declared members of the class, others are not allowed to be class members, and for some we have a choice whether they're placed in the class.

Recall [[Methods|method]] that, **All** class methods have a hidden, extra first parameter called `this` that is a pointer of the class type. Thus, the first parameter `this` is the first operand.
```ad-example
```c
struct Vec {
   int x, y;
   
   Vec operator+( const Vec & other ) {
      return {x + other.x, y + other.y};
   }
   
   Vec operator*( const int k ) {
      return { x * k, y * k };
   }
};
```
where
```c
Vec operator+( const Vec & other)
``` 
is really
```c
Vec operator+(this, const Vec & other)
```

`v1 + v2` is `v1.operator+(v2)`. Note that this implies the first parameter must be a `Vec`, thus making `3 * v1` a syntax error.

The only way we can create a version that works is to move this version of `operator*` outside of `Vec`, as in:

```c
struct Vec {
   int x, y;
   
   Vec operator+( const Vec & other ) {
      return {x + other.x, y + other.y};
   }
   
   Vec operator*( const int k ) {
      return { x * k, y * k };
   }
};

Vec operator*( const int k, const Vec & other ) {
   return other * k;
}
```

Relate: [[]]