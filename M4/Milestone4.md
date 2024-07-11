# Milestone 4

## 1. What and Why CSS?

Cascading Style Sheets (CSS) is a stylesheet language used to describe the presentation of a document written in HTML. CSS describes how elements should be rendered on screen. It can control the layout of multiple web pages all at once. External stylesheets are stored in CSS files.

When tags like `<font>`, and color attributes were added to the HTML 3.2 specification, it started a nightmare for web developers. Development of large websites, where fonts and color information were added to every single page, became a long and expensive process.

### Three Ways to Insert CSS

There are three ways of inserting a style sheet:

1. **External CSS:**
   With an external style sheet, you can change the look of an entire website by changing just one file. External styles are defined within the `<link>` element, inside the `<head>` section of an HTML page:

   ```html
   <!DOCTYPE html>
   <html>
   <head>
   <link rel="stylesheet" href="mystyle.css">
   </head>
   <body>
   <h1>This is a heading</h1>
   <p>This is a paragraph.</p>
   </body>
   </html>
   ```

2. **Internal CSS:**
   An internal style sheet may be used if one single HTML page has a unique style. The internal style is defined inside the `<style>` element, inside the head section.

   ```html
   <!DOCTYPE html>
   <html>
   <head>
   <style>
   body {
     background-color: linen;
   }
   h1 {
     color: maroon;
     margin-left: 40px;
   }
   </style>
   </head>
   <body>
   <h1>This is a heading</h1>
   <p>This is a paragraph.</p>
   </body>
   ```

3. **Inline CSS:**
   An inline style may be used to apply a unique style for a single element.

   ```html
   <h1 style="color:blue;text-align:center;">This is a heading</h1>
   <p style="color:red;">This is a paragraph.</p>
   ```

### Cascading Order:

All the styles in a page will "cascade" into a new "virtual" style sheet by the following rules, where number one has the highest priority:

1. Inline style (inside an HTML element)
2. External and internal style sheets (in the head section)
3. Browser default

## 2. SASS and SCSS:

- Sass stands for Syntactically Awesome Stylesheet. Sass is an extension to CSS. Sass is a CSS pre-processor. Sass is completely compatible with all versions of CSS. 

```scss
$primary_1: #a2b9bc;
$primary_2: #b2ad7f;
$primary_3: #878f99;

/* use the variables */
.main-header {
  background-color: $primary_1;
}
.menu-left {
  background-color: $primary_2;
}
```

- A browser does not understand Sass code. Therefore, you will need a Sass pre-processor to convert Sass code into standard CSS.
- This process is called transpiling. So, you need to give a transpiler (some kind of program) some Sass code and then get some CSS code back.

### SASS variables:

Sass Variables are a way to store information that you can re-use later.
With Sass, you can store information in variables, like:
- strings
- numbers
- colors
- Booleans
- lists
- nulls

Syntax:
```scss
$variablename: value;
```



## SASS Variables Scope

Sass variables are only available at the level of nesting where they are defined. The default behavior for variable scope can be overridden by using the `!global` switch.

```scss
$myColor: red;
h1 {
  $myColor: green !global;
  color: $myColor;
}
```

## SASS Nesting

Sass lets you nest CSS selectors in the same way as HTML.

```scss
nav {
  ul {
    margin: 0;
    padding: 0;
    list-style: none;
  }
}
```

## SASS Nested Properties

```scss
font: {
  family: Helvetica, sans-serif;
  size: 18px;
  weight: bold;
}
text: {
  align: center;
  transform: lowercase;
  overflow: hidden;
}  
```

Instead of:

```css
font-family: Helvetica, sans-serif;
font-size: 18px;
font-weight: bold;
```

## SASS @import

The CSS `@import` directive has a major drawback due to performance issues; it creates an extra HTTP request each time you call it. However, the Sass `@import` directive includes the file in the CSS; so no extra HTTP call is required at runtime.

```scss
@import "variables";
@import "colors";
@import "reset";
```

## SASS Partials

By default, Sass transpiles all the `.scss` files directly. However, when you want to import a file, you do not need the file to be transpiled directly. Sass has a mechanism for this: If you start the filename with an underscore, Sass will not transpile it. Files named this way are called partials in Sass.

So, a partial Sass file is named with a leading underscore. 

Sass Partial Syntax:
```
_filename;
```

## SASS Mixins and Include

The `@mixin` directive lets you create CSS code that is to be reused throughout the website. The `@include` directive is created to let you use (include) the mixin.

Example:

```scss
@mixin important-text {
  color: red;
  font-size: 25px;
  font-weight: bold;
  border: 1px solid blue;
}

.danger {
  @include important-text;
  background-color: green;
}
```

This will compile to:

```css
.danger {
  color: red;
  font-size: 25px;
  font-weight: bold;
  border: 1px solid blue;
  background-color: green;
}
```

## Passing Variables to a Mixin

Mixins can accept variables as parameters, allowing for more flexible and reusable styles:

```scss
@mixin bordered($color, $width) {
  border: $width solid $color;
}

.myArticle {
  @include bordered(blue, 1px);  // Call mixin with two values
}
```

## Default Values for a Mixin

You can set default values for mixin parameters:

```scss
@mixin bordered($color: blue, $width: 1px) {
  border: $width solid $color;
}
```

## Extend Directive

The `@extend` directive lets you share a set of CSS properties from one selector to another. The `@extend` directive is useful if you have almost identically styled elements that only differ in some small details.

Example:

```scss
.button-basic  {
  border: none;
  padding: 15px 30px;
  text-align: center;
  font-size: 16px;
  cursor: pointer;
}

.button-report  {
  @extend .button-basic;
  background-color: red;
}
```
```

