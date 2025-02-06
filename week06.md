# Week 6

This is the final week of the first run.  Make sure you fill out the survey
so we can gauge the informativeness, pace, complexity, fun, and get you your
completion sticker.  You'll implement a missing piece of the xv6 kernel, which
is what makes shell scripts (and perl scripts, python scripts, etc) work
without requiring them to have a special file extension.

## Reading

* [xv6 book](https://pdos.csail.mit.edu/6.1810/2024/xv6/book-riscv-rev4.pdf) pages 40-41 (from last week again)
* https://en.wikipedia.org/wiki/Shebang_(Unix)
* `kernel/exec.c`

## Questions

* What is the "magic" for an interpreted script?  What is the "magic" for ELF binaries?
* Can an interpreted script have an interpreted script as its interpreter?
  * Can you just implement `exec` recursively?

## Assignments

* Implement basic interpreted script handling. When a file is executable,
  read the first few bytes and decide if it's instead a path to use as the
  binary to load (not `argv[0]`).  Assuming you pick `/sh` as your interpreter,
  you might need to make changes there as well, since the _script_ will now be
  `argv[0]`.  (If you need to debug your kernel, see instructions in week 4.)
