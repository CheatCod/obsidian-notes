
# Make

The relationship between files created a system of <u>dependencies</u>:"

```nomnoml
[vecs] -> [main.o]
[main.cc] -> [vec.h]
[vecs] -> [vec.o]
[vec.o] -> [vec.cc]
[vec.cc] -> [vec.h]
[main.o] -> [main.cc]
[main.cc] -> [vec.h]
```

The make file for the project structure above is:
```make
vecs: main.o vec.o  <-- vecs depends on main.o and vec.o
	g++ main.o vec.o -o vecs
main.o: main.cc vec.h  <-- main.o depends on main.cc nad vec.h
	g++ -c main.cc
vec.o: vec.cc vec.h
	g++ -c vec.cc
```

```ad-note
must be placed in file named ```makefile``` or ```Makefile```
```

If we don't ask specifically, then ```make``` creates the first target that's in the makefile. However, you can also specify a target:

```bash 
$ make main.o
```
# Phony Targets

To delete the detritus ```.o``` files in the directories, we can use phony target(i.e., a target that exists only for its recipe, and doesn't actually build anything). 
```make
vecs: main.o vec.o
	g++ main.o vec.o -o vecs

main.o: main.cc vec.h
	g++ -std=c++14 -c main.cc

vec.o: vec.cc vec.h
	g++ -std=c++14 -c vec.cc

.PHONY: clean

clean:
	rm *.o vecs**
```

```bash 
$ make clean  
rm *.o vecs  
```

# Make Variables

We can extract duplicate flags into make variables

```bash
$ cat Makefile 
CXX=g++
CXXFLAGS=-std=c++14**
OBJECTS=main.o vec.o
EXEC=vecs

${EXEC}: ${OBJECTS}
	${CXX} ${OBJECTS} -o ${EXEC}

main.o: main.cc vec.h
vec.o: vec.cc vec.h
.PHONY: clean

clean:
	rm ${OBJECTS} ${EXEC}
```

```ad-note
`CXX` and `CXXFLAGS` are predefined make variables
```

# Automatic Dependency Management

```g++``` is capable to generating dependency information with the ```-MMD``` flag. 

```bash
$ cat Makefile 
CXX=g++
CXXFLAGS=-std=c++14 -MMD
OBJECTS=main.o vec.o
DEPENDS=${OBJECTS:.o=.d} <- swap .o with .d
EXEC=vecs

${EXEC}: ${OBJECTS}
	${CXX} ${OBJECTS} -o ${EXEC}

-include ${DEPENDS}

.PHONY: clean

clean:
	rm ${OBJECTS} **${DEPENDS}** ${EXEC}  
  
$ make  
g++ -std=c++14 -MMD   -c -o main.o main.cc  
g++ -std=c++14 -MMD   -c -o vec.o vec.cc  
g++ main.o vec.o -o vecs  
$ cat main.d  
main.o: main.cc vec.h  
$ cat vec.d  
vec.o: vec.cc vec.h
```