Floating-point numbers have a limited precision and calculations. Equality test of two floating-point values is not reliable. However, we can compare whether they are close enough by testing whether the difference of the two numbers is less than some threshold. $\epsilon$, epsilon is commonly used to denote a very small value. Comparison of floats can be done as below:

```java
public class FloatEqualityTest {
    public static void main(String[] args) {
        double x = 1.0 - 0.1 - 0.1 - 0.1;
        System.out.println("x is " + x);
        System.out.println("x == 0.7 is " + (x == 0.5));
        
        // Very small difference, 1 * 10^-14
        final double EPSILON = 1E-14;

        // Correct way to test equality of two floating-point values
        if (Math.abs(x - 0.7) < EPSILON) {
            System.out.println(x + " is approximately 0.7");
        }
        else {
            System.out.println(x + " is not 0.7");
        }
    }
}

```