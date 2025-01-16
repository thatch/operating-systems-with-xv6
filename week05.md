# Week 5

This week is tightly coupled with Week 6, and peeking ahead might be useful to
get the context why pages 40-41 are more important.

## Reading

* [xv6 book](https://pdos.csail.mit.edu/6.1810/2024/xv6/book-riscv-rev4.pdf) from page 31 to 42 (but pay particular attention to 40-41)
* [binfmt_misc](https://en.wikipedia.org/wiki/Binfmt_misc) for background on `exec` pluggability
* [linuxemu](https://docs.freebsd.org/en/books/handbook/linuxemu/) if you're
  interested in BSD at all -- in particular 12.4.2 about `brandelf`

## Questions

* Name one thing oversimplified about the xv6 memory model?
* Gauge how complex it would be to add CoW support for memory pages?  Could you
  share pages with identical contents that have different protection bits?
* Can you imagine how swap would be implemented on top of this?

## Assignments

* pg 36: Without the text in front of you, explain TLB like I'm five years old.
  You're not allowed to use the words "memory" or "mapping"
* pg 37: "xv6 assumes that the machine has 128 megabytes of RAM."  Can you make
  it support more (under qemu) without having to hardcode the amount? How do
  you validate it works?
