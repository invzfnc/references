> Around computers it is difficult to find the correct unit of time to measure progress. Some cathedrals took a century to complete. Can you imagine the grandeur and scope of a program that would take as long?

#### Source files
- The C standard uses the term "source file" to refer to all files written by the programmer, including both `*.c` and `*.h` files. In this context source files only refer to `*.c` files.
- Must contain function named `main`.
- Contain part of the program, primarily definitions of functions and variables.
- Example (Reverse Polish notation, RPN calculator): `stack.c` contains `push`, `pop`, `make_empty`, `is_empty`, `is_full`, while `calc.c` contains `main`

Advantages of splitting a program into multiple source files
- Grouping related functions and variables into a single file helps clarify the structure of the program.
- Each source file can be compiled separately - a great time-saver if the program is large and must be changed frequently.
- Functions are more easily reused in other programs when grouped in separate source files.

#### Header files
- Or include files, by convention has the extension `*.h`.
- `#include` directive tells the preprocessor to open a specified file and insert its contents into the current file.

##### `#include` directives
- `#include <filename>` for C's own library. Compiler searches the directory in which system header files reside (`/usr/include` on UNIX systems)
- `#include "filename"` for all other header files. Compiler searches the current directory, then search the directory in which system header files reside.
- The places to be searched for header files can usually be altered, using command-line option `-Ipath`
- `#include "c:\cprogs\utils.h"` is a valid include path, the preprocessor does not treat them as escape sequence in string literals.
- `#include tokens`, where `tokens` is any sequence of preprocessing tokens
	```c
	#if defined(IA32)
		#define CPU_FILE "ia32.h"
	#elif defined(IA64)
		#define CPU_FILE "ia64.h"
	#elif defined(AMD64)
		#define CPU_FILE "amd64h"
	#endif
	
	#include CPU_FILE
	```

- Macro and type definitions that are intended to be shared by several source files should go into header files.
- Include the header file declaring a function `f` in the source file that contains `f`'s definition

Example
```c
/* stack.h */

void make_empty(void); // Declares the function
int is_empty(void);
int is_full(void);
void push(int i);
int pop(void);
```

```c
/* calc.c */

#include "stack.h"

int main(void)
{
	make_empty(); // Calls the function
}
```

```c
/* stack.c */

#include "stack.h"

int contents[100];
int top = 0;

void make_empty(void) // Defines the function
{ ... }

int is_empty(void)
{ ... }

int is_full(void)
{ ... }

void push(int i)
{ ... }

int pop(void)
{ ... }
```

#### Sharing variable declaration (`extern` variables)
```c
int i; // Declares i and defines it as well
```

To declare `i` without defining it, use the keyword `extern` at the beginning of its declaration.
```c
extern int i; // Declares i without defining it
```

`extern` informs the compiler that `i` is defined elsewhere in the program (most likely in a different source file), so there's no need to allocate space for it. It works with variable of all type, when used in declaration of an array, we can omit the length of the array.
```c
extern int a[]; // Compiler doesn't allocate space, thus length is not needed
```

#### Protecting header files (from multiple inclusion)
Multiple inclusion example: `file1.h` includes `file3.h`, `file2.h` includes `file3.h`, `main.c` includes  `file1.h` and `file2.h`. When `main.c` is compiled, `file3.h` will be compiled twice.

If the file contains a type definition, it will raise compilation error.

Safe even when included more than once:
- Macro definitions
- Function prototypes
- Variable declarations

To protect a header file:
```c
#ifndef FILE3_H
#define FILE3_H
... // Other declarations
#endif
```

When this `file3.h` is included the first time, `FILE3_H` macro won't be defined, so the preprocessor will allow the lines between `#ifndef` and `#endif` to stay. If the file should be included a second time, the preprocessor will remove the lines between `#ifndef` and `#endif`.

#### `#error` directives
`#error` directives are often put in header files to check for conditions under which the header file shouldn't be included.

For example, to prevent the header file from being used with older, nonstandard compilers:
```c
#ifndef __STDC__
#error This header requires a Standard C Compiler
#endif
```

#### Defining macros outside a program
```sh
gcc -DDEBUG=1 foo.c
```
equals
```c
#define DEBUG 1
```