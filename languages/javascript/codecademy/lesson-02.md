```js
var myName = "Name";
console.log(myName);
```
- `var` *declares* a new variable
- camelCasing is the standard convention in js
- `=` *assigns* the value to variable, it is said to be *initialized*
- The last line *references* the variable
- Variables are given initial value of `undefined` if not assigned during declaration

Rules for naming variables
- Cannot start with numbers
- Are case sensitive
- Cannot be the same as [keywords](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Lexical_grammar#keywords)

`var` vs `let`
- (https://stackoverflow.com/questions/762011/what-is-the-difference-between-let-and-var)
- https://javascript.info/var

`const`
- Cannot be reassigned with new values, or else `TypeError`
- Must be assigned a value when declared, or else `SyntaxError`

String interpolation
In the ES6 version of JavaScript, we can insert, or *interpolate*, variables into strings using *template literals*.
```js
const a = "A";
console.log(`Value of a: ${a}`);
// output: Value of a: A
```
- A template literal is wrapped by backticks `` ` ``
- Placeholder: `${variable}`

`typeof` (Unary operator)
```js
let a = 42;
console.log(typeof a); // output: number
```
