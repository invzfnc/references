## Packed BCD (TBYTE) Data

10 bytes. Each half byte contain 1 decimal digit. Highest bit indicates the number sign.

Constant initializers must use hexadecimal.

```asm
intVal TBYTE 800000000000001234h  ; valid
intVal TBYTE -1234                ; invalid 
```