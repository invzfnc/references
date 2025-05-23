Method 1
```html
<button onclick="alert('Hello, world!')">CLick Me</button>
```

Method 2
```html
<button id="btn">Click Me</button>
```

```js
const btn = document.querySelector("#btn");
btn.onclick = () => alert("Hello, world!");
```

Method 3
```html
<button id="btn">Click Me</button>
```

```js
const btn = document.querySelector("#btn");
btn.addEventListener("click", () => {
  alert("Hello, world!");
})
```