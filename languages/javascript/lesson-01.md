Printing to console
```javascript
console.log(42);
// console: object, log: method
```

Commenting
```javascript
// single line comment
/* multi
   line comment
 */
console.log(/* comment in between */ 42)
```

Fundamental data types
- **Number**: Any number, including numbers with decimals: `4`, `8`, `1516`, `23.42`.
- **BigInt**: Any number, greater than 253-1 or less than -(253-1), with n appended to the number: 1234567890123456n.
- **String**: Any grouping of characters on your keyboard (letters, numbers, spaces, symbols, etc.) surrounded by single quotes: `' ... '` or double quotes `" ... "`, though we prefer single quotes. Some people like to think of string as a fancy word for text.
- **Boolean**: This data type only has two possible values— either `true` or `false` (without quotes). It’s helpful to think of booleans as on and off switches or as the answers to a “yes” or “no” question.
- **Null**: This data type represents the intentional absence of a value, and is represented by the keyword `null` (without quotes).
- **Undefined**: This data type is denoted by the keyword `undefined` (without quotes). It also represents the absence of a value though it has a different use than `null`. `undefined` means that a given value does not exist.
- **Symbol**: A newer feature to the language, symbols are unique identifiers, useful in more complex coding. No need to worry about these for now.
- **Object**: Collections of related data.

Operators
1. Add: `+`
2. Subtract: `-`
3. Multiply: `*`
4. Divide: `/`
5. Remainder: `%`

Additionally,
1. Mathematical assignment operators: `+=`, `-=` etc
2. Increment, decrement operators: `++`, `--`

String concatenation
```javascript
console.log("Hello, " + "World!");
```

`length` property
```javascript
console.log("Hello".length); // 5
```

String methods
```javascript
console.log("hello".toUpperCase()); // HELLO
console.log("hello".startsWith('H')); // true
console.log("  hello  ".trim()); // hello
```

`Math` object
```javascript
Math.random(); // returns a number between 0 and 1

/* to generate number between 0 and 50 */
Math.random() * 50;

Math.floor(5.5) // 5, rounds down to the nearest whole number
Math.ceil(5.5) // 6, returns smallest integer >= the number
```

Reference: https://developer.mozilla.org/en-US/docs/Web/JavaScript