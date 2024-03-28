> Make no mistake about it: Computers process numbers --- not symbols. We measure our understanding (and control) by the extent to which we can arithmetize an activity.

#### `int`
```c
/* int types */

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
/* Writing constants */

/* type */

// long constant
15L 0377l 0x7fffL

// unsigned constant
15U 0377u 0x7fffU

/* base */

// decimal
15 255 07777

// octal
017 0377 07777

// hexadecimal
0xf 0xff 0x7fff
```

```c
/* Specifiers */

/** unsigned **/
unsigned int u;

/* base 10 */
scanf("%u", &u);
printf("%u", u);

/* base 8 */
scanf("%o", &u);
printf("%o", u);

/* base 16 */
scanf("%x", &u);
printf("%x", u);

/** short **/
short s;

// put letter h in front of d, o, u, or x
scanf("%hd", &s);
printf("%hd", s);

/** long **/
long l;

// put letter l in front of d, o, u, or x
scanf("%ld", &l);
printf("%ld", l);

/** long long **/
long long ll;

// put letters ll in front of d, o, u, or x
scanf("%lld", &ll);
printf("%lld", ll);
```

#### `float`, `double`
```c
/* floating-types */
float  // single-precision floating-point
double // double-precision floating-point
long double // extended-precision floating-point
```

Most modern computers follow the specifications in IEEE Standard 754 (aka IEC 60559).
- Single precision 32-bit, double precision 64-bit
- Numbers are stored in a form of scientific notation
- Each number have three parts: a sign, an exponent, and a fraction
- Exponent determines how large or small the numbers can be, fraction determines the precision
