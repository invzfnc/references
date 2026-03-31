## React Basics

### What is JSX?
- JSX stands for JavaScript XML.
- Syntax extension that allows us to directly write HTML-like code in JavaScript files.
- JSX is stricter than HTML, each tags must be closed, like `<br />`.
- Example:
```jsx
const element = <h1>Hello, world!</h1>;
```

### React Components

- React apps are all about components.
- Components are pieces of reusable UI that has its own logic and appearance.
- Components are JS functions that return markup.
- All components must return one root element, usually wrapped in a pair of `<div>` tags
- HTML tags must be in lowercase, while React components starts with a capital letter.

```jsx
// this is a component
function MyButton() {
  return (
    <button>I'm a button</button>
  );
}

// nesting components
export default function MyApp() {
  return (
    <div>
	  <h1>Welcome to my app</h1>
	  <MyButton />
    </div>
  );
}
```

### Props
- Props (properties) are data passed into components.
- Like knobs that we can adjust, like attributes to HTML tags, and like arguments to functions.
```jsx
function Greeting({ name }) {
  return (
	<h1>Hello, {name}.</h1>
  );
}

function MyApp() {
  return (
    <Greeting name={"Jane Doe"}/>
  );
}
```

### State - `useState`
For component to "remember" some information and display it, add a state to your component with `useState`.

Example: Building a button that displays time clicked by user.
1. Import `useState`
	```jsx
	import { useState } from 'react';
	```
2. Declare state variable inside component.
	```jsx
	function CounterButton() {
	  const [count, setCount] = useState(0);
	}
	```
	`useState` returns two things: `count` as the current state, and `setCount` as the function that lets you update the current state. `useState(0)` sets the initial value of `count` to 0.
3. Use `count` variable when showing times clicked.
4. Use `setCount` for incrementing the value of count.

Complete code:
```jsx
function CounterButton() {
  const [count, setCount] = useState(0);
  return (
    <button onClick={() => setCount(count + 1)}>
	  Clicked {count} time(s)
	</button>
  );
}
// CLick on the button to increment the value.
```

### State vs Props
|State|Props|
|---|---|
|Mutable (can be changed by the component)|Immutable (read-only in the child component)|
|Managed **internally** by the component|Passed **externally** from a parent element|
|For dynamic data that changes over time|For configuration and passing data from parent to children components|

### Conditional Rendering
- Showing different UI depending on the conditions.
- Use `if-else` statements or ternary operator.

```jsx
let content;  

if (isLoggedIn) {  
  content = <AdminPanel />;  
} 
else {  
  content = <LoginForm />;  
}  

return (  
  <div>  
    {content}  
  </div>  
);
```

### Render List
- To efficiently display list of items/repeated data.
- Use `for` loop or `map` method (`Array.prototype.map`).

Example: To display list of users as an unordered list
```jsx
const users = ["Alice", "Bob", "Charlie"];
```

#### Method 1: Using `for` loop
- The loop builds a list of `<li>` elements from users list.
- `<li>` elements are wrapped in `<ul>` tag before returning.

```jsx
const users = ["Alice", "Bob", "Charlie"];

function UsersList() {
  const listItems = [];

  for (let i = 0; i < users.length; i++) {
    listItems.push(<li key={i}>{users[i]}</li>);
  }

  return <ul>{listItems}</ul>;
}

function App() {
  return (
    <UsersList />
  )
}
```

#### Method 2: Using `map` method
- Same concept as for loop, but done in one line.
- Cleaner solution.

```jsx
const users = ["Alice", "Bob", "Charlie"];

function UsersList() {
  return (
    <ul>
      {users.map((user, index) => (
        <li key={index}>{user}</li>
      ))}
    </ul>
  );
}

function App() {
  return (
    <UsersList />
  )
}
```

Important: Always include a unique key to help React track item changes. (`key={index}`)
