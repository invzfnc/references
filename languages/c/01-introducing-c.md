*Reference: C Programming: A Modern Approach, Second Edition by K. N. King*

> When someone says "I want a programming language in which I need only say what I wish done," give him a lollipop.

**Portability**
- C, developed at Bell Labs in early 1970s, by Ken Thompson, Dennis Ritchie, and others.
- UNIX was written in assembly, Thompson wrote B to further develop UNIX (B based on BCPL, and BCPL is based off Algol 60).
- Ritchie joined UNIX project and programmed in B, Thompson rewrote a portion of UNIX in B.
- By 1971, it became apparent that B is not well-suited to the PDP-11.
- Ritchie began to develop the extended version of B, called the NB (New B).
- It began to diverge more from B, he changed the name to C.
- By 1973, C was stable enough that UNIX could be rewritten in C.
- Portability: By writing C compilers, the team could get UNIX running on those others machines as well.

**Standardization**
- In 1978, Brian Kernighan and Dennis Ritchie wrote *The C Programming Language*, known as K&R, which served as the de facto standard. 
- Programmers wrote compilers based on K&R. Some parts were fuzzy and compilers often treated these features differently.
- K&R also failed to make clear distinctions between which features belonged to C and which were part of the UNIX.
- C continued to change after K&R was published, with new features added and some old features removed.
- ANSI (American National Standards Institute) began development of C standard by 1983. It was approved in 1989 as ANSI standard X3.159-1989.
- This version was approved by the International Organization for Standardization as an international standard ISO/IEC 9899:1990. This version of C is often referred to as C89 or C90. Before this is K&R C.
- C underwent a few changes in 1995. More changes occurred with the publication of a new standard, ISO/IEC 9899:1999, in 1999, known as the C99 standard.