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
