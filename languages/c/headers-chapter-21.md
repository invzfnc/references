#### `stddef.h`
The header provides definitions of frequently used types and macros, it doesn't declare functions

`ptrdiff_t` result of subtraction between pointers
`size_t` result of `sizeof`
`wchar_t` a type large enough to represent all possible supported locales

`NULL` - In `locale.h`, `stdio.h`, `stdlib.h`, `string.h` and `time.h`

`offsetof`
A parameterized macro that computes the number of bytes between the beginning of the structure and the specified member
```c
struct s {
    int a;
    char b;
    float c;
};

offsetof(struct s, a);  // Guranteed to be 0
```


#### `stdbool.h`
Four macros
`bool` - `_Bool`
`true` - `1`
`false` - `0`
`__bool_true_false_are_defined` - `1`, could test this before defining our own version of `bool`, `true`, `false`

