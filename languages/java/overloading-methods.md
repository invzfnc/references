Defining methods with the same name as long as their **parameter lists** are different.

Example
```java
public static int max(int n1, int n2) { ... }
public static int max(int n1, int n2, int n3) { ... }
public static double max(double n1, double n2) { ... }
public static double max(double n1, double n2, double n3) { ... }
```

**Ambiguous invocation**: When there are two or more possible matches for the invocation of a method, but the compiler cannot determine the most specific match. Causes compile error.