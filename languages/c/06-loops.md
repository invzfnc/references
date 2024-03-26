> A program without a loop and a structured variable isn't worth writing.

#### `while`
```c
while ( expression ) statement
```

```c
// With compound statement
while (i > 0) {
	printf("T minus %d and counting\n", i);
	i--;
}
```
Controlling expression is tested before the loop body is executed.

**Infinite loops**
```c
while (1) ...
```

#### `do`
```c
do statement while ( expression ) ;
```
The loop body is executed first, then the controlling expression is evaluated to determine if the loop should continue or terminate.

```c
do {
	printf("T minus %d and counting\n", i);
	i--;
} while (i > 0);
```

#### `for`
```c
for ( expr1 ; expr2 ; expr3 ) statement
```

```c
// is equivalent to
expr1;
while (expr2) {
	statement
	expr3;
}
```

```c
for (i = 10; i > 0; i--)
	printf("T minus %d and counting\n", i);
```

**Omitting expressions in `for` statement**
```c
// omitting the first expression
i = 10;
for (; i > 0; --i)
	printf("T minus %d and counting\n", i);
// no initialization is performed before the loop is executed
```

```c
// omitting the third expression
for (i = 10; i > 0;)
	printf("T minus %d and counting\n", i--);
```

```c
// omitting the first and third expressions
// makes it equivalent to a while loop
for (; i > 0;)
	printf("T minus %d and counting\n", i--);

while (i > 0)
	printf("T minus %d and counting\n", i--);
```

**Declaring variable for use in loop**
```c
for (int i = 0; i < n; i++)
	...

// declaring multiple variables in for statement
for (int i = 0, int j = 0; i < n; i++)
	...
```
The statement creates a new version of `i` that will be used solely within the loop. This variable is not visible outside the body of the loop.

#### `,` (comma operator)
```c
expr1 , expr2
```
`expr1` is evaluated, then `expr2` is evaluated, the value of `expr2` is returned for the whole expression (`(expr1, expr2)`).

```c
string s;
while (read_string(s), s.len() > 5)
	...

// is equivalent to

string s;
read_string(s);
while (s.len() > 5)
{
	read_string(s);
	...
}

// from
// https://stackoverflow.com/questions/52550/what-does-the-comma-operator-do
```

#### `break` and `continue`
```c
for (int d = 2; d < n; d++)
	if (n % d == 0)
		break;

if (d < n)
	printf("%d is divisible by %d\n", d);
else
	printf("%d is prime\n", d);
```

`break` transfers control just *past* the end of a loop, while `continue` transfers control to a point just *before* the end of a loop. The loop continues after `continue`.

#### `goto`
```c
// identifier
identifier : statement

// goto
goto identifier ;
```

```c
for (d = 2; d < n; d++)
	if (n % d == 0)
		goto done;

done:
if (d < n)
	printf("%d is divisible by %d\n", n, d);
else
	printf("%d is prime\n", n);
```

`goto` is rarely needed in everyday C programming, `break`, `continue`, and `return`, which are essentially restricted `goto` statements are sufficient to handle most situation that might require a `goto` in other languages.

`goto` can be helpful once in a while - exiting loop form within a `switch` statement
```c
while (...) {
	switch (...) {
		goto loop_done;  // break won't work here
	}
}
loop_done: ...
```

#### Null statement
```c
// This line contains three statements
// Statements can be null
i = 0; ; j = 1;
```

```c
for (d = 2; d < n; d++)
	if (n % d == 0)
		break;

// is equivalent to 

for (d = 2; d < n && n % d != 0; d++)
	;  // empty loop body
```