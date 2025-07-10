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

**Constructor**
- Must have the same name as the class itself.
- Does not have a return type, not even `void`.
- Is invoked using the `new` operator when an object is created.

A default constructor will be provided when there is no constructor explicitly defined in the class.

Objects are accessed via the object's reference variables, which contains references to the objects. (like arrays)

Default value of data fields if not specified:
- reference type: `null`
- numeric type: `0`
- `boolean`: `false`
- `char`: `\u0000`