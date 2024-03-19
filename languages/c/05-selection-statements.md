> Programmers are not to be measured by their ingenuity and their logic but by the completeness of their case analysis.

#### Type of statements
- **Selection statements**, `if` and `switch`
- **Iteration statements**, `while`, `do`, `for`
- **Jump statements**, `break`, `continue`, `return` and `goto`
- **Compound statements**
- **Null statement**

#### Logical expressions
**Relational operators**
- `<`, less than
- `>`, greater than
- `<=`, less than or equal to
- `>=`, greater than or equal to

The precedence of the relational operators is lower than that of the arithmetic operators, and they are left associative.
```c
i < j < k;
// is equivalent to 
(i < j) < k;

// To test whether j lies between i and k
i < j && j < k;
```

These statements produce either `0` (false) or `1` (true).

**Equality operators**
- `==`, equal to 
- `!=`, not equal to 

These statements produce either `0` (false) or `1` (true).

**Logical operators**
- `!`, logical negation
- `&&`, logical and
- `||`, logical or

`!` is unary and right associative. 
`&&` and `||` perform "short-circuit" evaluation of their operands. If the value of the expression can be deduced form the value of the left operand alone, then the right operand isn't evaluated.
```c
(i != 0) && (j / i > 0)  // is safe
```

#### Selection statements
##### `if`
```c
if ( expression ) statement
// The parentheses are mandatory
```
When an `if` statement is executed, the expression is evaluated; if the value of the expression is nonzero, the statement after the parentheses is executed.

##### `else`
```c
if ( expression ) statement else statement
```

**Cascaded `if` statements**  
Testing a series of conditions, stopping as soon as one of them is true
```c
if (n < 0)
    printf("n is less than 0\n");
else if (n == 0)
	printf("n is equal to 0\n");
else
	printf("n is greater than 0\n");
```
(Cascaded `if` statement isn't some new kind of statement, it's just an ordinary `if` statement that happens to have another `if` statement as its `else` clause)

##### Conditional expressions
```c
expr1 ? expr2 : expr3
```
`expr1` is evaluated first; if its value isn't zero, then `expr2` is evaluated, and its value is the value of the entire conditional expression. If the value of `expr1` is zero, then the value of `expr3` is the value of the conditional.

```c
int i, j, k;
i = 1;
j = 2;
k = i > j ? i : j;       // k == 2
k = (i >= 0 ? i : 0) + j // k == 3
```

```c
return i > j ? i : j;

// equivalent to 

if (i > j)
	return i;
else
	return j;
```

```c
printf("%d\n", i > j ? i : j);

// equivalent to 

if (i > j)
	printf("%d\n", i);
else
	printf("%d\n", j);
```

##### Booleans
```c
/* C89 */
#define BOOL int
#define TRUE 1
#define FALSE 0

BOOL flag = TRUE;

/* C99 */
_Bool flag;  // unsigned int type, either 1 or 0
flag = 5;    // flag is assigned 1

/* C99 */
#include <stdbool>
bool flag;
flag = false;
flag = true;
```

The C89 standard specifies that names beginning with an underscore followed by an uppercase letter are reserved for future use and should not be used by programmers.

#### `switch`
```c
switch ( controlling_expression ) {
    case constant_expression : statements
    ...
    case constant_expression : statements
    default : statements
}
```
- `controlling_expression` must be integer expression.
- Characters are treated as integers in C and thus can be tested in `switch` statements.
- Floats and strings don't qualify.
- `constant_expressions` can't contain variables or function calls.
- `default` isn't required in `switch` statements.

```c
if (grade == 4)
	printf("Excellent");
else if (grade == 3)
	printf("Good");
else if (grade == 2)
	printf("Average");
else if (grade == 1)
	printf("Poor")
else if (grade == 0)
	printf("Failing")
else
	printf("Illegal grade")

// can be written as

switch (grade) {
	case 4:  printf("Excellent");
			 break;
	case 3:  printf("Good");
			 break;
	case 2:  printf("Average");
			 break;
	case 1:  printf("Poor");
			 break;
	case 0:  printf("Failing");
			 break;
	default: printf("Illegal grade");
			 break;
}
```

`breaks` breaks out of the `switch` statement. When the controlling expression is evaluated, control jumps to the case label matching the value of the `switch` expression, then proceeds until the `break` statement.