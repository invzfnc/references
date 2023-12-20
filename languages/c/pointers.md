Pointer variables: Variables that hold address of another variable

#### Declaration, Initialization
Pattern `type *var`

```c
int *p;
double *q;
char *r;

int i = 0;
p = &i;

```

#### Address (`&`), Indirection Operator (`*`)
`&` reveals the address a variable
```c
int i;
&i;   /* Address of i */
```

`*` 
- Declaration
- Revealing object of a pointer variable / Access value in variable that it points to
```c
int i = 0;
int *p = &i;   /* Declare p and point it to i */
*p;   /* Access value of i, 0 in this case */
```

__What about using both?__

Consider:
```c
int i = 0;
int j;
j = *&i;
```
`j = *&i` is the same as `j = i`
Think of it as: value of (address of `i`)

#### Assignment
1. `*pointer` is a lvalue, assignment to it will modify the value of the variable it points to

2. Consider:
	```c
	int i = 0;
	int *p = &i, *q;
	q = p;
	```
	A pointer variable can be assigned with another pointer, making them both point to the same object (in this case, `p` and `q` points to `i`)
3. `*p = *q`
	`p`'s variable will be assigned with the value in `q`'s variable
	

#### Argument, Return Value
__Argument__
Function declaration that takes pointer as argument can be written as:
```c
void f(int *x)
```

Calling it would be:
```c
int x = 0;
f(&x);
```
`f` has access to the variable `x` 

__Return Value__
Never return pointers to automatic local variables, the pointer will be invalid
Pointers to external variables, or local variable that has been declared `static` are fine

#### `const` Keyword
```c
void f(const int *x)
void f(int * const x)
void f(const int * const x)
```

__Statement 1__
`const` indicates that `x` is a pointer to a "constant integer"
`f` can't change the integer that `x` points to (`p` is still changable), so statement such as `*x = 5` will not be accepted

__Statement 2__
`x` is protected instead, but not the variable it points to
`*x = 5` will be legal
`x = y` is not

__Statement 3__
Both the pointer and variable are protected