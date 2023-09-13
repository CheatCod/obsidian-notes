# library os
library os is a library of services


# Multitasking OS

- Can run more than one process at a time
- When one process blocks run another process
- A multitasking OS must provide mechanisms to prevent an ill-behaved process from fking shit up
	- **Preemption** - take processor away form looping process
	- **Memory protection** - protect processes' memory from one another

## Protection

- OS takes on the role of interposition or mediation, places itself between application and the resources 
- On each access, look in a resource table to check that the access is legal
- Privilege and unprivileged modes in processor
	- User applications are unprivileged
	- OS has privilege access
- The OS kernel runs in privilege mode
	- Kernel manages process 
	- Kernel does IO with system drivers

# System calls

- Application can invoke the kernel through **system calls**
- System calls are special instructions that transfers control to kernel which in turn dispatches one of hundreds of system call handlers
- Difference to normal function call
	- Not jumping to the instruction address
- The kernel supplies well-defined system call interface, the application setup syscall arguments and **trap** to the kernel 

# Processes

Processes are one of the abstractions that are commonly part of an operating system, which could also include threads, synchronization, address spaces and file systems.

- A process is an instance of a running program
- Sometimes what the user thinks is a "running program" does not match to a running process
	- Word uses one process to manage multiple instance of the editor
- Browser will often have each website as its own process to provide isolation
- Modern OSes run multiple process simultaneously to
	- Simplify programming: a programmer does not have to account for the fact that other processes may be running
	- Provides isolation, a program with bugs should not crash other processes or the OS
	- Higher throughput: better processor utilization
	- Lower latency: time between launching a program and getting a response