> If a program manipulates a large amount of data, it does so in a small number of ways.

#### One-dimensional arrays
An array is a **data structure** containing data values (**elements**), all of which have the **same type**.

**Declaration**
```c
int a[10];  
// declares array a has 10 elements of type int
```

**Initialization**
```c
int a[10] = {1, 2, 3, 4, 5, 6, 7, 8, 9};
int b[5] = {1, 2, 3};  // {1, 2, 3, 0, 0}
int c[5] = {0};  // {0, 0, 0, 0, 0}
int d[] = {1, 2, 3, 4, 5}

bool is_x[10] = {false};  // 10 falses
```

**Subscripting/Indexing**
```
a[10] contains 10 elements:
a[0], a[1], a[2], a[3], a[4], 
a[5], a[6], a[7], a[8], a[9]
```

```c
a[0] = 1;
printf("%d\n", a[5]);
```

**Idioms**
```c
// clears a
for (i = 0; i < N; i++)
	a[i] = 0;

// reads data into a
for (i = 0; i < N; i++)
	scanf("%d", &a[i]);

// sums the elements of a
for (i = 0; i < N; i++)
	sum += a[i];

// looping through array of unknown size
for (i = 0; i < sizeof(a) / sizeof(a[0]); i++)
	...
// to avoid warning for comparing int and size_t
for (i = 0; i < (int) (sizeof(a) / sizeof(a[0])); i++)
```

**Designated initializers (C99)**
```c
int a[15] = {[2] = 29, [9] = 7, [1] = 0};
// other elements are initialized with value 0
// each number in brackets is a designator
```

#### Multidimensional arrays
**Declaration**
```c
int m[x][y];
// x rows, y columns
```

**Initialization**
```c
int a[3][2] = {{1, 1, 0},
			   {0, 1 ,0}};
int b[3][2] = {1, 1, 0,   // omit braces: fill element by
			   0, 1 ,0};  // element, when full switch row 
```

**Designated initializers (C99)**
```c
double ident[2][2] = {[0][0] = 1.0, [1][1] = 1.0};
// other elements are default to 0
```
**Visualization**
```
// say x=3, y=2, int m[3][2], elements as o
// visualisation:
o o o
o o o

// in memory (row-major order)
o o o o o o
```

```c
/* identity matrix */

#define N 10

double ident[N][N];
int row, col;

for (row = 0; row < N; row++)
	for (col = 0; col < N; col++)
		if (row == col)
			ident[row][col] = 1.0;
		else
			ident[row][col] = 0.0;
```

#### Constant arrays
```c
const char hex_chars[] = 
{'0', '1', '2', '3', '4', '5', '6', '7', '8', '9',
 'A', 'B', 'C', 'D', 'E', 'F'};
```

#### Variable-length arrays (C99)
```c
int n;
int a[n];  // length of array depends on n
```
- VLAs can be multidimensional
- VLAs can't have static storage duration
- VLAs may not have an initializer (restriction)

#### Extras
**Copying arrays**
```c
for (i = 0; i < N; i++)
	a[i] = b[i];

// or

#include <string.h>
memcpy(a, b, sizeof(a));
```