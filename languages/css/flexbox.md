Flexbox is a way to arrange items into rows or columns. They grow or shrink (flex) based on rules defined.

A **flex container** is any element with `display: flex`. A **flex item** is any element that lives directly inside of a flex container.

Define a **flex container** with `display: flex`, everything inside will be a **flex item**. A flex item (child) can also be a flex container with `display: flex`.

`flex` is a shorthand property setting values for `flex-grow`, `flex-shrink`, and `flex-basis` simultaneously. For example:

```css
div {
  flex: 1  
  /* 
  equals:
  flex-grow: 1;
  flex-shrink: 1;
  flex-basis: 0;

  also equals:
  flex: 1 1 0;
  */
}
```

`flex-grow` defines the growth factor of the flex item.
```css
div.one {
  flex-grow: 1;
}

div.two {
  flex-grow: 2;
}
```
`div.two` is 2x the size of `div.one`.