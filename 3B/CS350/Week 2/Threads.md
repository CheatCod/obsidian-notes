
Threads are one of the abstractions that are typically part of an OS.

Can think of thread as a sequence of instructions.

A thread is a *schedulable execution context*

Each thread has its own stack and register values (PC, instruction register, stack pointer, frame pointer)

Threads in the same process share: the code, global variable heap and file descriptors of the process.

Threads now compete in the same "stack space", thus we will need to put in a stack size

# POSIX thread API

`int pthread_reate(pthread_t *thr, pthread_attr_t *attr, void *(*fn)(void *), void *arg)`

`void pthread_exit(void *return_value);

Destroy the current thread and set a pointer to its return value

Cast arg to void* and cast it back when threads want to access it

**User threads** are threads that the user application creates and manages, including which one will run next

**Kernel thread** are threads that the OS creates and manages, including which one will run next

Since syscall is expensive, it might take 100 or so assembly language instructions for a system call and only a few assembly language instructions for a function call.

Functions such as pthread_create and be either implemented in syscall or a normal function call (inexpensive)

# Kernel Threads

![[Pasted image 20230921124224.png]]

n:n threads

Limitations:

- Every thread operation must go through the kernel
- Syscalls are slower
- One-size fits all thread implementation
	- Kernel threads must please all sorts of application demands
- Heavy-weight memory requirements
	- Requires a fixed-size stack (2mb)

# User Threads

implement threads in a user-level library (javascript)

multiple user threads can run on one kernel threads



#