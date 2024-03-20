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
