
Kernel can preempt a process when kernel gets control
- System call, page fault illegal instruction
- May put the current process to sleep

# Context switch

During context switch, kernel saves the PCB (process control block) and restores it later (registers, etc)

What's saved is machine dependent, typically:

- PC and integer registers (always)
- Floating point or other special registers
- Condition codes
- Change virtual address translation

**A context switch is has non-neligible cost**

- Saving/restoring register is expensive
- May require flushing TLB (translation lookaside buffers, address translation hardware)
- Usually causes more cache miss

