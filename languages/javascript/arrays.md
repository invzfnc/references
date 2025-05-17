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

"Popping" first element:
```js
cars.shift();
console.log(cars);  // [ 'Porsche', 'Koenigsegg' ]
```

"Pushing" element to front:
```js
cars.unshift("Honda");
console.log(cars);  // [ 'Honda', 'Nissan', 'Porsche', 'Koenigsegg' ]
```

`splice`
```js
// Syntax
arr.splice(starting_position[, how_many_elements_to_remove, replacement1, replacement2 ...]);
```

`map`
```js
// map returns a new array, the original array remains unchanged.

function square(n) {
    return n * n;
}

const numbers = [0, 1, 2, 3, 4, 5];
const squares = numbers.map(square);

console.log(numbers);
console.log(squares);

// [ 0, 1, 2, 3, 4, 5 ]
// [ 0, 1, 4, 9, 16, 25 ]
```

`filter`
```js
// the custom callback function (as a test) will return either true or false, elements passing the test will be added to the new array returned at the end.

function is_odd(n) {
    return n % 2;
}

const numbers = [0, 1, 2, 3, 4, 5];
const odds = numbers.filter(is_odd);

console.log(numbers);
console.log(odds);

// [ 0, 1, 2, 3, 4, 5 ]
// [ 1, 3, 5 ]
```

`reduce`
```js
function f(n, m) {
    return n * m;
}

const nums = [1, 2, 3, 4, 5];
const product = nums.reduce(f);

console.log(nums);
console.log(product);

// [ 1, 2, 3, 4, 5 ]
// 120
```
Full list of methods and properties: https://www.w3schools.com/jsref/jsref_obj_array.asp