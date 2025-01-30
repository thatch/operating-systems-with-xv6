# Week 4

We start digging into how the kernel is put together, and what a boot process
looks like on RISC-V.  This is fairly similar to ARM Cortex-M4, but drastically
simpler than x86.

We introduce kernel debugging, which is pretty easy with qemu, but historically
was kind of a pain (involving null modem serial cables) so most people relied
on panic screens that dump registers.  The Windows BSOD is an example of this.

## Reading

* [xv6 book](https://pdos.csail.mit.edu/6.1810/2024/xv6/book-riscv-rev4.pdf) from page 28 to 30

## Questions

* pg 28: what is the job of "/init" here?  What does a *real* init need to take
  care of?  Can you specify `init=/bin/bash` to a linux kernel command line?

## Assignments

* Look at the file `kernel/kernel`, determine its format, and disassemble it
  yourself (not just looking at `kernel/kernel.asm`, that's cheating) to
  understand how low-level the instructions are without benefit of the source
  code.  Find one amusing function near the beginning and surmise what it does.
  [RISC-V Assmebler: Branch Set](https://projectf.io/posts/riscv-branch-set/#program-counter)
  may be helpful.  (Hints: `file(1)`, `<prefix>-objdump -d <file> | head -n
  50`, `auipc` is one such instruction, typically in the third column)
* Debug your kernel, and put a breakpoint on a syscall (like `sys_write`) to see
  how argument handling happens.  (Hints: `make qemu-gdb` and then run
  `riscv64-elf-gdb` *in the same working dir in another window* then use
  the cheat sheet below to break in `sys_write`.  Try to follow the trail until
  your find the code that actually outputs a single byte (Hint: `consolewrite`
  is close)
* Extra credit: Implement a syscall `dup2` that allows you to specify the
  destination fd number.  Refer to previous week's "optimist" assignment if you
  need hints.  Write a user program that dup2's stdout to a new number of your
  choice and write to it in user code.  Do that (with the same args) in a loop
  1000 times; does your code have any bugs?

## GDB Install

Mac:

```
brew install riscv64-elf-gdb
```

Arch:

```
pacman -S riscv64-elf-gdb
```

Ubuntu (use standard `gdb` command after install):
```
apt install gdb-multiarch
```

etc.  (`riscv64-linux-gnu-gdb` also works, if you can't find the bare-metal one)

If you get an error about having to run something to trust this `.gdbinit`, you should run that.

## GDB Cheat Sheet

```
b <funcname>    set breakpoint at start of given function
c               continue
n               next (similar to "step over")
s               step (similar to "step into")
info locals     prints current contents of local vars
p <varname>     prints just one variable
```
