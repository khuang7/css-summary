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
At-rules are used to convey metadata, conditional information or other descriptive info
```html
@media (min-width: 801px) {
  body {
    margin: 0 auto;
    width: 800px;
  }
}
```
The media applies to a browser that matches a specific 800 pixel condition

#### Readability
White spaces: Used to make the code more readable, css ignores white space
Comments: Use /* comment */ for useful guide

## 2 Selectors

#### Simple Selector
Type Selector (aka element selectors)
Basically a case insensitive match between selector name and a given html element name.
This is basically what is shown before

Class Selectors
dot '.' followed be class name.
Class attributes, where we can choose the name of the class. 
Multiple eleents in a document can have the same class value and a single element can have multiple class names

```html
<ul>
  <li class="first done">Create an HTML document</li>
  <li class="second done">Create a CSS style sheet</li>
  <li class="third">Link them all together</li>
</ul>

/* The element with the class "first" is bolded */
.first {
  font-weight: bold;
}

/* All the elements with the class "done" are strikethrough */
.done {
  text-decoration: line-through;
}
```

ID Selectors
These consists of a hash symbol followed by the ID name of the given element.
ID MUST BE UNIQUE, duplicate ID result in unpredictable behaviour

```html
<p id="polite"> — "Good morning."</p>
<p id="rude"> — "Go away!"</p>

#polite {
  font-family: cursive;
}
#rude {
  font-family: monospace;
  text-transform: uppercase;
}
```

Universal Selector
The ultimate joker. Allows selecting all elements on page and is often used in combination with out selectors.

```html
* {
  padding: 5px;
  border: 1px solid black;
  background: rgba(255,0,0,0.25)
}
```

#### Attribute Selectors
Selectors that match an exact attribute value
``` /* All elements with the attribute "data-vegetable"
   are given green text */
[data-vegetable] {
  color: green;
}

/* All elements with the attribute "data-vegetable"
   with the exact value "liquid" are given a golden
   background color */
[data-vegetable="liquid"] {
  background-color: goldenrod;
}

/* All elements with the attribute "data-vegetable",
   containing the value "spicy", even among others,
   are given a red text color */
[data-vegetable~="spicy"] {
  color: red;
}
```

Substring value attributes selectors
These are sort of like regex selectors as they offer flexible matching similar to regular expressions. However they are NOT TRUE REGEX.


#### Pseudo-classes
These selectors don't select elements but rather certain parts of elements. The types are: pseudo classes, pseudo elements

A pseudo class is a keyword added to the end of a selector preceded by a colon. Used to specific that you want to style the select element when it is in a certain state. For example only access when being pointed over by the mouse pointer.
```html
a:hover,
a:active,
a:focus {
  color: darkred;
  text-decoration: none;
}
```

A pseudo elements are similar to pseudo classes but this time we use :: to be added at the end of selectors
```html
/* All elements with an attribute "href" with values
   starting with "http" will have an arrow added after their
   content (to indicate they are external links) */
[href^=http]::after {
  content: '⤴';
}
```

#### Combinators
Using one selector at a time is useful but can be inefficient. CSS has several ways to select elements based on how they are related to one another. Expressed via cominators

[refer to example on combinators.html]

Groups of selectors on one rule.
We can write groups of selectors separated by commas to apply the same rule to muiltiple sets of select elements at once
```html
h1, h2, h3, h4, h5, h6 {
  font-family: helvetica, 'sans serif';
}
```

There's quite a lot on selectors! Refer back to this [link](https://https://developer.mozilla.org/en-US/docs/Learn/CSS/Introduction_to_CSS/Selectorsduckduckgo.com) if trouble ever arises with this concept!!



## 4 CSS values and units
There are many types of property values to consider. Below are common ones (not all of them)

#### numeric values
Length and size (<length> for reference)
```html
  p {
  margin: 5px;
  padding: 10px;
  border: 2px solid black;
  background-color: cyan;
}
```
Pixels are considered an absolute unit (always the same size) but it is possible to use other measurements like cm, mm, in, pt, pc. But it is highly unlikely to be used


Another thing to consider are **relative units**
A one that is commonly used in web development is em:lem
The default base font-size by web browsers is 16 pixels. The computer value of 1em is 16 pixels by default. It uses inheritance and the parent element determines that it is 16

Unitless values
```html
margin: 0;
```
If we want to remove the margin or padding from an element we can just use 0

Number of animations
(refer to example in index.html)

#### percentages
An example is boxes whose width will always shift to be a certain percentage of hteir parent container width. 

#### colours
The standard colour system uses RGB. And a combination of 16.7 million colours are possible due to the different combinations possible. 256 x 256 x 256. RGB(255,0,0) == all red

Hexadecimal values are also possible which is written as #ff0000

Furthermore there are other things such as RGBA, HSLA which deals with transparency. Or rgba(255,0,0,0.5) to specify opacity

#### functions
Similar to any programming language. 
```css
background-color: rgba(255,0,0,0.5);
background-color: hsla(240,100%,50%,0.5);
```

```css
/* calculate the new position of an element after it has been rotated by 45 degress */
transform: rotate(45deg);
/* calculate the new position of an element after it has been moved across 50px and down 60px */
transform: translate(50px, 60px);
/* calculate the computed value of 90% of the current width minus 15px */
width: calc(90% - 15px);
/* fetch an image from the network to be used as a background image */
background-image: url('myimage.png'); 
/* create a gradient and use it as a background image */ 
background-image: linear-gradient(to left, teal, aquamarine);
```

## 4 Cascade and Inheritance
There are cases when multiple CSS rules will have selectors matching the same element. So which CSS rule wins? This is determined by the cascade

1. Importance
2. Specificity
3. Source Order

#### importance
AN example in action
```html
<p class="better">This is a paragraph.</p>
<p class="better" id="winning">One selector to rule them all!</p>
```

```css
#winning {
  background-color: red;
  border: 1px solid black;
}

.better {
  background-color: gray;
  border: none !important;
}

p {
  background-color: blue;
  color: white;
  padding: 5px;
}
```

Following this example above
1. The third rule has padding and colour is applied. However background colour is not applied (overriden by previous rule)
2. The rules above win, because ID/Class selectors have higher specificity than element selectors
3. Both elements have a class of better. The second class also has winning too. ID has a higher specifity compared than classes.  
4. The second element does get the red colour. Because of the !important declaration


if ! importance is used then this will ALWAYS WIN over the others but it is recommended not to use this because it makes debugging pretty hard

#### Specificity
How many elements it could match.

## 5 Box Model


## 6 CSS Layout


