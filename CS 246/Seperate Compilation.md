# Seperate Compilation

Spilts program into composable <u>modules</u>, which each provide
- Interface (header) file: type definitions and protypes for functions (.h files)
- Implementation file: Full definition of the header (.cc file)

Ex.
```vec.h```(interface):
```c
struct vec {
	int x, y;
};

Vec operator+(const Vec&, const Vec &);
```

```main.cc```(client):
```c
#include "vec.h"

int main() {
	Vec v{1, 2}; // <- legal since header file
	v = v+v
}
```

```vec.cc```(implementation):
```c
#include "vec.h"
Vec operator+(const Vec &v1, const Vec &v2){
	return ...;
}
```

! an entity can be multiple times, but defined only once 

Use ```-c``` flag to specify compiling a binary file without linking to create full executable.

```bash
g++ -c vec.cc
```
^by default creates vec.o

```bash
g++ -c main.cc
```
^by default creates main.o

```bash
g++ vec.o main.o -o main
```
^Link the two object files into an exectuable

We only need to recompile ```vec.cc``` if only it has changed

```nomnoml
[vecs] -> [main.o]
[main.cc] -> [vec.h]
[vecs] -> [vec.o]
[vec.o] -> [vec.cc]
[vec.cc] -> [vec.h]
[main.o] -> [main.cc]
[main.cc] -> [vec.h]
```
