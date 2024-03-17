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