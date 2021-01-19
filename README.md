# Coding Standards
Style guide and coding standards that have to be taken into account when writing HTML(5), SCSS and Javascript in Danagi projects.

## Table of contents

- [Background](#background)
- [General](#general)
    - [Indentation](#indentation)
        - [HTML](#html)
        - [SCSS](#scss)
        - [Javascript](#javascript)
    - [Trailing Whitespace](#trailing-whitespace)
    - [Avoid long lines of code](#avoid-long-lines-of-code)
    - [Line endings](#line-endings)
    - [Encoding](#encoding)
    - [Comments](#comments)
    - [Use filenames in lower case](#use-filenames-in-lower-case)
    - [File Extensions](#file-extensions)
- [HTML Style Rules](#html-style-rules)
- [SCSS Style Rules](#scss-style-rules)
- [Javascript Style Rules](#javascript-style-rules)

## Background
This document defines formatting and style rules for HTML, CSS. and Javascript The aim is to standardize and maintain the cooperation and the code quality. This applies to unformatted work files that use HTML, CSS and Javascript.

## General

### Indentation

Indent by 4 spaces at a time.

Don’t use tabs or mix tabs and spaces for indentation.

#### HTML
```html
<ul>
    <li>That</li>
    <li>is</li>
    <li>right</li>
</ul>
```

#### SCSS
```scss
.example {
    color: blue;
}
```

#### Javascript
```javascript
function example() {
    return 'Hello world!';
}
```

### Trailing Whitespace

Remove trailing white spaces.

### Avoid long lines of code

When using an HTML editor, it is inconvenient to scroll right and left to read the HTML code.

Vermeiden Sie Codezeilen mit mehr als 100 Zeichen.

### Line endings

Format files with `\n` at the end of a line (Unix line endings). Do not use `\r\n` (Windows line endings) or `\r` (Apple operating systems).

### Encoding

Use UTF-8 (no BOM).

Make sure your editor uses UTF-8 as the character encoding with no byte order mark.

Specify the coding in HTML templates and documents using `<meta charset="utf-8" />`. Do not specify the encoding of style sheets as they require UTF-8.

(For more information about encodings and when and how to specify them, see Working with Character Encodings in HTML and CSS.)

### Comments

Explain the code as needed, if possible.

Use comments to explain the code: what does it cover, what is its purpose, why is each solution used or preferred?

### Use filenames in lower case

To avoid problems and inconsistencies, all file names are given in lowercase letters. For better readability and to separate individual words, a kebab case is used:

```
<!-- Correct -->
johndoe.jpg
hello-world.html
script-name.js
style-sheet.css
```
```
<!-- Wrong -->
johndoe.JPG
HelloWorld.html
scriptName.js
style_sheet.css
```

### File Extensions

HTML files must have a **.html** extension.

SCSS files must have a **.scss** extension.

JavaScript files must have a **.js** extension.

## HTML Style Rules

### Write valid HTML

All HTML code must be valid and well-formed. You need to validate it against the HTML specification for the project you are working on. Use the HTML5 document type definition unless a different specification is requested or needed:

```html
<!doctype html>
```

### Document Type

Use HTML5.

(It is recommended to use HTML as text/html. Don't use XHTML. XHTML as an application/xhtml+xml does not offer any browser or infrastructure support and offers less room for optimization than HTML.)

### Lowercase names

Element and attribute names must be in lowercase:

```html
<!-- Correct -->
<input name="name" type="text">
```
```html
<!-- Wrong -->
<INPUT name="name" TYPE="text">
```

### Closing tags

Non-empty elements must have appropriate closing tags.

```html
<h1>My title</h1>
<p>Some text</p>
``` 

A corresponding closing tag must follow empty elements:

```html
<span></span>
<i></i>
```

Items with a single tag, such as `hr`, `br`, `input`, `img` must end with `>`:

```html
<br>
<hr>
<img src="example.jpg" alt="Description text" width="500" height="200">
```

### Nested elements

Nested elements must be nested accordingly - for example:

```html
<!-- Correct -->
<div>
    <p>Some text</p>
</div>
```

The `<p>` tag and the corresponding closing tag `</p>` are both nested in the `<div>` and `</div>` tags.

If elements overlap, they are not properly nested. The following code demonstrates this:

```html
<!-- Wrong -->
<div>
    <p>Some text</div>
</p>
```

### Attribute values

Attribute values, including numeric attributes, must be placed in quotation marks - for example:

```html
<!-- Correct -->
<input type="text" name="title" size="20">
```
```html
<!-- Wrong -->
<input type=text name=title size=20>
```

### Spaces and Equal Signs

Spaces around equal signs are not allowed.

```html
<!-- Correct -->
<link rel="stylesheet" href="styles.css">
```
```html
<!-- Wrong -->
<link rel = "stylesheet" href = "styles.css">
```

### Special characters

Encode special characters, for example:

```html
&amp;
&quot;
&copy;
```

### HTML anchors

If you need to link to a section in an HTML document, use the ID attribute:

```html
<!-- Correct -->
<a href="#anchor">Link</a>
<div id="anchor"></div>
```

The use of named anchors is prohibited.

```html
<!-- Wrong -->
<a href="#anchor">Link</a>
<a name="anchor"></a>
```

## SCSS Style Rules

SCSS is used to expand the bootstrap styles!

Use nested style rules instead of repeating the same selectors over and over:

```scss
nav {

    li {
        display: inline-block;
        
        a {
            display: block;
            padding: 6px 12px;
            text-decoration: none;
        }
    }
}
```

#### Watch out!

Nested rules are very helpful, but they can also make it difficult to visualize the actual CSS data generated. The deeper you nest, the more bandwidth it takes to serve your CSS and the more work it takes the browser to render it. Keep the selectors flat!

### Notation of selectors

The kebab case notation is used in SCSS: Multiple words are usually separated with minus (-) in CSS selectors. All letters are lowercase. Class names start with a letter.

```scss
/* Correct */
.my-selector {}
```
```scss
/* Wrong */
.my_selector {}
.mySelector {}
```

### Selector Lists

In order to be able to read the individual rules faster, individual selectors are written in lists, each of which is on a separate line. Likewise, the rules are each written on a separate line:

```scss
.selector,
.another-selector {
    ul,
    p {
        margin-right: 0;
        margin-left: 0;
        padding-bottom: 0;
    }
}
```

### Selector Combinators

With nested selectors, cobiners are always placed at the beginning of the inner selector.

```scss
/* Correct */
h2 {
    + p {
        border-top: 1px solid gray;
    }
}
```
```scss
/* Wrong */
ul > {
    li {
        list-style-type: none;
    }
}

p {
    ~ {
        span {
            opacity: 0.8;
        }
    }
}
```

### Comments

Only silent comments are used in SCSS and are not output as CSS.

Single-line comments should be treated like multi-line comments. These always begin with `/*`, end with `*/` and each individual line begins with `*`.

```scss
/* Correct */
/* Single line comment */
/* Comment
 * about
 * multiple
 * Lines
 */
```
```scss
// Wrong
// Single line comment
/*! loud comment */
```

### Order of rules

For a uniform and regulated cooperation, the details are given in the following order:

1. List @extend(s) First
1. List @include(s) Next
1. List “Regular” Styles Next
1. Nested Pseudo Classes and Pseudo Elements Next
1. Nested Selectors Last

```scss
.anything {
    @extend %module; 
    @include transition(all 0.3s ease);
    
    background: green;
    
    &:hover {
        background: red;
    }
    
    &::before {
        content: "";
        display: block;
    }
    
    > h3 {
        @include transform(rotate(90deg));
        border-bottom: 1px solid white;
    }
}
```


### Never Write Vendor Prefixes

Vendor prefixes are time-sensitive. As browsers get updated over time, the need for them will disappear. If you are using autoprefixer when compiling Sass, you should never have to write it.

Use Bootstrap's autoprefixer to avoid writing these manually.

### Maximum Nesting: Three Levels Deep

If you get deeper, you're probably writing a crappy selector. It sucks that it depends too heavily on the HTML structure (fragile), too specific (too powerful), and not very reusable (not useful). It's hard to understand even on the edge.

```scss
header {
    .nav {
        li {
            // no more!
        }
    }
}
```

## Javascript Style Rules

### Variable Names

At Danagi we use camelCase for identifier names (variables and functions).

All names start with a letter.

Names of jQuery objects are preceded by a dollar sign.

```javascript
var firstName = 'John';
var age = 49;
var $div = $('div#id');
```

### Spaces Around Operators

Always put spaces around operators ( = + - * / ), and after commas:

```javascript
var x = y + z;
var name = ["John", "Public", "Doe"];
```

### Statement Rules

#### General rules for simple statements

- Always end a simple statement with a semicolon.

```javascript
var values = ["Volkswagen", "Audi", "Tesla"];

var person = {
    firstName: "John",
    lastName: "Doe",
    age: 50
};
```

#### General rules for complex (compound) statements:

- Put the opening bracket at the end of the first line.
- Use one space before the opening bracket.
- Put the closing bracket on a new line, without leading spaces.
- Do not end a complex statement with a semicolon.

```javascript
function toCelsius(fahrenheit) {
    return (5 / 9) * (fahrenheit - 32);
}

for (i = 0; i < 5; i++) {
    x += i;
}

if (time < 20) {
  greeting = "Good day";
} else {
  greeting = "Good evening";
}
```

#### Object Rules

- Place the opening bracket on the same line as the object name.
- Use colon plus one space between each property and its value.
- Use quotes around string values, not around numeric values.
- Do not add a comma after the last property-value pair.
- Place the closing bracket on a new line, without leading spaces.
- Always end an object definition with a semicolon.

```javascript
var person = {
    firstName: "John",
    lastName: "Doe",
    age: 50
};
```

Single-line writing of short objects is not permitted.

