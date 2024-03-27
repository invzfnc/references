> Make no mistake about it: Computers process numbers --- not symbols. We measure our understanding (and control) by the extent to which we can arithmetize an activity.

#### `int`
```c
/* int */

short int
unsigned short int  // == unsigned short

int
unsigned int  // == unsigned

long int
unsigned long int  // == unsigned long

/* On a 64-bit computer (usually):
 * short  16-bit
 * int    32-bit
 * long   64-bit
 *
 * These aren't mandated by the C standard and may vary
 * from one compiler to another.
 */
```

```c
/* Constant */

// long constant
15L 0377l 0x7fffL

// unsigned constant
15U 0377u 0x7fffU
```

#### Base
```c
/* Decimal */
15 255 07777

/* Octal */
017 0377 07777

/* Hexadecimal */
0xf 0xff 0x7fff
```