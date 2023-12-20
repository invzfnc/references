> It's difficult to extract sense from strings, but they're the only communication coin we can count on.

#### Declaration / Initialization
```c
/* 
! Unexecutable code, 
  since variables can only be declared once
*/

char date[8] = "June 14";  // Equivalent to the one below
char date[8] = {'J', 'u', 'n', 'e', ' ', '1', '4', '\0'};

char date[] = "June 14";  // This is much easier
```

Special cases
```c
char date[9] = "June 14";  // Longer than expected
/* 
date would have the appearance:
[ J u n e   1 4 \0 \0]
*/

char date[7] = "June 14";  // Shorter than expected
/* 
date would have the appearance:
[ J u n e   1 4 ]
*/

```
#### String Literals
Or string constants. "A sequence of characters enclosed within double quotes"
C stores them as an array of characters, with `\0` as the final element to mark its end
Note: `\0` is a null character, with the code of 0 while `0` is zero, with the code of 48 (ASCII Code)

#### Escape Sequences
Octal escapes ends after three digits or when it encounters non-octal characters
`"\1234"` contains `\123` and `4`
`"\189"` contains `\1`, `8` and `9`

Hexadecimal escapes isn't limited to three digits, but a range of `\x0` - `\xff`
`"Z\xfcrich"` contains `Z`, `\xfc`, `r`, `i`, `c`, and `h`
`"\xfcber"` contains `\xfcbe` and `r`

#### Continuing a String Literal
1. `\` 
	```c
	printf("When you come to a fork in the road, take it. \
	-- Yogi Berra");
	```
	No other characters may follow `\` on the same line
	Drawback: the string must continue at the beginning of the next line, thereby ruining the indented structure
 
2. Adjacent string literals
	When two or more string literals are adjacent (separated only by white space), the compiler will join them into a single string
	```c
	printf("When you come to a fork in the road, take it."
		   "  --Yogi Berra");
	```
	

#### Operations on String Literals
- Strings can be passed to functions with argument of type `char *`
- A `char *` pointer can point to a string
- Supports subscripting (`"abc"[0]  // 'a'`)

Strings are immutable. Attempting to modify a string literal causes undefined behaviour

#### Idioms
- Declaring an string with `char` array
	```c
	#define STR_LEN 80
	char str[STR_LEN + 1];  // Can hold 80 characters max
	```

#### Character Arrays versus Character Pointers
```c
char date[] = "June 14";  // Array of characters
char *date = "June 14";   // Pointer to string literal
```

|Character Arrays|Character Pointers|
|---|---|
|Can be modified|Cannot be modified|
|Is an array name|Can point to other strings|

```c
/* We could still make p point to a character array */
char str[10];
char *p = str;
```

#### Writing Strings
##### `printf`
The `%s` conversion specification can be used to print a string

`printf` writes the characters in a string one by one until it encounters a null character

To print just part of a string, use `%.ps`, where `p` is a number of characters to be displayed
`%ms` can also be used to control the display field/width of string (`%m.ps` without `p`, that is)

##### `puts`
`puts` takes only one argument (the string to be printed). After writing the string, `puts` writes an additional new-line character

#### Reading Strings
##### `scanf`
`%s` to match string
`scanf("%s")` skips any whitespace characters, and reads characters until it reaches whitespace characters (a blank space, newline or tab). A string read using `scanf` will never contain whitespace characters

#####  `gets`
Doesn't skip white space characters
Reads until it encounters a new line character, but replaces it with a null character (in the char array)

Example:
```c
char sentence1[N + 1];
char sentence2[N + 1];

scanf("%s", sentence);
gets(sentence);
```

Suppose the user enters the line:
```terminal
   To C, or not to C: that is the question.
```

`sentence1` will contain
```terminal
To
````
`sentence2` will contain 
```terminal
   To C, or not to C: that is the question.
```

___

`strncpy` itself isn't without danger, it will leave the string in `s1` without a terminating null character if the length of the string stored in `s2`is >= the size of `s1` array

A safer way to use `strncpy`
```c
strncpy(s1, s2, sizeof(s1) - 1);
s1[sizeof(s1) - 1] = '\0'
```

##### `strlen`, String Length
`size_t strlen(const char *s)`
Returns the length of the string, excluding the null character
For example, `"abc"` will have the length of 3

##### `strcat`, String Concatenation
`char *strcat(char *s1, const char *s2)`
Appends the content of `s2` to `s1` and returns `s1` (a pointer, to be exact)

`strncat` is a safer but slower version of `strcat`

Example: 
```c
strncat(str1, str2, sizeof(str1) - strlen(str1) - 1);
```
`strncat` will terminate the string with a null character

##### `strcmp`, String Comparison
`int strcmp(const char *s1, const char *s2);`
Compares strings basing on lexicographic ordering, returns a value less than, equal to or greater than 0, depending on whether `s1` is less than, equal to or greater than `s2`

`s1` < `s2` if
- The first i characters of `s1` and `s2` match, but the (i + 1)st character of `s1` is less than the (i + 1)st character of `s2`
- All characters match, but `s1` is shorter than `s2`

##### `sprintf`, printf Into String
`int sprintf(char *str, const char *format, ...)`
Example: `sprintf(day_str, "%2d", day);`

#### String Idioms
All names that begin with `str` and a lower-case letter are reserved

##### Searching for the End of String
```c
/* Using for */
size_t count_length(const char *s)
{
    size_t count = 0;
    for (; *s != '\0'; s++)
        count++;
    return count
}
```

```c
/* Condensed -- Using while */
size_t count_length(const char *s)
{
    size_t count = 0;
    while (*s++)
        count++;
    return count;
}
```

```c
/* Increased speed */
size_t count_length(const char *s)
{
    const char *p = s;
    while (*s)
        s++;
    return s - p
}
```

##### Copying a String
```c
/* Straightforward but lengthy version */
char *concat_string(char *s1, const char *s2)
{
    char *p = s1;
    
    while (*p)
        p++;
    while (*s2 != '\0')
    {
        *p = *s2;
        p++;
        s2++;
    }
    
    *p = '\0';
    return s1;
}
```

```c
/* Condensed */
char *concat_string(char *s1, const char *s2)
{
    *p = s1;
    
    while (*p)
        p++;
        
    while (*p++ = *s2++)
        ;
        
    return s1;
}
```