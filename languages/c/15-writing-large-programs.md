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
- 