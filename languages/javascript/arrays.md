```js
const cars = ["Nissan", "Porsche", "Koenigsegg"];
```
In 2015, JavaScript introduced `const` (ECMAScript 2015, ES6). It has become a common practice to declare arrays using `const`.

`const` does not define a constant array. It defines a constant **reference** to an array.

```js
cars = ["Toyota", "Porsche", "Audi"];  // ERROR: Cannot reassign

cars[0] = "Toyota";  // Can change an element
cars.push("Audi");   // Can add an element
```

Note: `const` variables must be assigned a value when they are declared.

#### Common methods and properties
Example
```js
const cars = ["Nissan", "Porsche", "Koenigsegg"];
```

Getting length of array:
```js
let size = cars.length;  // 3
```

Converting to string:
```js
document.getElementById("demo").innerHTML = cars.toString();
// Nissan,Porsche,Koenigsegg
```

Indexing:
```js
// Getting second element
console.log(cars[1]);     // Porsche
console.log(cars.at(1));  // Porsche
```
To get last element, use `cars.at(-1)` (ES2022)

Joining:
```js
console.log(cars.join(", "));
// Nissan, Porsche, Koenigsegg
```

Popping element:
```js
console.log(cars.pop());  // Koenigsegg
console.log(cars);  // [ 'Nissan', 'Porsche' ]
```

Pushing element:
```js
console.log(cars.push("Audi"));  // 4
console.log(cars);  // [ 'Nissan', 'Porsche', 'Koenigsegg', 'Audi' ]
```


Full list of methods and properties: https://www.w3schools.com/jsref/jsref_obj_array.asp