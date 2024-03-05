> In seeking the unattainable, simplicity only gets in the way.

#### `printf`
```c
// Declaration of printf
int printf(const char *format, ...);
```
 The format string may contain both ordinary characters and **conversion specifications**. The information that follows the `%` character *specifies* how the value is *converted* from its internal form (binary) to printed form (characters). For example, `%d` specifies that `printf` convert an `int` value from binary to a string of decimal digits, while `%f` does the same for a `float` value.

```c
int x = 10;
float y = 1.2;
printf("x: %d, y: %f\n", x, y);
```

##### Conversion specifications
`%m.pX`

- `m`, minimum field width (digit) - Controls padding and fill, `-m` for ljust (filled with space characters)
- `.p`, precision (digit) - Effect depends on `X`
- `X`, conversion specifier (letter)

**Precision, `p`**
- `d`, integer in decimal - `p` indicates the minimum number of digits to display, with extra zeros added to the beginning of the number.
- `e`, exponential - `p` indicates the number of digits to display after decimal point. (default is 6)
- `f`, floating point - `p` indicates the number of digits to display after decimal point. (default is 6)
- `g`, either exponential form or fixed decimal format - `p` indicates the number of significant digits to display. This is useful for displaying numbers whose size can't be predicted when the program is written or that tend to vary widely in size.

```c
int i = 40;
float x = 839.21f;

printf("|%d|%5d|%-5d|%5.3d|\n", i, i, i, i);
printf("|%10.3f|%10.3e|%-10g|\n", x, x, x);

/* Output:
 * |40|   40|40   |  040|
 * |   839.210| 8.392e+02|839.21    |
 */
```

##### Escape Sequences
|Escape Sequence|Meaning|
|---|---|
|`\a`|Alert (bell)|
|`\b`|Backspace|
|`\n`|New line|
|`\t`|Horizontal tab|

`\"` represents the `"` character, `\\` represents `\`, and `%%` represents `%`.

#### `scanf`
```c
int scanf(const char *format, ...);
```

##### Format specifiers
- `%d`, decimal integers
- `%i`, octal (`056`), decimal (`56`), hexadecimal (`0x56`) integers
- `%f`, floating-point numbers

##### How `scanf` works?
```c
// Input: 
// 1-20.3-4.0e3\n
scanf("%d%d%f%f", &i, &j, &x, &y);
```
1. `%d`. The first nonblank input character is `1`; since integers can begin with `1`, `scanf` then reads the next character, `-`, which can't appear inside an integer, `scanf` stores `1` into `i` and puts the `-` character back into the input stream.
2. `%d`. `scanf` then reads the characters `-`, `2`, `0`, and `.`. Since an integer can't contain a decimal point, `scanf` stores -20 into `j` and puts the `.` character back.
3. `%f`. `scanf` reads the characters `.`, `3`, and `-`. Since a floating-point number can't contain a minus sign after a digit, `scanf` stores 0.3 into `x` and puts the `-` character back.
4. `%f`. `scanf` reads the characters `-`, `4`, `.`, `0`, `e`, `3` and `\n`. Since a floating-point number can't contain a new-line character, `scanf` stores -4.0x10^3 into y and puts the new-line character back.

- `scanf` ignores whitespaces when searching for matches. A whitespace character in format string will match zero or more whitespace characters in input stream.
- When `scanf` encounters non-whitespace character in format string, it will match the exact character in input stream. If the character does not match, `scanf` puts the offending character back into the input, then aborts without further processing the rest of the stream.
- If the item is read successfully, `scanf` continues processing the rest of the format string. If any item is not read successfully, `scanf` returns immediately without looking at the rest of format string and remaining input data.
- Putting `\n` at the end of format string is usually a bad idea. `scanf` treats new-line characters as spaces; both cause `scanf` to advance to the next non-whitespace character. This might cause an interactive program to "hang" until the user enters a non-blank character.

**Examples** (Whitespace and non-whitespace characters matching):

Format string: `%d/%d`

Input: ` 5/ 96`  
`scanf` will skip the first space while looking for an integer. It will match `%d` with `5`, `/` with `/`, and matches `%d` with `96`.

Input: ` 5 / 96`  
`scanf` will skip the first space, matches `%d` with `5`, then attempts to match the `/` in the format string with the space in input. There is no match, so `scanf` puts the space back and return. ` / 96` remain to be read by the next call of `scanf`. Therefore we should use `%d /%d` instead.

