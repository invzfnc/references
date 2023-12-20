#### Declaration Syntax
```none
declaration-specifiers declarator;
```

**Declaration specifiers** gives properties of the variable or function declared

Declaration specifiers fall into three categories
1. Storage classes
    `auto`, `register`,  `static`, `extern`
    Maximum 1, should come first in declaration
2. Type qualifiers
    `const`, `volatile`, `restrict` (C99)
3. Type specifiers
    `void`, `int`, `double`, `signed`, `unsigned`, `struct <tag>`
4. Function specifier (C99)
    `inline`
    
**Declarators** include identifiers, identifiers followed by `[]`, identifiers precided by `*`, and identifiers followed by `()`

#### Properties of Variables
##### Storage duration
When memory is set aside for the variable and when that memory is released
1. Automatic storage duration
    Allocated when the block executes, freed when the block ends
2. Static storage duration: 
    Stays at the same storage location as long as the program is running

##### Scope
Portion of program in which the variable can be referenced
1. Block scope
2. File scope

##### Linkage
The extent to which it can be shared by different parts of a program
1. External linkage
    May be shared by several (perhaps all) files in a program
2. Internal linkage
    Restricted to a single file
    If a variable with the same name appears in another file, it is treated as a different variable
 3. No linkage
     Belongs to a single function and can't be shared at all
     
By default, variables declared inside a block have automatic storage duration, block scope and no linkage. Variables declared outside any block, at the outermost level of a program, has static storage duration, file scope, and external linkage

#### Storage Classes
##### `auto`
Automatic storage duration, block scope, no linkage
Is legal only for variables that belong to a block
Is almost never specified explicitly

##### `static`
When used outside of block, it specifies that the variable has internal linkage. When used inside a block, the variable has static storage duration

A `static` variable inside a block is initialized only once (while `auto` variable is initialized every time the block is executed)

For recursive functions, the `static` variable is shared by all calls of the function

A function is legal to return a pointer to a `static` variable

##### `extern`
Static storage duration, ? linkage, the scope depends on the declaration's placement
Enables several source files to share the same variable
Using `extern` doesn't cause the compiler to allocate memory for the variable, it informs the compiler that that variable is defined elsewhere
Using initializers in `extern` declaration make it the same as normal declarations,  `extern int i = 0` is the same as `int i = 0`
Linkage: 
If the variable was declared `static`, then it has internal linkage, otherwise it has external linkage

##### `register`
Request the compiler to store the variable in register instead of the main memory
Is legal only for variables inside a block
Has the same properties as `auto` variable
`register` variables don't have addresses, the use of `&` is illegal

Best used for variables that are accessed of updated frequently

##### Functions
The only options are `extern` and `static`
`extern` allows the function to be called from other files
`static` indicates internal linkage

Specifying `extern` on functions serves no purpose, since that's already the default

Declare `static` functions for 
- Easier maintenance
- Reduced name space pollution

#### Type Qualifiers
`const` is for "read-only" variables
`volatile` is limited to low-level programming
`restrict` (C99) is only for pointers

#### Initializers
Initializers for variable with static storage duration must be constant
The initializer for an automatic structure or union can be another structure or union

Variables with static storage duration have the value zero by default. Pointer variables contain a null pointer

#### Inline Functions (C99)
