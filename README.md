# css_prac
Some notes on css. Just a mild overview to relearn the content

|TABLE OF CONTENTS|
| ------------- |
|1 Introduction|
|2 Styling Text|
|3 Styling Boxes|
|4 CSS Layout|

Important Sources to Consider
- [ ] [MDN/Learn](https://developer.mozilla.org/en-US/docs/Learn)

## 1 Introduction

To apply a style sheet (css) we use the link element within the head
```html
<!DOCTYPE html>
<html>
  <head>
    <meta charset="utf-8">
    <title>My CSS experiment</title>
    <link rel="stylesheet" href="style.css">
  </head>
  <body>
    <h1>Hello World!</h1>
    <p>This is my first CSS example</p>
  </body>
</html>
``` 

Then inside the actual style.css file
```html
 h1 {
  color: blue;
  background-color: yellow;
  border: 1px solid black;
}
p {
  color: red;
}
T
```
#### DOM
Browser converts HTML and CSS into DOM. DOM represents the documents in the computer's memory, it combines the document's content with its style.
Browser displays the contents of the DOM

DOM has a tree like structure, element, attribute and piece of text in the markup language becomes a DOM node in the tree. Understanding DOM helps design, debug and maintain CSS, DOM is where CSS and document's content meet up.

Let's consider the HTML code
```html
<p>
  Let's use:
  <span>Cascading</span>
  <span>Style</span>
  <span>Sheets</span>
</p>
```

In the DOM, the node corresponding to our p element is a parent. Children are text nodes and the nodes corresponding to our span elements.
SPAN are also parents


#### Applying css to html

*External Stylesheet*

The way we did it before is known as a external stylesheets. CSS is written in a separate file with a .css extension, and you reference it from an HTML link element (shown above)

*Internal Stylesheet*
Instead of having a separate css file. We place the CSS inside a style element contained in the HTML head
```html
<head>
    <meta charset="utf-8">
    <title>My CSS experiment</title>
    <style>
      h1 {
        color: blue;
        background-color: yellow;
        border: 1px solid black;
      }
     </style>
</head>
```

*Inline Stylesheet*
Put the style within each specific element.
CSS declarations that affect one element only, contained within a style attribute
NEVER use this unless your work envo is restrictive (only allows edits on HTML for example)
```html
  <body>
    <h1 style="color: blue;background-color: yellow;border: 1px solid black;">Hello World!</h1>
    <p style="color:red;">This is my first CSS example</p>
  </body>
```

#### css syntax
Made up of
Properties Human readable identifiers that indicate which stylistic features you want to change
Values: Each specified property is given a value, which indicates how you want to change those stylistic features.
Property : Value is a CSS Declaration (colon in the middle!)
CSS Declaration -> CSS declaration blocks -> paired with SELECTORS

An example of a css declaration block
```html
{
  background-color:red; SEMI COLON NEEDED.
  background-style:none
}
```

#### CSS selectors and rules
How do we tell our declaration block which elements they should be applied to. 
We do so via the SELECTOR, a pattern that matches some elements on the page. The associated declarations will be applied to those elements only. 

#### CSS statements
up to here https://developer.mozilla.org/en-US/docs/Learn/CSS/Introduction_to_CSS/Syntax


