#### `if-else` and `if-else-if`
```js
if (condition) {
    ...
} else {
	...
}

if (hour < 18) {
	greeting = "Good day";
} else {
	greeting = "Good evening";
}
```

```js
if (condition1) {
	...
} else if (condition2) {
	...
} else {
	...
}
	
if (time < 10) {
	greeting = "Good morning";
} else if (time < 20){
	greeting = "Good day";
} else {
	greeting = "Good evening";
}
```

#### Logical operators
`||` finds the first truthy value
```js
alert( null || undefined || 1); // 1
true || alert("not printed");
false || alert("printed"); // short-circuit evaluation
```

`&&` finds the first falsy value. If there are none falsy value, returns the last value
```js
alert( 1 && 2 && null && 3 ); // null
alert( 1 && 2 && 3 ); // 3, the last one
```

`!` negates and convert the operand to boolean type
```js
alert( !true ); // false
alert( !0 ); // true
```

`!!` (double NOT) is sometimes used to convert a value to boolean type
```js
alert( !!"non-empty string" ); // true
alert( !!null ); // false
```
equivalent (`Boolean` function)
```js
alert( Boolean("non-empty string") ); // true
alert( Boolean(null) ); // false
```

#### `switch`
```js
let a = 2 + 2;

switch (a) {
  case 3:
    alert( 'Too small' );
  case 4:
    alert( 'Exactly!' );
  case 5:
    alert( 'Too big' );
  default:
    alert( "I don't know such values" );
}
```
switch arguments can be expressions