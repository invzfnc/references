#### Concept
- **Non-singleton pattern:** We create objects like we are using a cookie cutter. Every cookie is new and separate. Take a bite of the cookie, the other cookies remain untouched.
- **Singleton pattern:** Ensures that the class yield only one specific instance/cookie. All classes are handed the same cookie. 

#### Implementation
1. Make the public constructor private to prevent other classes from creating a second instance.
2. The class will hold that single instance. Define a private static variable to hold that instance.
3. Define a public static method to return the private instance. In this method, initialize the instance if it is null, then return the instance.