### React Quick Start
#### Setup
Setting up React project locally using Vite
```sh
npm create vite@latest my-app -- --template react-ts
```

#### Folder Structure
A typical Vite React project folder structure, providing a solid foundation for small to growing applications, generally includes the following:

Root Directory:

- `index.html`: The main HTML file, serving as the template for the application. In Vite, it is typically located directly in the root, not within a `public/` folder.
- `package.json`: Contains project metadata and lists dependencies.
- `vite.config.js` (or `.ts`): Vite's configuration file for custom behaviors, plugins, and aliases.
- `.gitignore`: Specifies files and directories to be ignored by Git.
- `README.md`: Project documentation.
- `tsconfig.json` (for TypeScript projects): TypeScript configuration.
- `.eslintrc.json` (or `.js`): ESLint configuration for code linting.

Core Directories:

- `public/`: 
    
    Stores static assets like `favicon.ico` or images that are served directly without being processed by Vite.
    
- `src/`: 
    
    This is where the core application logic resides. It contains:
    
    - `main.jsx`: (or `main.tsx`): The entry point of the application, where the React app is initialized and mounted to the DOM.
    - `App.jsx`: (or `App.tsx`): The main application component.
    - `components/`: Houses reusable UI components (e.g., buttons, cards, forms, layouts). This can be further organized into subdirectories like `ui/`, `forms/`, `layout/`, etc., as the project grows.
    - `pages/`: Contains components representing different routes or views in the application.
    - `assets/`: Stores static assets like images, icons, and global styles that are imported into JavaScript files. Subdirectories like `images/`, `icons/`, `styles/` can be used for organization.
    - `hooks/`: Dedicated for custom React hooks to encapsulate and reuse logic.
    - `utils/`: Contains utility functions and helper modules.
    - `services/`: For handling data fetching, API interactions, and other service-related logic, potentially separated into `managers` and `repositories` for clearer responsibilities.
    - `context/`: If using React Context API for global state management, context providers and consumers are placed here.

https://www.thatsoftwaredude.com/content/14110/creating-a-good-folder-structure-for-your-vite-app
I haven't read this yet.

#### JSX
- JavaScript XML - XML-like extension to JavaScript.
- Allows us to write HTML elements in JavaScript.
- JSX is stricter than HTML, we have to close tags like `<br/ >`. Components also can't return multiple JSX tags. We have to wrap them in a parent tag like `<div>...</div>` or an empty `<></>` wrapper.

#### Components
- React apps are all about components.
- Components are are pieces of UI that has its own logic and appearance. 
- React components are JS functions that return markup.
- Components can be nested inside other components.

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

#### Adding Styles
In React, we specify styles with `className`, it works the same way as the HTML `class` attribute.

#### Curly Braces - Escaping back into JS
https://react.dev/learn#displaying-data

#### Conditional Rendering
- There is no special syntax for writing conditions. Just write it as the same way we write conditionals in JavaScript (`if` and `else` statements)
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

#### Rendering List
To display this array as a `ul`
```jsx
const products = [  
  { title: 'Cabbage', id: 1 },  
  { title: 'Garlic', id: 2 },  
  { title: 'Apple', id: 3 },  
];

```

Using `for` loop
```jsx
function MyList() {
  const listItems = new Array();
  for (let i = 0; i < products.length; i++) {
    listItems.push(<li key={products[i].id}>{products[i].title}</li>)
  }
  return (
    <ul>{listItems}</ul>
  )
}
```

Using `Array.prototype.map`
```jsx
function MyList() {
  const listItems = products.map(product =>  
    <li key={product.id}>  
      {product.title}  
    </li>  
  );  
  return (  
    <ul>{listItems}</ul>  
  );
}
```

> Notice how `<li>` has a `key` attribute. For each item in a list, you should pass a string or a number that uniquely identifies that item among its siblings. Usually, a key should be coming from your data, such as a database ID. React uses your keys to know what happened if you later insert, delete, or reorder the items.

#### `useState`
- For component to "remember" some information and display it, add a state to your component with`useState`.
	```jsx
	import { useState } from 'react';
	```
- Declare a state variable inside component
	```jsx
	function CounterButton() {
	  const [count, setCount] = useState(0);
	}
	```
- `useState` returns two things: the current state `count` and the function that lets you update the current state `setCount`. `useState(0)` sets `count` to the initial value of `0`.
- The convention is to write `[something, setSomething]`.
- Complete code:
	```jsx
	function CounterButton() {
	  const [count, setCount] = useState(0);
	  return (
	    <button onClick={() => setCount(count + 1)}>Clicked {count} time(s)</button>
	  )
	}
	// Click on the button increment the value shown
	```
- By default, each state is independent and bounded to its components only.

#### Props (Properties)
Continuing from `useState`, sometimes we want components to share the same state. To achieve this, we move the state variable to the parent component, then pass the state from parent to the components that we would like its state shared:
```jsx
function SharedCounterButton({ count, onClick }) {
  return (
    <button onClick={onClick}>Clicked {count} time(s)</button>
  )  
}

function App() {
  // shared state for SharedCounterButton
  let [count, setCount] = useState(0);

  return (
    <div>
      <SharedCounterButton count={count} onClick={() => setCount(count + 1)}/>
      <SharedCounterButton count={count} onClick={() => setCount(count + 1)}/>
    </div>
  )
```
The information that we pass down is called *props*. This is called *lifting state up*, by this, we've shared it between components.

Read this first: https://react.dev/learn/passing-props-to-a-component

- Components use props (properties) to communicate with each other.
- They look like HTML attributes, but you can pass JavaScript value through them, including objects, arrays and functions. Props are like knobs that you can adjust. Or like arguments that we pass to functions.
- Example code:
	```jsx
	function Logo({ width, height }) {
	  return (
	    <img 
	      src="https://i.imgur.com/ElWjENc.png"
	      alt="Google Logo" 
	      width={width}
	      height={height}
	      />
	  );
	}
	
	function App() {
	  return (
	    <div>
	      <Logo width="100" height="100"/>
	    </div>
	  )
	```
- Components only take one single argument, a `props` object
```jsx
function Component(props) {
  let width = props.width;
  let height = props.height;
}
```
- Putting curly braces - *Destructuring*
	```jsx
	function Component({ width, height }) {
	  // ...
	}
	```
- Default value for a prop
	```jsx
	function Component({ size = 100 }) {
	  // ...
	}
	```

#### Misc
JS Exports and Imports
https://javascript.info/import-export

JS `Array.prototype.map` method - Passes 3 argument to callback method, namely `currentValue`, `index`, and `array`
