Object literal syntax
```js
// defining object
const myObject = {
	property: 'Value',
	otherProperty: 77,
	"obnoxious property": function() { /* do stuff */ }
};

// using object
myObject.property;  // dot notation
myObject["obnoxious property"]  // bracket notation
```

Object constructor: Like a class. By convention is named with a uppercase initial letter.
```js
function Player(name, marker) {
	this.name = name;
	this.marker = marker;  // marker for tic tac toe
	this.sayName = function() { console.log(this.name) };
}

const player = new Player("steve", "X");
player.sayName();
```

Constructors are just regular functions, they could be called without the `new` operator by mistake. To prevent that, use the `new.target` meta-property:
```js
function Player(name, marker) {
    if (!new.target) {
		throw Error("You must use the 'new' operator to call the constructor");
    }
	this.name = name;
	this.marker = marker;
	this.sayName = function() { console.log(this.name) };
}
```