This is intended to be a self-paced course that teaches enough operating
systems fundamentals for you to decide if you like operating systems or not :)

With a couple hours' effort per week, a proficient C programmer can probably
get through this in about 18 weeks total, with plenty of time for questions and
side quests.  You pick how much effort you want to put into it, that's what
you'll get back out.

You should first clone the sources from

```
git clone https://github.com/mit-pdos/xv6-riscv.git
```

Then should bookmark/download the
[xv6 book](https://pdos.csail.mit.edu/6.1810/2024/xv6/book-riscv-rev4.pdf) as
most of the readings will be from that.  It is meant to be read along with the
source code, which is small enough that you can e.g. `grep -R usleep` and find
the implementation.

Both of those are (essentially) linked from the
[6.1810](https://pdos.csail.mit.edu/6.1810/2024/xv6.html) page if you want to
fuss with pdflatex to get the latest version (6.828 seems to have been renamed
6.1810 and `rev4` from 2024-08-31 is the most recent prebuilt version available).

* [Week 1](week01.md)
* [Week 2](week02.md)
* [Week 3](week03.md)
* [Week 4](week04.md)

## Notes for people taking this in Jan/Feb 2025 on slack

I'm committing to coordinating these readings and thought-provoking questions
for 6 weeks, at which point we'll regroup and figure out if the format is
working for enough people.  If you can commit to 6 weeks too, great, I'll send
you a gold star penguin sticker or something.

If it turns out this isn't your thing, no big deal.  If you miss a week, or
start late, just read back in slack, no big deal.  Like all MOOCs I don't
expect the completion rates to be anywhere near 100%, and you get back what you
put in.

My expectation is this will take a total of 18 weeks to cover adequately, given
time for questions and side quests.

You'll want a computer that you can run `qemu` on -- a Mac is fine, as long as
you have Homebrew (see Week 1 for setup instructions).

## Format

I'm not going to lecture at you.  I know operating systems pretty well, as do
other people who might help, and I'm happy to provide advice or tell stories.

The "Questions" section is structured somewhat like TAOCP's exercises or a
Socratic dialogue's examples, while "Assignments" is more of a typical "do
this."  I won't be grading things but if you want to ask the group about how
you solved it, go for it.

## Concrete Goals

* Be able to pass a systems interview
* Understand in more detail choices made in POSIX.  This isn't always due to
  the principle of minimal sufficiency, often it's historical baggage.
* Read some actual source code, and be familiar enough to go from the xv6 impl
  to FreeBSD's or Linux's equivalent one.
* Understand clearly the distinction between kernel, library, and user code.

## Timing

The week's plan will be finalized on Wednesday evenings.  This is a live repo
and will change over time, so if you're reading ahead, *caveat emptor*.

## Reporting issues

Please use the github issue tracker if you find something is incorrect, or take
issue with an assignment's usefulness.  For big-picture things, there will be a
survey at the end, and for troubleshooting please use the studygroup slack channel.
