#### CSS-style selectors
```html
<!-- Example -->
<div id="container">
  <div class="display"></div>
  <div class="controls"></div>
</div>
```
- `div.display`
- `.display`
- `#container > .display`
- `div#container > div.display`

Other [CSS combinators](/languages/css/basics.md)

In JavaScript:
```js
const controls = document.querySelector("#container > .controls");
console.log(controls);
// Output: <div class="controls"></div>
```

#### Relational selectors
- `firstElementChild`
- `lastElementChild`

```html
<div id="container">
  <div class="box" id="one">one</div>
  <div class="box" id="two">two</div>
  <div class="box" id="three">three</div>
</div>
```

```js
const container = document.querySelector("#container");
const first = container.firstElementChild;
console.log(first);
// Output: <div class="box" id="one">one</div>
```

#### Query selectors
- `element.querySelector(selector)`- returns a reference to the first match of `selector`
- `element.querySelectorAll(selectors)` - returns a `NodeList` (not array, though looks like array) containing references to all of the matches of the `selectors`
