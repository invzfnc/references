```java
+Random() // constructs a Random object with the current time as seed
+Random(seed: long) // with specified seed

+nextInt(): int
+nextLong(): long
+nextDouble(): double // returns a random double value bewteen 0.0 and 1.0 (exclusive)
+nextFloat(): float // returns a random float value between 0.0F and 1.0F (exclusive)
+nextBoolean(): boolean

+nextInt(n: int) // returns a random int value between 0 and n (exclusive)
+nextFloat(n: float)
...
```

```java
java.util.Random random = new java.util.Random()
// java.util.Random@2833cc44

random.nextInt()
// -1467826511

random.nextLong()
// -3933587135022441772

random.nextDouble()
// 0.6372039765735484

random.nextBoolean()
// false

random.nextInt(100)
// 69
```