# MIPS Hardware

```ad-note
We use 32 bit of MIPs, this means that each instruction will be 32 bits in length.
```

![[Pasted image 20220112012845.png]]

## Fetch-Execute Cycle
```
PC = 0x00
while true {
	IR = MEM[PC]
	PC+=4
	Decode and execute instruction
}
```

```ad-note
PC is incremented **BEFORE** the instruction is executed.
```


## Jump Instruction

```ad-syx
~~~
jr $s
~~~
```

$31 contains the return address of the caller.
To exist, jump to $31.


## Load Immediate and Skip

This instruction treats the value immediately after in memory as data, or an *immediate*, and place this value into $d, and then increase PC by 4.

