# Coding Standards
Style guide and coding standards that have to be taken into account when writing HTML(5), (S)CSS and Javascript in Danagi projects.

## Table of contents

- [Background](#background)
- [General](#general)
    - [Indentation](#indentation)
        - [HTML](#html)
        - [CSS](#css)
        - [Javascript](#javascript)
    - [Trailing Whitespace](#trailing-whitespace)
    - [Avoid long lines of code](#avoid-long-lines-of-code)
    - [Line endings](#line-endings)
    - [Encoding](#encoding)
    - [Comments](#comments)
    - [Use filenames in lower case](#use-filenames-in-lower-case)
    - [File Extensions](#file-extensions)

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

#### CSS
```css
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

CSS files must have a **.css** extension.

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

<!-- Wrong -->
<input type=text name=title size=20>
```

### Spaces and Equal Signs

Spaces around equal signs are not allowed.

```html
<!-- Correct -->
<link rel="stylesheet" href="styles.css">

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

