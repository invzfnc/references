#### Exponent methods
```java
Math.pow(a, b)  // a raised to the power of b (a^b)
Math.exp(x)     // e raised to the power of x (e^x)
Math.log(x)     // natural logarithm of x     (ln x, base e)
Math.log10(x)   // base 10 logarithm of x     (log x, base 10)
Math.sqrt(x)    // square root of x for x >= 0
```

#### Trigonometric methods
**Unit conversion between degree and radians**
```java
Math.toDegrees(radians);
Math.toRadians(degree);

// Examples
Math.toDegrees(0.5 * Math.PI) == 90.0;

Math.toRadians(90) == 1.5707963267948966;
1.5707963267948966 / Math.PI == 0.5;
```

**`sin`, `cos`, `tan` functions** takes angle in radians as parameter
```java
Math.sin(0);                // 0.0
Math.sin(Math.PI / 2);      // 1.0
Math.sin(Math.PI);          // 1.2246467991473532E-16 approx 0
Math.sin(Math.PI * 3 / 2);  // -1.0
Math.sin(Math.PI * 2);      // -2.4492935982947064E-16 approx 0

// Math.cos
// Math.tan
```

**`asin`, `acos`, `atan`** returns the angle in radians for the inverse of `sin`, `cos`, and `tan`.
```java
Math.asin(1) / Math.PI == 0.5;
// Math.acos
// Math.atan
```

#### Service methods
(`Math.min`, `Math.max` etc.)

- `min(a, b)` returns the minimum number of two numbers.
- `max(a, b)` returns the maximum number of two numbers.
- `abs(n)` returns the absolute value of the number.

- `random` generates a random `double` value greater than or equal to 0.0 and less than 1.0.

General formula for generating random integer
```java
a + (int)(Math.random() * b)
// Return a random integer between a and a + b - 1
```

#### Rounding methods
```java
Math.ceil(1.1) == 2.0
Math.floor(1.9) == 1.0
Math.rint(1.4) == 1.0
Math.rint(1.5) == 2.0
Math.round(1.5) == 2
```
- All methods other than `round` return as `double` value.
- `ceil` rounds up to its nearest integer.
- `floor` rounds down to its nearest integer.
- `rint` rounds to its nearest integer.
- `round` returns `(int)Math.floor(x + 0.5)` if `x` is a float and returns `(long)Math.floor(x + 0.5)` if `x` is a double.

