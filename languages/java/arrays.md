##### Declaring array variable
```java
double[] arr;
double arr[];  // allowed, but not preferred
```
Array variables store only reference to the actual array. Value is initialized to null.

##### Creating array
```java
arr = new double[10];  // creates double array of size 10
```
Size can be a variable (eg `new double[n]`).

##### Declaration and creation of array in one line
```java
double[] arr = new double[10];
```

##### Array length
```java
arr.length
```
The size of an array cannot be changed after the array is created. The elements are assigned the default value of `0` (numeric), `\u0000` (`char`) and `false` (`boolean`).

##### Indexing
```java
arr[2] = arr[0] + arr[1];
```
An indexed variable can be used in the same way as a regular variable.

##### Array initializers
```java
double[] arr = {1.6, 2.4, 3.5, 4.7};
```

##### Creating copy of array
- Use loop to copy individual elements one by one
- Use `System.arraycopy(sourceArray, srcPos, targetArray, tarPos, length)`
- Use `clone` method

Example
```java
System.arraycopy(sourceArray, 0, targetArray, 0, sourceArray.length)
```

##### Anonymous array
```java
new double[]{1.1, 2.2, 3.3, 4.4};
```