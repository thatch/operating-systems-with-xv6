# Week 1

This is mostly about making sure your environment is going to work, and reading
the introductory text.  The questions and assignments will get you ready for
more of the same (increasing in difficulty) in future weeks, so don't skimp on
them.

## Computer Setup

Mac:

Thanks to https://github.com/riscv-software-src/homebrew-riscv this is pretty
easy if you already have homebrew.

```
brew tap riscv-software-src/riscv
brew install riscv-tools qemu
```

Arch Linux:

```
pacman -S qemu-system-riscv riscv64-linux-gnu-gcc
```

Fedora:

```
yum install qemu-system-riscv make gcc binutils-riscv64-linux-gnu gcc-riscv64-linux-gnu
```

Ubuntu 24.04 at least:

```
apt-get install qemu-system-misc build-essential gcc-riscv64-unknown-elf
```

## Testing compiler and emulator

Build and start a super basic system, including a toy shell and a few other binaries:

```
$ make qemu
...
hart 1 starting
hart 2 starting
init: starting sh
$ echo hi | cat
hi
```

To exit, type `Ctrl-a x` (similar to how shortcuts work in GNU Screen or Tmux).

## Reading

* [xv6 book](https://pdos.csail.mit.edu/6.828/2023/xv6/book-riscv-rev3.pdf) through middle of page 11

## Questions

* pg 9: Is "to a lesser extent, Microsoft Windows" entirely fair?  (Hint: read
  about [WSL 1 on Wikipedia](https://en.wikipedia.org/wiki/Windows_Subsystem_for_Linux) and
  form an opinion)
* pg 10: pick one of *processes, memory, file descriptors, pipes, and a file
  system* and consider what an implementation entirely in userland would look
  like -- even if it's silly.  Search the Internet to find if anyone has
  actually done just that :)
  * OSTEP for [Processes](https://pages.cs.wisc.edu/~remzi/OSTEP/cpu-api.pdf)
  * OSTEP for ([Virtual](https://pages.cs.wisc.edu/~remzi/OSTEP/vm-intro.pdf)) [Memory](https://pages.cs.wisc.edu/~remzi/OSTEP/vm-api.pdf)
  * OSTEP for [File](https://pages.cs.wisc.edu/~remzi/OSTEP/file-intro.pdf) ([System](https://pages.cs.wisc.edu/~remzi/OSTEP/file-implementation.pdf))
  * (I don't find a chapter that covers pipes)
  * Hints: coLinux, FUSE, any message queue system like RabbitMQ
* pg 10 (test in qemu): why does `echo "hi"` include the quotes?  Whose job is
  it to parse those?  (hint: see `man 3 system` [why 3])
* pg 11: where should you look for documentation (hint: `man 2 fork` [why 2],
  [posix spec](https://pubs.opengroup.org/onlinepubs/9699919799.2018edition/),
  or `man 3p fork` on Arch)

## Assignments

* Improve the kernel to support a longer `MAXPATH`.  Run your modified version
  in qemu and figure out a way to create a file, given only the userland
  provided, that demonstrates your change works.  (Hint: you should find at
  least one more hardcoded number that has to be changed, while trying it out)
  Find out what your computer's current OS uses for MAXPATH by either using
  `getconf(1)` or reading sources.

* Improve the `user/ls.c` to output the `st.type` as a mnemonic instead of as a
  number. Play with it in the emulator.  (Hint: If you need test data, note
  that `console` is a device)

* Write a userland program of your own, even if it's just printing a hardcoded
  string or a trivial implementation of `touch`.  (Hint: look at cat, echo, and
  references to `UPROGS` in the Makefile -- there's a pattern rule for `_%`
  that runs the actual compilation )
