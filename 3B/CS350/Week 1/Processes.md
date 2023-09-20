- Each process has its own view of the computer with its own
	- Address space
	- Open files
	- Virtual CPU
- An address that each process sees is a virtual address.
- Simplfied programming model, process does not care about the existence of other processes

## Process API

`fork()`
- Creates a new process that is an exact copy of the current one
- Return process ID of new process in "parent"
- Return 0 in "child"

`int waitpid`



`int execve(char *prog, char **arv, char **envp)`
- Replaces the current running program with a new one `prog`
- If call success, the current program cease to exist