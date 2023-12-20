Wherever there is modularity there is the potential for misunderstanding: Hiding information implies a need to check communication.

Module: A collection of services
Client: People who uses it 
Interface: Describes the available services of a module
Implementation: The details, including the source code of the module

In the context of C
Services: Functions
Interface: Header file (declarations)
Implementation: Source file (definitions)
Client: Source file (the ones that includes the interface)

Dividing a program into modules has several advantages:
- Abstraction
- Reusability
- Maintainability

Good module should have two properties:
- High cohesion
    The elements in module are closely related to each other
- Low coupling
    Modules should be independent of each other as possible. This makes it easier to modify the program and reuse modules

Types of modules:
- Data pool
   Collection of related variables and constants. For example, `<float.h>` and  `<limits.h>`
- Library
   Collection of related functions. For example, `<string.h>`
- Abstract object
   Collection of functions that operate on a hidden data structure
- Abstract Data Type (ADT)
   A type whose representation is hidden
   
   ADT 类似包装 Abstact Object，把它变成一种可以用来 declare 变数的 type，不然 Abstact Object 只有一个可以用
   
#### Incomplete Types
Types that describe objects but lack information needed to determine their sizes
Used for encapsulation

Using incomplete types to declare a variable is illegal
But declaring a pointer to object of an incomplete type is fine

```c
struct t;

struct t s;    /* WRONG */
struct t *s;   /* Legal */
```