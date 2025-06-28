- Every Java program must have at least one class.
- By convention, class names starts with an uppercase letter.
- The `main` method is the entry point where the program begins execution.
- Source file must have the same exact name as the public class name.

```java
public class Hello {
    public static void main(String[] args) {
        System.out.println("Hello, world!");
    }
}
```

To run the script
```sh
javac Hello.java
java Hello
```
`javac` compiles `Hello.java` into `Hello.class`, `java` launches the Java virtual machine, executes the bytecodes that the complier placed in the class file.

Printing
- `System.out.print` prints without newline at the end.
- `System.out.println` prints with newline at the end.
