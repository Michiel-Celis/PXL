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
			- [Element Selector](#element-selector)
			- [ID Selector](#id-selector)
			- [Class Selector](#class-selector)
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

## CSS
### Selectors
> Selectors are used to "find" (or select) the HTML elements you want to style.
#### Element Selector
```css
p {}
```
#### ID Selector
```css
#unique {}
```
#### Class Selector
```css
.classname {}
```
#### Universal Selector
```css
* {}
```
#### Group Selector
```css
h1, h2, p {}
```
#### Descendant Selector
```css
div p {
  color: red;
}
```
#### Child Selector
```css
div > p {
  color: red;
}
```
#### Adjacent Sibling Selector
```css
div + p {
  color: red;
}
```
#### General Sibling Selector
```css
div ~ p {
  color: red;
}
```
#### Attribute Selector
```css
a[target] {
  color: red;
}
```
#### Attribute Value Selector
```css
a[target="_blank"] {
  color: red;
}
```
#### Attribute Value Starts With Selector
```css
a[href^="https"] {
  color: red;
}
```
#### Attribute Value Ends With Selector
```css
a[href$=".pdf"] {
  color: red;
}
```
#### Attribute Value Contains Selector
```css
a[href*="w3schools"] {
  color: red;
}
```
#### Attribute Value Contains Word Selector
```css
a[href~="w3schools"] {
  color: red;
}
```
#### Attribute Value Contains Prefix Selector
```css
a[href|="https"] {
  color: red;
}
```
#### Pseudo-classes
```css
a:hover {
  color: red;
}
```
#### Pseudo-elements
```css
p::first-line {
  color: red;
}
```
#### Combinators
```css
div p {
  color: red;
}
```
#### Multiple Selectors
```css
h1, h2, p {
  color: red;
}
```
#### CSS Comments
```css
/* This is a single-line comment */
```
```css
