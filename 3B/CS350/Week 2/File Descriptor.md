
File descriptor is an entry in a table the OS manages to keep track of all the file a process has opened and the corresponding permission

POSIX provides some standard file descriptors that are open by default each process.

- 0 for stdin
- 1 for stdout
- 2 for stderr

```c
int dup2(int oldfd, int newfd);
```


```c
int pipe(int fds[2])
```

- Sets the array to linked channels

