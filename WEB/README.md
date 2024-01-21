# Table of Contents
- [Table of Contents](#table-of-contents)
- [HTML](#html)
	- [Structure](#structure)
	- [Nesting](#nesting)
	- [Attributes](#attributes)
		- [id](#id)
		- [class](#class)
	- [comments](#comments)
	- [conventions and validation](#conventions-and-validation)
	- [Tags](#tags)
		- [block elements](#block-elements)
			- [Structural Elements](#structural-elements)
				- [Divisions](#divisions)
				- [Sections](#sections)
				- [Articles](#articles)
				- [Asides](#asides)
				- [Headers](#headers)
				- [Footers](#footers)
				- [Navs](#navs)
				- [Addresses](#addresses)
			- [main](#main)
			- [Headings](#headings)
			- [Paragraphs](#paragraphs)
			- [Divisions](#divisions-1)
			- [Lists](#lists)
				- [Unordered](#unordered)
				- [Ordered](#ordered)
				- [Description](#description)
			- [Tables](#tables)
			- [Forms](#forms)
			- [Images](#images)
		- [Inline Elements](#inline-elements)
			- [Text](#text)
			- [code](#code)
			- [blockquotes](#blockquotes)
			- [Spans](#spans)
			- [Links](#links)
		- [Inline-block Elements](#inline-block-elements)
			- [Images](#images-1)
			- [Figure](#figure)
			- [iframe](#iframe)
			- [Input](#input)
			- [Buttons](#buttons)
			- [Select](#select)
			- [Textarea](#textarea)
		- [Special Elements](#special-elements)
			- [Breaks](#breaks)
			- [Horizontal Rule](#horizontal-rule)
			- [word break](#word-break)
- [CSS](#css)
	- [Selectors](#selectors)
		- [Overview](#overview)
		- [Element Selector](#element-selector)
		- [#id Selector](#id-selector)
		- [.class Selector](#class-selector)
		- [Universal Selector](#universal-selector)
		- [Group Selector](#group-selector)
		- [Descendant Selector](#descendant-selector)
		- [Child Selector](#child-selector)
		- [Adjacent Sibling Selector](#adjacent-sibling-selector)
		- [General Sibling Selector](#general-sibling-selector)
		- [Attribute Selector](#attribute-selector)
		- [Attribute Value Selector](#attribute-value-selector)
		- [Attribute Value Starts With Selector](#attribute-value-starts-with-selector)
		- [Attribute Value Ends With Selector](#attribute-value-ends-with-selector)
		- [Attribute Value Contains Selector](#attribute-value-contains-selector)
		- [Attribute Value Contains Word Selector](#attribute-value-contains-word-selector)
		- [Attribute Value Contains Prefix Selector](#attribute-value-contains-prefix-selector)
		- [Pseudo-classes](#pseudo-classes)
		- [Pseudo-elements](#pseudo-elements)
		- [Combinators](#combinators)
		- [Multiple Selectors](#multiple-selectors)
	- [CSS Comments](#css-comments)
	- [Units](#units)
	- [Colors](#colors)
		- [Notations](#notations)
		- [Color Names](#color-names)
	- [Text Properties](#text-properties)
		- [Font](#font)
		- [Text](#text-1)
		- [Links](#links-1)
		- [Lists](#lists-1)
		- [Tables](#tables-1)
		- [Quotes](#quotes)
		- [Icons](#icons)
		- [Opacity](#opacity)
		- [Cursor](#cursor)
		- [User Select](#user-select)
		- [Resize](#resize)
		- [Box Sizing](#box-sizing)

# HTML
## Structure
	- DOCTYPE
	- html
		- head
    		- meta tags
			- title
			- icon
			- references
    			- links to CSS ( are loaded asynchronously )
    			- links to JS ( are loaded asynchronously )
		- body
			- header
			- main
			- footer
			- scripts ( that need to be loaded with the page )
```html
<!DOCTYPE html>
<html lang="eng">
  <head>
	<!-- meta tags -->
	<meta charset="UTF-8">
	<meta name="description" content="Free Web tutorials">
	<meta name="keywords" content="HTML, CSS, JavaScript">
	<meta name="author" content="John Doe">
	<meta name="viewport" content="width=device-width, initial-scale=1.0">
	<!-- title -->
	<title>Page Title</title>
	<!-- icon -->
	<link rel="icon" href="favicon.ico" type="image/x-icon">
	<!-- references -->
	<link rel="stylesheet" href="styles.css">
	<script src="script.js"></script>
  </head>
  <body>
	<header></header>
	<main></main>
	<footer></footer>
  </body>
</html>
```
## Nesting
> Nesting is the process of putting elements inside other elements.
> An element can be both a parent and a child at the same time.
```html
<div>
	<p>Paragraph</p>
</div>
```
## Attributes
> Attributes are used to provide additional information about HTML elements.
> Style attributes should be defined in style sheets, not in the HTML markup.

```html
<tag attribute="value">Content</tag>
```
### id
> The id attribute specifies a unique id for an HTML element
> They are used to adress this specific element by style sheets or scripts
```html
<p id="unique">Paragraph</p>
```
### class
> The class attribute specifies one or more classnames
> They are not unique, and areused to adress all elements with this class by style sheets or scripts
```html
<p class="classname">Paragraph</p>
```
## comments
> Comments are not displayed in the browser, but they can help document your HTML source code.
```html
<!-- This is a comment -->
```
## conventions and validation
- lowercase for tags and attributes.
- texts should be wrapped in paragraphs
- the existing tags should be used for their purpose
- self-closing tags should have a space before the closing slash
- attributes should have double quotes
- attributes should be in the order: id, class, name, src, alt, width, height, href, title, rel
- id's should be unique
- class names should be short and descriptive
```html
<p id="unique-id" class="sup-sub extra">Paragraph</p>
```

## Tags
- block elements are elements that are displayed in a new line
- inline-block elements are elements that are displayed in the same line but they can have a width and a height
- inline elements are elements that are displayed in the same line but they can't have a width and a height
### block elements
> Block elements: These elements start on a new line and take up the full width available. Examples from your list include 
```html 
<div>, <section>, <article>, <aside>, <header>, <footer>, <nav>, <address>, <main>, <h1> to <h6>, <p>, <ul>, <ol>, <dl>, <table>, <form>
```
#### Structural Elements
##### Divisions
```html
<div>Division</div>
```
##### Sections
```html
<section>Section</section>
```
##### Articles
```html
<article>Article</article>
```
##### Asides
```html
<aside>Aside</aside>
```
##### Headers
```html
<header>Header</header>
```
##### Footers
```html
<footer>Footer</footer>
```
##### Navs
```html
<nav>Nav</nav>
```
##### Addresses
```html
<address>Address</address>
```
#### main
```html
<main>Main</main>
```

#### Headings
```html
<h1>Heading 1</h1>
<h2>Heading 2</h2>
<h3>Heading 3</h3>
<h4>Heading 4</h4>
<h5>Heading 5</h5>
<h6>Heading 6</h6>
```
#### Paragraphs
```html
<p>Paragraph</p>
```
#### Divisions
```html
<div>Division</div>
```
#### Lists
##### Unordered
```html
<ul>
	<li>Item 1</li>
	<li>Item 2</li>
	<li>Item 3</li>
</ul>
```
##### Ordered
```html
<ol>
	<li>Item 1</li>
	<li>Item 2</li>
	<li>Item 3</li>
</ol>
```
##### Description
```html
<dl>
	<dt>Coffee</dt>
	<dd>- black hot drink</dd>
	<dt>Milk</dt>
	<dd>- white cold drink</dd>
</dl>
```
#### Tables
```html
<table>
	<thead>
		<tr>
			<th>Firstname</th>
			<th>Lastname</th>
			<th>Age</th>
		</tr>
	</thead>
	<tbody>
		<tr>
			<td>Jill</td>
			<td>Smith</td>
			<td>50</td>
		</tr>
		<tr>
			<td>Eve</td>
			<td>Jackson</td>
			<td>94</td>
		</tr>
	</tbody>
</table>
```
#### Forms
```html
<form action="/action_page.php" method="get">
	<label for="fname">First name:</label><br>
	<input type="text" id="fname" name="fname" value="John"><br>
	<label for="lname">Last name:</label><br>
	<input type="text" id="lname" name="lname" value="Doe"><br><br>
	<input type="submit" value="Submit">
</form>
```
#### Images
```html
<img scr="image.png" alt="image">
```

### Inline Elements
> Inline elements: These elements do not start on a new line and they only take up as much width as necessary. Examples from your list include
```html 
<b>, <strong>, <i>, <em>, <mark>, <small>, <del>, <ins>, <sub>, <sup>, <span>, <a>, <code>
```
#### Text
```html
<b>Bold text</b>
<strong>Important text</strong>
<i>Italic text</i>
<em>Emphasized text</em>
<u>Underlined text</u>
<q>This is a short quotation</q>
<em>Emphasized text</em>
<mark>Marked text</mark>
<small>Small text</small>
<del>Deleted text</del>
<ins>Inserted text</ins>
<sub>Subscript text</sub>
<sup>Superscript text</sup>
```
#### code
```html
<code>This is computer code</code>
```
#### blockquotes
```html
<blockquote cite="http://www.worldwildlife.org/who/index.html">
For 50 years, WWF has been protecting the future of nature.
</blockquote>
```

#### Spans
```html
<span>Span</span>
```
#### Links
> target="_blank" opens the link in a new tab

> target="_self" opens the link in the same tab
```html
<a href="https://www.w3schools.com" target="_self">Visit W3Schools.com!</a>
```
> mailto: opens the default mail client

> tel: opens the default phone client
```html
<a href="mailto:person@mail.com">Send email</a>
<a href="tel:+123456789">Call</a>
```

### Inline-block Elements
> Inline-block elements: These elements are a hybrid of inline and block elements. They flow with the text like inline elements, but they can have width and height like block elements. Examples from your list include
```html
<img>, <input>, <button>, <select>, <textarea>.
```
#### Images
```html
<img src="image.png" alt="image">
```
#### Figure
> The \<figure> tag specifies self-contained content, like illustrations, diagrams, photos, code listings, etc.
```html
<figure>
	<img src="image.png" alt="image">
	<figcaption>Figcaption</figcaption>
</figure>
```
#### iframe
> An inline frame is used to embed another document within the current HTML document.
```html
<iframe src="https://www.w3schools.com"></iframe>
```
#### Input
```html
<input type="text" name="fname">
```
#### Buttons
```html
<button>Click me</button>
```
#### Select
```html
<select>
	<option value="volvo">Volvo</option>
	<option value="saab">Saab</option>
	<option value="mercedes">Mercedes</option>
	<option value="audi">Audi</option>
</select>
```
#### Textarea
```html
<textarea name="message" rows="10" cols="30">
The cat was playing in the garden.
</textarea>
```
### Special Elements
> \<br> and \<hr> are special cases. \<br> is a line break and doesn't really have a "block" or "inline" classification because it simply inserts a line break. \<hr> is a thematic break (or horizontal rule) and is typically displayed as a horizontal line, which is a block-level behavior.
#### Breaks
```html
<br>
```
#### Horizontal Rule
```html
<hr>
```
#### word break
```html
<wbr>
```

# CSS
## Selectors

> Selectors are used to "find" (or select) the HTML elements you want to style.

### Overview
```css
// ID and Class Selectors
div #♾️() {} 	// ID Selector
div .♾️() {} 	// Class Selector

// Descendant Selectors
div p {} 	// Descendant Selector 
div > p {} 	// Child Selector
div + p {} 	// Adjacent Sibling Selector
div - p {} 	// Subsequent Sibling Selector
div ~ p {} 	// General Sibling Selector
div * {} 	// Universal Selector 

// Grouping Selectors
div , p {} 	// Group Selector 
div | p {} 	// Column Selector 

// Attribute Selectors
div = p {} 	// Attribute Selector
div / p {} 	// Path Selector

// Pseudo Selectors
div : p {} 	// Psuedo-class Selector
div :: p {} // Psuedo-element Selector

// Pseudo-class Selectors
:not() {} , :matches(p) {} , :nth-child(p) {} , :nth-last-child(p) {} , :nth-last-of-type(p) {} , :nth-of-type(p) {} , :only-child {} , :only-of-type {} , :root {} , :target {} , :where() {} , :has() {} , :is() {} , :dir() {} , :lang() {} , :scope() {} , :current() {} , :past() {} , :future() {} , :active {} , :any() {} , :blank {} , :checked {} , :default {} , :disabled {} , :empty {} , :enabled {} , :first {} , :first-child {} , :first-of-type {} , :fullscreen {} , :focus {} , :hover {} , :indeterminate {} , :in-range {} , :invalid {} , :last-child {} , :last-of-type {} , :left {} , :link {} , :not() {} , :nth-child() {} , :nth-last-child() {} , :nth-last-of-type() {} , :nth-of-type() {} , :only-child {} , :only-of-type {} , :optional {} , :out-of-range {} , :read-only {} , :read-write {} , :required {} , :right {} , :root {} , :scope {} , :target {} , :valid {} , :visited {} , :where() {} , :default {} , :dir() {} , :drop() {} , :fullscreen {} , :host() {} , :host-context() {} , :indeterminate {} , :is() {} , :lang() {} , :matches() {} , :not() {} , :nth-child() {} , :nth-last-child() {} , :nth-last-of-type() {} , :nth-of-type() {} , :placeholder-shown {} , :read-only {} , :read-write {} , :required {} , :right {} , :root {} , :scope {} , :target {} , :valid {} , :visited {} , :where() {} , :active {} , :any-link {} , :blank {} , :checked {} , :current {} , :default {} , :defined {} , :disabled {} , :drop {} , :empty {} , :enabled {} , :first {} , :first-child {} , :first-of-type {} , :fullscreen {} , :focus {} , :focus-visible {} , :focus-within {} , :future {} , :hover {} , :in-range

// Pseudo-element Selectors
::after {} , ::before {} , ::cue {} , ::first-letter {} , ::first-line {} , ::grammar-error {} , ::marker {} , ::placeholder {} , ::selection {} , ::slotted() {} , ::spelling-error {} , ::backdrop {} , ::cue() {} , ::part() {} , ::placeholder-shown {} , ::selection {} , ::slotted() {} , ::target-text {} , ::after {} , ::before {}
```

<details><summary>Most common selectors</summary>

| Selector | Example | Example description |
| --- | --- | --- |
| * | * | Selects all elements |
| .class | .intro | Selects all elements with class="intro" |
| #id | #firstname | Selects the element with id="firstname" |
| element | p | Selects all \<p> elements |
| element,element | div, p | Selects all \<div> elements and all \<p> elements |
| element element | div p | Selects all \<p> elements inside \<div> elements |
| element>element | div > p | Selects all \<p> elements where the parent is a \<div> element |
| element+element | div + p | Selects all \<p> elements that are placed immediately after \<div> elements |
| element1~element2 | p ~ ul | Selects every \<ul> element that are preceded by a \<p> element |
| [attribute] | [target] | Selects all elements with a target attribute |
| [attribute=value] | [target=_blank] | Selects all elements with target="_blank" |
| [attribute~=value] | [title~=flower] | Selects all elements with a title attribute containing the word "flower" |
| [attribute\|=value] | [lang\|=en] | Selects all elements with a lang attribute value starting with "en" |

</details>

<details><summary>Psuedo-class selectors</summary>

| Selector | Example | Example description |
| --- | --- | --- |
| :active | a:active | Selects the active link |
| ::after | p::after | Insert something after the content of each \<p> element |
| ::before | p::before | Insert something before the content of each \<p> element |
| :checked | input:checked | Selects every checked \<input> element |
| :disabled | input:disabled | Selects every disabled \<input> element |
| :empty | p:empty | Selects every \<p> element that has no children (including text nodes) |
| :enabled | input:enabled | Selects every enabled \<input> element |
| :first-child | p:first-child | Selects every \<p> element that is the first child of its parent |
| ::first-letter | p::first-letter | Selects the first letter of every \<p> element |
| ::first-line | p::first-line | Selects the first line of every \<p> element |
| :first-of-type | p:first-of-type | Selects every \<p> element that is the first \<p> element of its parent |
| :focus | input:focus | Selects the input element which has focus |
| :hover | a:hover | Selects links on mouse over |
| :in-range | input:in-range | Selects input elements with a value within a specified range |
| :invalid | input:invalid | Selects all input elements with an invalid value |
| :lang(language) | p:lang(it) | Selects every \<p> element with a lang attribute value starting with "it" |
| :last-child | p:last-child | Selects every \<p> element that is the last child of its parent |
| :last-of-type | p:last-of-type | Selects every \<p> element that is the last \<p> element of its parent |
| :link | a:link | Selects all unvisited links |
| ::marker | li::marker | Selects the marker box of a list item |
| :nth-child(n) | p:nth-child(2) | Selects every \<p> element that is the second child of its parent |
| :nth-last-child(n) | p:nth-last-child(2) | Selects every \<p> element that is the second child of its parent, counting from the last child |
| :nth-last-of-type(n) | p:nth-last-of-type(2) | Selects every \<p> element that is the second \<p> element of its parent, counting from the last child |
| :nth-of-type(n) | p:nth-of-type(2) | Selects every \<p> element that is the second \<p> element of its parent |
| :not(selector) | :not(p) | Selects every element that is not a \<p> element |
| :only-of-type | p:only-of-type | Selects every \<p> element that is the only \<p> element of its parent |
| :only-child | p:only-child | Selects every \<p> element that is the only child of its parent |
| :optional | input:optional | Selects input elements with no "required" attribute |
| ::placeholder | input::placeholder | Selects input elements with placeholder text specified |
| :read-only | input:read-only | Selects input elements with the "readonly" attribute specified |
| :read-write | input:read-write | Selects input elements with the "readonly" attribute NOT specified |
| :required | input:required | Selects input elements with the "required" attribute specified |
| :root | :root | Selects the document's root element |
| ::selection | ::selection | Selects the portion of an element that is selected by a user |
| :target | #news:target | Selects the current active #news element (clicked on a URL containing that anchor name) |
| :valid | input:valid | Selects all input elements with a valid value |
| :visited | a:visited | Selects all visited links |

</details>

### Element Selector
```css
p {}
```
### #id Selector
```css
#unique {}
```
### .class Selector
```css
.classname {}
```
### Universal Selector
> The universal selector (*) selects all HTML elements on the page.
```css
* {}
```
### Group Selector
> The group selector selects all the \<h1>, \<h2> and \<p> elements in a page.
```css
h1, h2, p {}
```
### Descendant Selector
> The descendant selector matches all elements that are descendants of a specified element.
```css
div p {}
```
### Child Selector
> The child selector selects all elements that are the children of a specified element.
```css
div > p {}
```
### Adjacent Sibling Selector
> The adjacent sibling selector selects all elements that are the immediately following siblings of a specified element.
```css
div + p {}
```
### General Sibling Selector
> The general sibling selector selects all elements that are siblings of a specified element.
>
> This example selects all \<p> elements that are siblings of \<div> elements:
```css
div ~ p {}
```

### Attribute Selector
> The CSS attribute selector matches elements based on the presence or value of a given attribute.
```css
a[target] {}
```
### Attribute Value Selector
> The CSS attribute value selector matches elements based on the presence or value of a given attribute.
```css
a[target="_blank"] {}
```
### Attribute Value Starts With Selector
```css
a[href^="https"] {}
```
### Attribute Value Ends With Selector
```css
a[href$=".pdf"] {}
```
### Attribute Value Contains Selector
```css
a[href*="w3schools"] {}
```
### Attribute Value Contains Word Selector
```css
a[href~="w3schools"] {}
```
### Attribute Value Contains Prefix Selector
```css
a[href|="https"] {}
```
### Pseudo-classes
> A pseudo-class is used to define a special state of an element.
```css
a:hover {}
```
### Pseudo-elements
> A CSS pseudo-element is used to style specified parts of an element.
```css
	p::first-line {}
```
### Combinators
> Combinators are used to combine multiple selectors into more specific selectors.
```css
div p {}
```
### Multiple Selectors
```css
h1, h2, p {}
```
## CSS Comments
```css
/* This is a single-line comment */
```

## Units
> CSS has several different units for expressing a length.

| --- | Unit | Description |
| --- | --- | --- |
| 💚 | % | Relative to the parent element |
| 💚 | px | pixels |
| 💚 | em | Relative to the font-size of the element |
| 💚 | rem | Relative to font-size of the root element |
| 💚 | vw | Relative to 1% of the width of the viewport* |
| 💚 | vh | Relative to 1% of the height of the viewport* |
| | vmin | Relative to 1% of viewport's* smaller dimension |
| | vmax | Relative to 1% of viewport's* larger dimension |
|||
| | cm | centimeters |
| | mm | millimeters |
| | in | inches (1in = 96px = 2.54cm) |
| 💛 | pt | points (1pt = 1/72 of 1in) |
| | pc | picas (1pc = 12 pt) |
| | ex | Relative to the x-height of the current font (rarely used) |
| | ch | Relative to width of the "0" (zero) |

## Colors
### Notations
> RGB, RGBA, HEX, HSL, HSLA

| --- | Color | Description |
| --- | --- | --- |
| 💚 | rgb(0,0,0) | 0-256 Red Green Blue |
| 💚 | rgba(0,0,0,0) | 0-256 Red Green Blue Opacity |
| 💚 | #000000 | Hexadecimal Red Blue Green |
| 💚 | hsl(0,0%,0%) | Hue Saturation Lightness |
| 💚 | hsla(0,0%,0%,0) | Hue Saturation Lightness Opacity |

### Color Names
> CSS has 147 predefined color names that can be used without any prior declaration:
```css
Aqua, Black, Blue, Fuchsia, Gray, Green, Lime, Maroon, Navy, Olive, Orange, Purple, Red, Silver, Teal, White, Yellow ...
```

## Text Properties
### Font
```css
font-family: "Times New Roman", Times, serif;
font-size: 20px;
font-weight: bold;
font-style: italic;
font-variant: small-caps;
```
### Text
```css
color: #000000;
text-align: center;
text-decoration: underline;
text-indent: 50px;
text-shadow: 2px 2px 5px #FF0000;
text-transform: uppercase;
line-height: 1.5;
letter-spacing: 2px;
word-spacing: 5px;
white-space: nowrap;
```
### Links
```css
a:link {color: #FF0000;}		/* unvisited link */
a:visited {color: #00FF00;}		/* visited link */
a:hover {color: #FF00FF;}		/* mouse over link */
a:active {color: #0000FF;}		/* selected link */
```
### Lists
```css
list-style-type: disc;
list-style-position: inside;
list-style-image: url('sqpurple.gif');
```
### Tables
```css
table, th, td {
	border: 1px solid black;
	border-collapse: collapse;
}
```
### Quotes
```css
q:lang(no) {quotes: "«" "»" "‹" "›";}
q:lang(en) {quotes: "“" "”" "‘" "’";}
```
### Icons
```css
.icon {
	width: 16px;
	height: 16px;
	background-image: url('img_tree.png');
}
```
### Opacity
```css
div {
	opacity: 0.5;
}
```
### Cursor
```css
div {
	cursor: pointer; // auto, default, none, context-menu, help, pointer, progress, wait, cell, crosshair, text, vertical-text, alias, copy, move, no-drop, not-allowed, e-resize, n-resize, ne-resize, nw-resize, s-resize, se-resize, sw-resize, w-resize, ew-resize, ns-resize, nesw-resize, nwse-resize, col-resize, row-resize, all-scroll, zoom-in, zoom-out, grab, grabbing
}
```
### User Select
```css
div {
	user-select: none; // none, auto, text, contain, all
}
```
### Resize
```css
div {
	resize: both; // horizontal, vertical, none, both
}
```
### Box Sizing
```css
div {
	box-sizing: border-box;  // include padding and border in the width and height
	box-sizing: content-box; // default
}
```



