C Preprocessor translate the code before the compiler

**Syntax:**

```c
#....
```
ex.
```c
#include <file>
```
is a preprocessor directive. It ==copie== the contents of that file into the code

---
# ```#define```

```c
#define VAR VALUE
```
define sets a preprocessor variable. Any occurance of ```VAR``` in the source file is replaced with ```VALUE```

```c
#define MAX 10
int x[MAX]
```
use ```const``` instead

---
# ```#if``` with ```#define```

```c
#define FLAG
```

Sets the preprocessor variable FLAG, defaults to the empty string

Use ```if``` in conjuncture with preprocessor variables to change compilation conditionally

Ex.
```c
#define OS 1
...

#if OS == 1
do_smthing(..);
#elfi OS == 2
do_another(..);
#endif
```
---
# Compilation Flags

```-D[VAR]=[VALUE]``` as compilation flag

ex.
```c 
int main() {
	cout << X << endl;
}
```

```bash
g++ -std=c++14 -DX=15 preprocessor.c
```
Output:
```15```

! Remember to escape string

```bash
g++ -std=c++14 -DX='"Hello"' preprocessor.c
```

---
# ```ifdef / ifndef NAME```

```ifdef``` - true if name has been defined

```ifndef``` true if name hasn't been defined
