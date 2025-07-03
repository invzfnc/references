- `System.out` refers to the standard output device.
- `System.in` refers to the standard input device.

#### in
##### Initializing `Scanner` object for console input
```java
import java.util.Scanner;
Scanner input = new Scanner(System.in);
```
Without the `import` statement, need to type out `java.util.Scanner` instead of just `Scanner`.

##### Reading values of specific type
- `nextByte()`
- `nextShort()`
- `nextInt()`
- `nextLong()`
- `nextFloat()`
- `nextDouble()`

Example
```java
double radius = input.nextDouble();
```

##### Reading strings
- `next()` - reads a string that ends with a whitespace character
- `nextLine()` - reads a string that ends with the enter key pressed
From the official docs, `nextLine` advances this scanner past the current line and returns the input that was skipped.

##### To read a single character
```java
String s = input.nextLine();
char ch = s.charAt(0);
```

##### String comparison
- `equals(s)`
- `equalsIgnoreCase(s)`
- `compareTo(s)`
- `compareToIgnoreCase(s)`
- `startsWith(s_prefix)`
- `endsWith(s_suffix)`
- `contains(s)`

All methods above other than `compareTo` and `compareToIgnoreCase` returns boolean value. `compareTo` compares strings lexicographically and returns an integer greater than 0, equal to 0, or less than 0 to indicate whether this string is greater than, equal to, or less than `s`. `compareToIgnoreCase` is just `compareTo` but case insensitive.

##### Obtaining substrings
- `substring(beginIndex)` - returns substring from `beginIndex` to the end of string.
- `substring(beginIndex, endIndex)` - returns substring from `beginIndex` to `endIndex` (exclusive).

```java
jshell> String s = "substring"
s ==> "substring"

jshell> s.substring(3)
$1 ==> "string"

jshell> s.substring(3, 6)
$2 ==> "str"
```

Runtime error if `endIndex` is larger than `startIndex`.

##### Finding character or substring in string
- `indexOf(ch)` - returns the index of the first occurrence of `ch` in string.
- `indexOf(ch, fromIndex)` - returns the index of the first occurrence of `ch` after `fromIndex` in the string.
- `indexOf(s)` - searches for string `s` instead.
- `indexOf(s, fromIndex)` - searches for string `s` instead.
- `lastIndexOf(ch)` - returns the index of the last occurrence of `ch`.
- `lastIndexOf(ch, fromIndex)`
- `lastIndexOf(s)`
- `lastIndexOf(s, fromIndex)`

All these methods return `-1` if no match is found.

Example: Separating first name and last name
```java
String name = "John Doe";
int k = name.indexOf(" ");
String firstName = name.substring(0, k);  // John
String lastName = name.substring(k + 1);      // Doe
```

##### Conversion between strings and numbers
**String to number**
```java
// java.lang.Integer and java.lang.Double
int x = Integer.parseInt(s);
double y = Double.parseDouble(s);
```

**Number to string**
```java
// From book: Simply use string concatenation
String s = number + "";
```

Other ways
```java
String s = String.valueOf(12);    // "12"
String s = String.valueOf(12.3);  // "12.3"
```

https://stackoverflow.com/questions/5071040/java-convert-integer-to-string


##### Formatting console output
```java
System.out.printf("%4.2f", x);
```

See [conversion specification](../c/03-formatted-input-output.md)