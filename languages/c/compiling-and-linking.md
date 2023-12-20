Converting C source code files to an executable program is normally done in two steps: **compiling** and **linking**.

First, the compiler converts the source code to object files (`*.o`). Then, the linker takes these object files, together with statically-linked libraries and creates an executable program.

In the first step, the compiler takes a **compilation unit**, which is normally a preprocessed source file (so, a source file with the contents of all the headers that it `#include`s) and converts that to an object file.

In each compilation unit, all the functions that are used must be **declared**, to let the compiler know that the function exists and what its arguments are. In your example, the declaration of the function `returnSeven` is in the header file `header.h`. When you compile `main.c`, you include the header with the declaration so that the compiler knows that `returnSeven` exists when it compiles `main.c`.

When the linker does its job, it needs to find the **definition** of each function. Each function has to be defined exactly once in one of the object files - if there are multiple object files that contain the definition of the same function, the linker will stop with an error.

Your function `returnSeven` is defined in `source.c` (and the `main` function is defined in `main.c`).

So, to summarize, you have two compilation units: `source.c` and `main.c` (with the header files that it includes). You compile these to two object files: `source.o` and `main.o`. The first one will contain the definition of `returnSeven`, the second one the definition of `main`. Then the linker will glue those two together in an executable program.

About linkage:

There is **external linkage** and **internal linkage**. By default, functions have external linkage, which means that the compiler makes these functions visible to the linker. If you make a function `static`, it has internal linkage - it is only visible inside the compilation unit in which it is defined (the linker won't know that it exists). This can be useful for functions that do something internally in a source file and that you want to hide from the rest of the program.

___

The C language has no concept of source files and header files (and neither does the compiler). This is merely a convention; remember that a header file is always `#include`d into a source file; the preprocessor literally just copy-pastes the contents, before proper compilation begins.

Your example _should_ compile (foolish syntax errors notwithstanding). Using GCC, for example, you might first do:

```
gcc -c -o source.o source.c
gcc -c -o main.o main.c
```

This compiles each source file separately, creating independent object files. At this stage, `returnSeven()` has not been resolved inside `main.c`; the compiler has merely marked the object file in a way that states that it must be resolved in the future. So at this stage, it's not a problem that `main.c` can't see a _definition_ of `returnSeven()`. (Note: this is distinct from the fact that `main.c` must be able to see a _declaration_ of `returnSeven()` in order to compile; it must know that it is indeed a function, and what its prototype is. That is why you must `#include "source.h"` in `main.c`.)

You then do:

```
gcc -o my_prog source.o main.o
```

This _links_ the two object files together into an executable binary, and performs resolution of symbols. In our example, this is possible, because `main.o` requires `returnSeven()`, and this is exposed by `source.o`. In cases where everything doesn't match up, a linker error would result.