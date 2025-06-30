Casting is an operation that converts a value of one data type into a value of another data type.

Casting a type with a small range to a type with a larger range is known as *widening a type*. Casting a type with a large range to a type with a smaller range is known as *narrowing a type*. Java automatically widens a type, but must narrow a type explicitly. 

```java
jshell> int a = (int)1.9
a ==> 1
```

A compile error will occur when narrowing a type without casting
```java
jshell> int a = 1.9
|  Error:
|  incompatible types: possible lossy conversion from double to int
|  int a = 1.9;
|
```