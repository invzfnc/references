```java
public class TestCircle {

    public static void main(String[] args) {
        Circle circle = new Circle(3.0);
        System.out.printf("Area: %.3f\n", circle.getArea());
        System.out.printf("Perimeter: %.3f\n", circle.getPerimeter());
    }
}

class Circle {
    private double radius;

    /* Construct a circle object */
    Circle() {
        this(1.0);
    }

    /* Construct a circle object */
    Circle(double radius) {
        this.radius = radius;
    }

	/* Return radius */
	public double getRadius() {
	    return radius;
	}

	/* Set a new radius */
	public void setRadius(double newRadius) {
	    radius = (newRadius >= 0) ? newRadius : 0;
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

Objects are accessed via the object's **reference variables**, which contains references to the objects. (like arrays)

**Default value** of data fields if not specified:
- reference type: `null`
- numeric type: `0`
- `boolean`: `false`
- `char`: `\u0000`

**Static variables**
```java
static int x;
final static double PI = 3.14159265358979323846;
```

Instance methods can access/invoke both instance and static members, whereas static methods can access/invoke only static members.

**Visibility modifiers**
- `public`: accessible from any other classes
- default: accessible from any classes in the same package
- `private`: accessible only from within its own class (applies only to the members of a class)

To prevent users from creating objects from the Math class, the constructor in `java.lang.Math` is defined as `private Math() { ... }`

**Data encapsulation**: Private data field with public getter and setter methods (also referred to as an accessor and a mutator).

**`this` keyword** refers to the calling object. It can also be used inside a constructor to invoke another constructor of the same class. The `this` keyword is normally omitted for brevity. Nevertheless, the this keyword is needed to reference a data field hidden by a method or constructor parameter, or to invoke an overloaded constructor.

```java
private double radius = 1;
public void setRadius(double radius) {
	this.radius = radius;
}
```

**Inheritance** (is-a)
```java
public class Circle extends GeometricObject {
	...
}
```
`extends` does not allow multiple inheritance. Multiple inheritance can be achieved through interfaces.

**`super` keyword** refers to the superclass of the class in which `super` appears. It can be used to call a superclass constructor or a superclass method.

Unlike properties and methods, the constructors of a superclass are not inherited by a subclass. They can only be invoked from the constructors of the subclasses using the keyword `super`, and the call must be the first statement in the constructor.
```java
public Circle(double radius, String color, boolean filled) {
	super(color, filled);
	this.radius = radius;
}
```
If neither an overloaded constructor or its superclass constructor is invoked explicitly, the compiler automatically puts `super()` as the first statement in the constructor.

**`super.method(argument)`** to call superclass methods.

**Override annotation, `@Override`** denotes that the annotated method is required to override a method in its superclass. If the method annotated does not override its superclass's method, the compiler will report an error.

All classes derive from `Object`, which defines `toString`, which returns `"ClassName@memoryAddress"`. Calling `System.out.println(object)` is equivalent to calling `System.out.println(object.toString())`.