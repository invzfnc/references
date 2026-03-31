- **integer literal radix**: `h`, `o`/`q`, `d`/`t`, `b`/`y`, `r` (encoded real). default is decimal
- **real number literals**: `[sign]integer.[integer][exponent]`, where `sign` is `{+|-}` and `exponent` is `E[{+,-}]integer`. eg. `-44.2E+05`, `2.`, `26.E5`
- **encoded real**: real number in hexadecimal. real numbers are also known as floating-point numbers.
- **arithmetic expressions** work same as in common modern programming languages. same operator precedence.
- **character literals**: single character enclosed in either single or double quotes. eg. `'A'` and `"d"`. character literals are stored internally as integers.
- **string literals:** sequence of characters, including spaces, enclosed in single or double quotes. eg. `'ABC'`, `"Good night, world"`
- **reserved words**: not case sensitive. eg. `MOV` is the same as `mov` and `Mov`. types of reserved words are: instruction mnemonics, register names, directives, attributes, operators, predefined symbols.
- **identifier**: programmer-chosen name. not case sensitive. first character must be a letter, underscore, or one of these: @, ?, $. subsequent characters may be digits. it is not recommended to start identifiers with special characters.
- **directives**: command embedded in source code, recognized and acted upon by the assembler. directives do not execute at runtime, but they let you define variables, macros, and procedures. eg. `.data`, `DWORD`.
- **instructions**: a statement that becomes executable when a program is assembled. instruction consist of parts: `[label:] mnemonic [operands] [;comment]`

you can make all keywords and identifiers case sensitive by adding the `-Cp` command line switch when running the assembler.