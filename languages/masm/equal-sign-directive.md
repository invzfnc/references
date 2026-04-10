### Symbolic constants

```asm
name = expression

COUNT = 500
mov eax, COUNT
```

Usually the expression is a 32-bit integer value (DWORD). It is read by the assembler, all occurrences of `name` will be replaced by `expression` during the assembler's preprocessor step.

(Think `#define` in C)

The `$` symbol is called the *current location counter*.

```asm
selfPtr DWORD $
; declares variable named selfPtr and initializes with the variable's offset value
```