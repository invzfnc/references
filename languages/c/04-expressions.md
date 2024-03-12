> One does not learn computing by using a hand calculator, but one can forget arithmetic

#### Arithmetic operators
Unary operators (involves one operand) `+` and `-`  
Binary operators (involves two operands)
- `+` addition
- `-` subtraction
- `*` multiplication
- `/` division
- `%` remainder

**Limitations**  
- `/` truncates the result when both of its operands are `int`s. Eg `1/2 == 0`
- `%` requires `int` operands or else the program won't compile
- Using `0` as the right operand of either `/` or `%` cause undefined behavior
- Results of `/` and `%` are implementation-defined

**Precedence and Association**  
See [here](./precedence-and-association.md)

#### Assignment operators
Assignment in C is an *operator* instead of a *statement*. The value of assignment `v = e` is the value of `v` *after* the assignment.

Most C operators don't modify their operands, but some do. These operators are said to have **side effects**, since they do more than just compute a value. For example, the assignment operator `=`.

Since assignment is an operator, several assignments can be chained together:
```c
i = j = k = 0;
// is equivalent to 
i = (j = (k = 0));
```

**L value** represents an object stored in computer memory, not a constant or the result of a computation. Variables are a type of lvalues. Assignment operator requires an lvalue as its left operand so expressions on the left side of an assignment expression like `i + j = 0`, `12 = i` and `-i = j`  are illegal.

**Compound assignment** operators allow us to shorten statements like `i = i + 2` into `i += 2`. There are ten compound assignment operators including:
- `+=`
- `-=`
- `*=`
- `/=`
- `%=`

The precedence of these operators are at the lowest (together with `=`). They are right associative, so 
```c
i += j += k;
// is equivalent to 
i += (j += k);
```

#### Increment and Decrement Operators
The increment, `++` and decrement, `--` operators have side effects. `++i` yields `i + 1` and, as a side effect, increments `i`. The post-increment operator `i++` on the other hand yields `i`(unmodified) and increments `i` afterwards.
```c
// Prefix increment
int i = 1;
printf("%d\n", ++i);  // "2"
printf("%d\n", i);    // "2"
```
```c
// Postfix increment
int i = 1;
printf("%d\n", i++);  // "1"
printf("%d\n", i);    // "2"
```
The `--` has similar properties
```c
int i = 1;
printf("%d\n", --i);  // "0"
printf("%d\n", i);    // "0"
```
```c
int i = 1;
printf("%d\n", i--);  // "1"
printf("%d\n", i);    // "0"
```

**Evaluating complex expression**
```c
a = b += c++ - d + --e / -f
a = b += (c++) - d + --e / -f
a = b += (c++) - d + (--e) / (-f)
a = b += (c++) - d + ((--e) / (-f))
a = b += ((c++) - d) + ((--e) / (-f))
a = b += (((c++) - d) + ((--e) / (-f)))
a = (b += (((c++) - d) + ((--e) / (-f))))
(a = (b += (((c++) - d) + ((--e) / (-f)))))
```