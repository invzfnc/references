Data structure containing elements (data values) that belongs to one same type
> In this business, you're always off by one.

#### Declaration
```c
/* The simplest declaration */
int a[10];   
/* 1D Array, with the length of 10, containing int typed values */
```

```c
/* Good practice using macros */
#define N 10
int a[N];
```

#### Subscripting
Or Indexing, to access a particular element of an array

```c
a[0];   /* Access the first element of an array */ 
```

#### Idioms
Assuming `N` is the macro defining the length of array and `a` is the array

Clearing (Setting all elements to 0)
```c
for (i = 0; i < N; i++)
	a[i] = 0;
```

Reads data from input into array
```c
for (i = 0; i < N; i++)
	scanf("%d", &a[i]);
```

Sums the elements of an array
```c
int sum = 0;
for (i = 0; i < N; i++)
	sum += a[i];
```

#### Case: Over-indexing
Suppose that `a` is an array with the length of 10 and indexing is done from `1` to `10` instead of `0` to `9`
```c
int a[10], i;

for (i = 1; i <= 10; i++)
	a[i] = 0;
```

With some compilers, this might cause an infinite loop
When `i` reaches `10`, `0` is stored into the memory next to `a[9]`, which doesn't exist
If `i` happens to be in the memory right after where `a[9]` is, `i` will be set to `0`, causing the loop to go on forever

#### Initializers
Common form
```c
int a[] = {0, 1, 2, 3, 4, 5};
```

If the length of initializer is shorter than the length of array, the elements will be set to `0` by default

To set all elements to zero
```c
int a[10] = {0}
```

__Designated Initializers (C99)__

```c
int a[] = {[0] = 1, 2, [4] = 1};
```

The code above will create an array `{1, 2, 0, 0, 1}`
Each number in brackets are called the "designator"

#### Macros
```c
#define N (sizeof(arr) / sizeof(arr[0]))
int arr[10];
```

#### Multi-Dimensional Array
```c
int a[2][3] = {{1, 1, 1}, 
			   {1, 1, 1}}
```
or
```c
int a[2][3] = {1, 1, 1, 
			   1, 1, 1}
```

#### Constant Arrays
Constant arrays shouldn't be modified
```c
const char hex_chars[] = 
{'0', '1', '2', '3', '4', '5', '6', '7', '8', '9'
'A', 'B', 'C', 'D', 'E', 'F'}
```

Advantages of declaring a `const` array
- Documents that the program won't modify the array
- Helps the compiler catch errors, by informing it that we don't intend to modify the array

#### Variable-Length Arrays / VLA (C99)
Basically,
(let `n` be the variable with the type `int` and `arr` as the array)
`scanf` the length of array (from user input) into variable `n`
construct the array using `arr[n]`

#### Array Assignment
Don't do assignment like this: 
```c
/* Assuming that a and b are both arrays */
a = b;
```

Use a loop to assign
```c
/* Assuming that N is the length of array a */
for (int i = 0; i < N, i++)
	a[i] = b[i]
```

Or, use the `memcpy` (memory copy) function from `<string.h>` header
```c
memcpy(a, b, sizeof(a))
```

#### goto statement with VLA
C99 doesn't allow a `goto` statement to bypass the declaration of a variable-length-array
The memory used to store a VLA is reached during program execution. Bypassing the declaration using a `goto` statement could result in a program accessing the elements of an array that was never allocated.
