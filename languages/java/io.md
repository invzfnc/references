- `System.out` refers to the standard output device.
- `System.in` refers to the standard input device.

To perform console input
```java
import java.util.Scanner;
Scanner input = new Scanner(System.in);
```
- without the `import` statement, need to type out `java.util.Scanner` instead of just `Scanner`.

To take a `double` value
```java
double radius = input.nextDouble();
```

Other methods of `Scanner` object
```java
nextByte()
nextShort()
nextInt()
nextLong()
nextFloat()
nextDouble()
```