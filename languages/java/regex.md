```java
"Welcome to Java".matches(".* Java");  // true

String pattern = "\\d{3}-\\d{3,4}\\s*\\d{4}";
// 3 digits, 1 dash, 3-4 digits, 0 or more spaces, 4 digits
"011-1123 3445".matches(pattern);  // true
"011-112 3445".matches(pattern);   // true
"011-11233224".matches(pattern);   // true
```