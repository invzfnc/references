# Cascading Style Sheet
## Syntax
CSS is made up of rules.  
Rules are made up of selectors, properties and values.
```css
selector {
  property: value;
}
```

## Selectors
### Universal Selector
```css
* {
  color: purple;
}
```

### Type Selector
#### Tags
```css
div {
  color: white;
}
```

#### Class
```css
.alert-text {
  color: red;
}
```
- Can use same class on as many elements as wanted
- Multiple class declaration: `class="alert-text severe-alert"` (Separated by space)

#### ID
```css
#title {
  background-color: red;
}
```
- Use IDs sparingly.
- An element can only have one ID.
- An ID cannot be repeated on a single page
- Takes advantage of specificity

### Grouping Selector (Comma)
For groups of elements that share the same style declaration
```css
.read,
.unread {
  color: white;
  background-color: black;
}
```

### Chaining Selector
Chaining more than one type selector.  
Going specific for a single element. (Describing tag, classes and id in the element)
```html
<div>
  <div class="subsection header">Latest Posts</div>
  <p class="subsection" id="preview">Preview goes here.</p>
</div>
```
```css
.subsection.header {
  color: red;
}

.subsection#preview {
  color: black;
}
```

## Combinators
Types of combinators:
- Descendant selector (space)
- Child selector (>)
- Adjacent sibling selector (+)
- General sibling selector (~)

### Descendant Combinator
Selects the last selector that has an ancestor (parent, grandparent, etc) that matches the previous selector.  
(Nesting)

## Properties
### Colors
- `color` (foreground color)
- `background-color`

#### CSS Legal Color Values
- Hexadecimal colors, `0000ff`
- Hex with transparency, `0000ff50`
- RGB, `rgb(0, 0, 256)`
- RGBA, `rgba(0, 0, 256, 0.5)`
- HSL, `(hue, saturation, lightness)`
- HSLA, `(hue, saturation, lightness, alpha)`
- Predefined, see https://www.w3schools.com/colors/colors_names.asp
- `currentcolor` Keyword

### Typography
- `font-family`
    - Font family name, eg `"DejaVu Sans"`
    - Generic family name, eg `sans-serif`
    - Example: `font-family: "DejaVu Sans", sans-serif;`
- `font-size`
    - `font-size: 22px` (No whitespace in between)
- `font-weight` (value ranges from 1 to 1000)
    - Boldness of text
    - `font-weight: 700` == `font-weight: bold`
- `text-align`
    - `text-align: center`

### Image
```css
img {
  height: 500px;
  width: auto;
}
/* Use auto for scaling without losing its proportions */
```

If the dimensions are unspecified and the image takes longer to load than other page contents, it will cause drastic shift of the other contents when the image does load in. Specifying dimensions of image "reserves" a space for it.

## Specificity
1. 
    1. ID selectors
    2. Class selectors
    3. Type selectors

2.  1. Number of classes specified 
    2. Ultimate tie: Last defined

Combinators do not add any specificity (`space`, `+`, `~`, `>`)

# Adding CSS to HTML
1. External CSS
```html
<head>
  <link rel="stylesheet" href="styles.css">
</head>

<!-- rel: Relationship, between the HTML file and the linked file -->
```

2. Internal CSS / Embedded CSS
```html
<head>
  <style>
    div {
      color: white;
      background-color: black;
    }
  </style>
</head>
```

For adding unique styles to a *single* page of a website

3. Inline CSS
```html
<div style="color: white; background-color: black;">
  ...
</div>
```

For adding unique style for a *single* element

**Quick Reference**
```css
/* Grouping (Comma) 
To avoid repetitive code */

.read,
.unread {
  color: white;
  background-color: black;
}
```

```css
/* Chaining (No space)
Like `and`, going specific
eg this element has a class of subsection and an id of header */

.subsection#header {
  color: white;
  background-color: black;
}
```

```css
/* Descendant Combinator (Space)
Nesting tags and attributes */

.ancestor .descendant .contents {
  color: white;
  background-color: black;
}
```