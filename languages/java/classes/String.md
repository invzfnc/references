```java
String s = "Hello, world!";

s.length()           // 13
s.charAt(5)          // ','
s.concat(" Again!")  // "Hello, world! Again!" (returns a new string)
s.toUpperCase()      // "HELLO, WORLD!"
s.toLowerCase()      // "hello, world!"
"  hi  ".trim()      // "hi" (trims whitespace characters)
s.replace("o", "O")  // "HellO, wOrld!" (takes char or CharSequence)
s.replaceFirst("o", "O")  // "HellO, world!" (takes regex string)
s.split(", ")        // String[2] { "Hello", "world!" } (takes regex string)
```

String objects
```java
// string from array of char
String s = new String(new char[]{'H', 'e', 'l', 'l', 'o'});

// s1, s3: interned strings
// s2, s4: string objects
String s1 = "Java";
String s2 = new String("Java");
String s3 = "Java";
String s4 = new String("Java");

s1 == s2;  // false
s1 == s3;  // true
s2 == s4;  // false
```