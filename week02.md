# Week 2

Everything you run needs to come from the kernel, libraries, or user code.
Collectively, libraries (like libc) and user code are called "userland".  We'll
take a side quest to remind ourselves of the primitives that create processes,
and how to accomplish *useful* work with a minimal environment on top of syscalls.

## Reading

* [xv6 book](https://pdos.csail.mit.edu/6.828/2023/xv6/book-riscv-rev3.pdf) from page 11 to 19.
* OSTEP for [File](https://pages.cs.wisc.edu/~remzi/OSTEP/file-intro.pdf) ([System](https://pages.cs.wisc.edu/~remzi/OSTEP/file-implementation.pdf))

## Questions

* end of pg 12: what happens if `echo` forgets to call `exit`?  Hint: `user/ulib.c`
* beginning of pg 13: *does* `malloc` call `sbrk`?  Hint: `user/umalloc.c`
* pg 19: "XV6 is *not* POSIX compliant" -- from the list on page 11, find at
  least one that's different and explain how.  How hard do you think it would
  it be to *make* it more compliant (Hint: start with just the function
  prototypes)

## Assignments

* write a program that causes `malloc` to return an error -- for example an
  impossible allocation size.  If very large, what is the limiting factor here
  -- virtual, or physical?
* ping-pong exercise from the end of pg 19 (but performance measurement is
  probably a bit much, just make it go 10 rounds and stop)
