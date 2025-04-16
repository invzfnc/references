```js
const string = "string primitive"; // typeof: string
const stringConstructor = new String("String object"); // typeof: object
```

Template literal
> **Template literals** are literals delimited with backtick (`` ` ``) characters, allowing for [multi-line strings](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Template_literals#multi-line_strings), [string interpolation](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Template_literals#string_interpolation) with embedded expressions, and special constructs called [tagged templates](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Template_literals#tagged_templates).

```js
const a = 5;
const b = 10;
console.log(`fifteen is ${a + b}`)
```