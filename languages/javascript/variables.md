#### `let`
Variable declaration
```js
let name = "John";
console.log(name);
```

Reassignment
```js
name = "Lily";
```

#### `const`
```js
const COLOR_ORANGE = "#FF7F00";
```
Reassignment to `const` variables will throw `Uncaught TypeError: Assignment to constant variable.`

##### ALL_CAPS or camelCase?
- All caps for "hard-coded" values, known before execution
- camelCase for values known after execution/calculated during execution, but does not change once assigned value. 

```js
const pageLoadTime; /* time taken by a webpage to load */
```
The value of `pageLoadTime` is not known before the page load, so it’s named normally. But it’s still a constant because it doesn’t change after the assignment.

#### `var`
?
Quoted from odin
> There is also a third way, `var`, which was the original way variables were declared in JavaScript. `var` is similar to `let` in that variables assigned this way can be reassigned, but it has other quirks that were cleared up when the language introduced `let` and `const`. By and large, it is not used anymore. However, you will likely come across code which uses `var` at some point, so it is useful to know that it exists.
