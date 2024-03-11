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