```java
public class TestCircle {

    public static void main(String[] args) {
        Circle circle = new Circle(3.0);
        System.out.printf("Area: %.3f\n", circle.getArea());
        System.out.printf("Perimeter: %.3f\n", circle.getPerimeter());
    }
}

class Circle {
    double radius;

    /* Construct a circle object */
    Circle() {
        radius = 1;
    }

    /* Construct a circle object */
    Circle(double newRadius) {
        radius = newRadius;
    }

    /* Return the area of this circle */
    double getArea() {
        return radius * radius * Math.PI;
    }

    /* Return the perimeter of this circle */
    double getPerimeter() {
        return 2 * Math.PI * radius;
    }

    /* Set a new radius for this circle */
    void setRadius(double newRadius) {
        radius = newRadius;
    }
}

```

A Java file can contain more than one class, but it can have only one public class, and it must share the same name as the file.