```html
<body>
  <div id="container">
    <button>Click me!</button>
  </div>
</body>
```

```js
const container = document.querySelector("#container");
const button = document.querySelector("button");

container.addEventListener("click", () => {
    console.log("div was clicked.");
})

button.addEventListener("click", () => {
    console.log("button was clicked.");
})
```

Clicking on the button prints both "button was clicked." and "div was clicked."

**Event bubbling** happens when an element receives an event, and that event "bubbles" (propagates) up to its parent and ancestor elements in the DOM tree until it gets to the root element.

In some cases we want to prevent bubbling from happening, we add `event.stopPropagation()` to the callback function for child element.

```js
button.addEventListener("click", (e) => {
    e.stopPropagation();
    console.log("button was clicked.");
})
```

**Event bubbling** enables **event delegation**, where a parent element handles events for its child elements.

```html
<body>
  <div id="container">
    <button id="one">Click me!</button>
    <button id="two">Click me!</button>
    <button id="three">Click me!</button>
    <button id="four">Click me!</button>
  </div>
</body>
```

```js
const container = document.querySelector("#container");

container.addEventListener("click", (e) => {
    console.log(`button ${e.target.id} was clicked.`);
})

// output: button one/two/three/four was clicked.
```

Instead of setting the event listeners on each of the buttons, we set one single listener on their parent and have events that happen on them bubble up to their parent.

**`currentTarget` vs `target`**
- `e.currentTarget` refers to the `div` container / element to which this event handler has been attached.
- `e.target` refers to the exact button being clicked / element to which the event was initially fired.

**Event capturing** is just reversed event bubbling (both are forms of event propagation). It is disabled by default, pass `capture` option in `addEventListener()` to enable it.

> Why bother with both capturing and bubbling? In the bad old days, when browsers were much less cross-compatible than now, Netscape only used event capturing, and Internet Explorer used only event bubbling. When the W3C decided to try to standardize the behavior and reach a consensus, they ended up with this system that included both, which is what modern browsers implement.

---

Source: https://developer.mozilla.org/en-US/docs/Learn_web_development/Core/Scripting/Event_bubbling