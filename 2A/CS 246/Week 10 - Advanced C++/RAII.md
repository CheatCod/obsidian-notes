---
alias: [Resource Acquisition Is Initialization]
---
# RAII: Resource Acquisition Is Initialization
❌✔️✅📗

Resources that must be explicitly cleaned up are bound to resources that are cleaned up automatically.

Dynamic memory is only one of the resources, other resources include files, network connections, databases connections, etc.

```ad-example
`ifstream` for opening file doesn't need to be explicitly closed
```
Relate: [[]]