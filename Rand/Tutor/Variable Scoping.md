Java does not allow you redeclare a variable !

```java
int a = 1;
int a = 5; // WRONG! 
```

Why can't we do this?

```java
for (int i = 0; ; ) {
      // some code
    }
System.out.println(i); // ERROR!
```

The variable `i` is SCOPED inside the loop, and therefore cannot be accessed outside the loop.

```java
public class A1 {
	public static void main(String args[]) {
		// Given an positive integer variable a, print to the console
		// a triangle with heigh of a
		
		int a = 5;
		
		// output:
		// *
		// **
		// ****
		// *****
		// ******
	}
}
```