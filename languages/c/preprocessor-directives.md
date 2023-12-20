Macro definition, `#define`
File inclusion, `#include`
Conditional compilation, `#if`, `#elif`, `#else`, `#ifdef`, `#ifndef`, `#endif`

#### Macro definition, `#define`

__Object-like macro__ (simple macro)
`#define identifier replacement-list`
replacement-list is any sequence of preprocessing tokens

__Function-like macro__ (parameterized macro)
`#define identifier(x1, x2, ..., xn) replacement-list`
`x1, x2, ..., xn` are identifiers / macro's parameters
```c
/* Example */
#define MAX(x, y) ((x) > (y)? (x): (y))
```

`#`
Performs "stringization", which converts a macro argument into a string literal
```c
/* Example */
#define PRINT_INT(x) printf(#x ": %d\n", x)

...

int i = 5;
PRINT_INT(i);   /* output: x: 5 */
```

`##`
Performs "token-pasting", which "paste" two tokens together to form a single token

`#undef` to undefine macro

Predefined Macros
```c
printf("__LINE__: %d\n", __LINE__);   /* 27 */
printf("__FILE__: %s\n", __FILE__);   /* test.c */
printf("__DATE__: %s\n", __DATE__);   /* Jun  6 2021 */
printf("__TIME__: %s\n", __TIME__);   /* 18:00:42*/
printf("__STDC__: %d\n", __STDC__);   /* 1 */

/* STDC: 1 if the compiler conforms to the C standard (C89, C99, (C11?))*/
```

`#error` Compiler terminates compilation when it reaches this line