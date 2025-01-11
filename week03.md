# Week 3

The text proposes some first-principles requirements for an operating system:
multiplexing, isolation, and interaction.  Some new terms are introduced to
describe choices like "monolithic kernel" that are worth expanding on with
other readings.

We start passively talking about assembly instructions (but no prior exposure
to RISC-V is necessary, and you can gloss over this if it isn't fun).

## Reading

* [xv6 book](https://pdos.csail.mit.edu/6.1810/2024/xv6/book-riscv-rev4.pdf) from page 21 to 27.

## Questions

* pg 22: find an operating system that uses/used cooperative multitasking.  Why
  might that have been a design choice?
* beginning of pg 23: how are the privileged structures keeping track of open
  files isolated from user code, for "operating system must arrange that
  applications cannot modify"?
* pg 23: find an example of `ecall` in the hybrid disassembly for a user
  program like `user/cat.asm`.  Why might there be trivial named wrappers here?
  (Slight hint, these are included from `user/usys.S`)
* pg 24 (if you like history): most kernels are monolithic today, but the one
  modern exception is the one used in OS X (as well as other Apple products)
  which is "hybrid."  Read a bit of history at
  https://en.wikipedia.org/wiki/Mach_(kernel) and consider what their reasons
  might have been for going this route.
* pg 27: Research how (even today) you might want to not have a full OS thread
  per "thread of control," such as "Virtual Threads" in Java, goroutines in
  go, asyncio in Python, or (if you're a fan of dad jokes)
  [fibers](https://learn.microsoft.com/en-us/windows/win32/procthread/fibers) in Windows.


## Assignments

* write a program that outputs `sizeof(long)` and `sizeof(int)` to verify the
  claims of "LP64" on pg 21.  (Technically these are known at compile-time, but
  it's probably simpler to just use `printf`)
* write your own syscall called `optimist` that takes a pointer and usually
  puts the text `"yes"` into it, but rarely puts the text `"maybe"`.  Since we
  don't have a full RNG, consider what else you might use to decide.  Call it
  from a trivial user program.  Consider how to coordinate syscall numbers
  between vendors, or what to do when you "run out." (Hint: `grep -i sys_read
  kernel/*` and `user/user.h`)
