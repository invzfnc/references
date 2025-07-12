```java
+Date() // constructs object of current time
+Date(elapsedTime: long) // constructs object of given time in milliseconds since epoch

+toString(): String // returns string representing the date and time
+getTime(): long // returns number of milliseconds since epoch

+setTime(elapsedTime: long): void // sets a new elapse time in the object
```

```java
java.util.Date date = new java.util.Date();
// Sat Jul 12 14:34:23 MYT 2025

date.toString()
// "Sat Jul 12 14:34:23 MYT 2025"

date.getTime()
// 1752302063907
```
