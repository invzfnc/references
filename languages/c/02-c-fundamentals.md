> One man's constant is another man's variable.

#### Compiling and Linking
- Preprocessing: The **preprocessor** obeys commands that begin with `#` (**directives**)
- Compiling: The **compiler** translates the program into machine instructions (**object code**)
- Linking: The **linker** combines the object code produced by the compiler with any additional code needed to yield a complete executable program. This additional code includes library functions that are used in program.

#### Comments
```c
// This is a comment

/*Lorem ipsum dolor sit amet, consectetur adipiscing elit.*/
/*Lorem ipsum dolor sit amet, consectetur adipiscing elit.*/
/*Lorem ipsum dolor sit amet, consectetur adipiscing elit.*/

/* Lorem ipsum dolor sit amet, consectetur adipiscing elit.
   Lorem ipsum dolor sit amet, consectetur adipiscing elit.
   Lorem ipsum dolor sit amet, consectetur adipiscing elit. */

/* Lorem ipsum dolor sit amet, consectetur adipiscing elit.
   Lorem ipsum dolor sit amet, consectetur adipiscing elit.
   Lorem ipsum dolor sit amet, consectetur adipiscing elit.
*/

/************************************************************
*  Lorem ipsum dolor sit amet, consectetur adipiscing elit. *
*  Lorem ipsum dolor sit amet, consectetur adipiscing elit. *
*  Lorem ipsum dolor sit amet, consectetur adipiscing elit. *
*************************************************************/

/* Lorem ipsum dolor sit amet, consectetur adipiscing elit.
 * Lorem ipsum dolor sit amet, consectetur adipiscing elit.
 * Lorem ipsum dolor sit amet, consectetur adipiscing elit.
*/
```

#### Variables and Assignments
**Types**
Specifies what kind of data to hold

#### Declaration
Variables must be declared before they can be used.
```c
int height;
float profit, loss;
```

#### Printing variables
```c
printf("%d\n", var0);   // int
printf("%f\n", var1);   // float
printf("%.2f\n", var2); // two decimal places float
```

#### Initialization
```c
int height;    // declared, uninitialized variable, may contain random value
int width = 6  // initialized variable, 6 is an initializer
int length, width, length = 10  // only length is initialized, with 10
```

#### Reading input
```c
float var;
scanf("%f\n", &var);
```

#### Defining Constants/Macros
```c
#define RECIPROCAL_OF_PI (1.0f / 3.14159f)
```
Parenthesis added for safeness (operator precedence)

#### Rules for Naming Identifiers
Identifiers are names for variables, macros, functions, and other entities.
- Identifiers may contain letters, digits and underscores
- Identifiers must begin with a letter
- Identifiers are case sensitive

#### Tokens
Tokens are groups of characters that can't be split up without changing their meaning.
```c
/* Example */
printf("Height: %d\n", height);
```
- `printf` and `height` are identifiers
- `"Height: %d\n"` is a string literal
- `(`, `)` and `;` are punctuations

Spaces are not critical in most cases. All tokens can be crammed together with no space between  them at all.

#### Extra: Inches per pound, rounding up
Add 165, then divide by 166
```c
weight = (volume + 165) / 166
```
