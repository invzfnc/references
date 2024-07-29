HTML stands for HyperText Markup Language.

#### Elements and Tags
```html
<p>content</p>
```

`<p>`: Opening tag
`</p>`: Closing tag
All: Single element

Predefined tags reference: https://developer.mozilla.org/en-US/docs/Web/HTML/Element

**Semantic HTML**: Using the correct elements for content.

HTML elements that do not have a closing tag is called **void elements**, like `<br>` or `<img>`. Also referred to as self-closing tags, like `<br />` or `<img />`, which are often seen for historical reasons, but the latest version of HTML specification discourages their use and considers them invalid.

#### HTML Boilerplate
```html
<!DOCTYPE html>

<html lang="en">
  <head>
	<meta charset="UTF-8">
	<title>Webpage title</title>
  </head>

  <body>
	...
  </body>
</html>
```

1. **The DOCTYPE**: Tells browser what version of HTML is should use to render the document. `<!DOCTYPE html>` stands for the latest version, HTML5.
2. **`<html>`**: The root elements, and that every other element in the document will be a descendant of it. The **`lang` attribute** specifies the language of the text content in that element, allowing assistive technologies to adapt according t the language and invoke correct pronunciation.
3. **`<head>`**: Includes meta-information about the webpage. Should never include elements that display content on the webpage.
4. **`<meta charset="UTF-8">`**: Encoding is important to ensure that the webpage will display special symbols and characters from different languages correctly in browser.
5. **`<title>`**: Title displayed in webpage's browser tab. If not set, it is defaulted to its file name.
6. **`<body>`**: Includes content that will be displayed to users.

HTML validator: https://validator.w3.org/

#### Text elements
- `<p>`: Paragraphs
- `<h1>`-`<h6>`: Headings
- `<strong>`: Bold
- `<em>`: Italic

#### Nesting
Elements nested within other elements makes a **parent and child** relationship between them. Elements at the same level of nesting are considered to be **siblings**.

#### Lists
- `<ul>`: Unordered lists (like this one)
- `<li>`: Ordered lists

Syntax:
```html
<ul>
  <li>Item 1</li>
  <li>Item 2</li>
  <li>Item 3</li>
</ul>
```

#### Links and Images
- `<a>`: Anchor element. `href` attribute specifies the link for redirection. `target="_blank"`