Example: Creating and adding styles to create a maroon square.
```js
const div = document.createElement("div");

div.style.width = "100px";
div.style.height = "100px";
div.style.backgroundColor = "maroon";

document.querySelector("#container").appendChild(div);
```

**kebab-case vs camelCase**
```js
// dot notation with kebab case: doesn't work as it attempts to subtract color from div.style.background
// equivalent to: div.style.background - color
div.style.background-color;

// dot notation with camelCase: works, accesses the div's background-color style
div.style.backgroundColor;

// bracket notation with kebab-case: also works
div.style["background-color"];

// bracket notation with camelCase: also works
div.style["backgroundColor"];
```

**Editing attributes**
```js
// if id exists, update it to 'theDiv', else create an id with value "theDiv"
div.setAttribute("id", "theDiv");

// returns value of specified attribute, in this case "theDiv"
div.getAttribute("id");

// removes specified attribute
div.removeAttribute("id");
```

**Working with classes**
```js
// adds class "new" to your new div
div.classList.add("new");

// removes "new" class from div
div.classList.remove("new");

// if div doesn't have class "active" then add it, or if it does, then remove it
div.classList.toggle("active");
```

**Adding text content**
```js
// creates a text node containing "Hello World!" and inserts it in div
div.textContent = "Hello World!";
```

**Adding HTML content**
```js
// renders the HTML inside div
div.innerHTML = "<span>Hello World!</span>";
```

**The `defer` keyword**
When including JS file at the top of the file, many of these DOM manipulation methods will not work because the JS code is being run before the nodes are created in DOM. To solve this, add the `defer` keyword to load the file when the DOM is ready (but before `DOMContentLoaded` event).
```html
<head>
  <script src="js-file.js" defer></script>
</head>
```
Details: https://javascript.info/script-async-defer#defer

---
Source: https://www.theodinproject.com/lessons/foundations-dom-manipulation-and-events