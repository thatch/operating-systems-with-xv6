This is intended to be a self-paced course that teaches enough operating
systems fundamentals for you to decide if you like operating systems or not :)

With a couple hours' effort per week, a proficient C programmer can probably
get through this in about 18 weeks total, with plenty of time for questions and
side quests.  You pick how much effort you want to put into it, that's what
you'll get back out.

You should first clone the sources from

```
$ git clone https://github.com/mit-pdos/xv6-riscv.git
```

Then should bookmark/download the
[https://pdos.csail.mit.edu/6.828/2023/xv6/book-riscv-rev3.pdf](xv6 book) as
most of the readings will be from that.  It is meant to be read along with the
source code, which is small enough that you can e.g. `grep -R usleep` and find
the implementation.

Both of those are (essentially) linked from the
[6.1810](https://pdos.csail.mit.edu/6.1810/2024/xv6.html) page if you want to
fuss with pdflatex to get the latest version (6.828 seems to have been renamed
6.1810, and `rev3` is the most recent one I can find prebuilt)

* [week01.md](Week 1)
* [week02.md](Week 2)
