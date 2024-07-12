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
   <h1>Hello</h1>
   <p>World.</p>
   </body>
   </html>
   ```

2. **Internal CSS:**
   An internal style sheet may be used if one single HTML page has a unique style. 
   ```html
  
   <html>
   <head>
   <style>
   body {
     background-color: linen;
   }
   </style>
   </head>
   <body>
    ...
   </body>
   ```

3. **Inline CSS:**
   An inline style may be used to apply a unique style for a single element.

   ```html
   <h1 style="color:blue;text-align:center;">Hello</h1>
   <p style="color:red;">World</p>
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

.main-header {
  background-color: $primary_1;
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
$variablename: somevalue;
```



## SASS Variables Scope

Sass variables are only available at the level of nesting where they are defined. The default behavior for variable scope can be overridden by using the `!global` switch.

```scss
$Color: red;
h1 {
  $Color: green !global;
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

# Sass String Functions

The string functions are used to manipulate and get information about strings. Sass strings are 1-based. The first character in a string is at index 1, not 0.
# Sass String Functions

| Function                          | Description & Example                                                                                   |
|-----------------------------------|---------------------------------------------------------------------------------------------------------|
| `quote(string)`                   | Adds quotes to string, and returns the result.                                                          |
|                                   | **Example:** `quote(Hello world!)`<br>**Result:** `"Hello world!"`                                       |
| `str-index(string, substring)`    | Returns the index of the first occurrence of the substring within string.                               |
|                                   | **Example:** `str-index("Hello world!", "H")`<br>**Result:** `1`                                        |
| `str-insert(string, insert, index)`| Returns string with insert inserted at the specified index position.                                   |
|                                   | **Example:** `str-insert("Hello world!", " wonderful", 6)`<br>**Result:** `"Hello wonderful world!"`    |
| `str-length(string)`              | Returns the length of string (in characters).                                                           |
|                                   | **Example:** `str-length("Hello world!")`<br>**Result:** `12`                                           |
| `str-slice(string, start, end)`   | Extracts characters from string; start at start and end at end, and returns the slice.                  |
|                                   | **Example:** `str-slice("Hello world!", 2, 5)`<br>**Result:** `"ello"`                                  |
| `to-lower-case(string)`           | Returns a copy of string converted to lower case.                                                       |
|                                   | **Example:** `to-lower-case("Hello World!")`<br>**Result:** `"hello world!"`                            |
| `to-upper-case(string)`           | Returns a copy of string converted to upper case.                                                       |
|                                   | **Example:** `to-upper-case("Hello World!")`<br>**Result:** `"HELLO WORLD!"`                            |
| `unique-id()`                     | Returns a unique randomly generated unquoted string (guaranteed to be unique within the current sass session).|
|                                   | **Example:** `unique-id()`<br>**Result:** `tyghefnsv`                                                   |
| `unquote(string)`                 | Removes quotes around string (if any), and returns the result.                                          |
|                                   | **Example:** `unquote("Hello world!")`<br>**Result:** `Hello world!`                                    |


# Sass List Functions

The list functions are used to access values in a list, combine lists, and add items to lists.

Sass lists are immutable (they cannot change). So, the list functions that return a list, will return a new list, and not change the original list.

Sass lists are 1-based. The first list item in a list is at index 1, not 0.

The following table lists all list functions in Sass:

| Function                           | Description & Example                                                                                     |
|------------------------------------|-----------------------------------------------------------------------------------------------------------|
| `append(list, value, [separator])` | Adds a single value to the end of the list. `separator` can be `auto`, `comma`, or `space`. `auto` is default.|
|                                    | **Example:** `append((a b c), d)`<br>**Result:** `a b c d`<br>**Example:** `append((a b c), (d), comma)`<br>**Result:** `a, b, c, d` |
| `index(list, value)`               | Returns the index position for the value in list.                                                         |
|                                    | **Example:** `index(a b c, b)`<br>**Result:** `2`<br>**Example:** `index(a b c, f)`<br>**Result:** `null` |
| `is-bracketed(list)`               | Checks whether the list has square brackets.                                                              |
|                                    | **Example:** `is-bracketed([a b c])`<br>**Result:** `true`<br>**Example:** `is-bracketed(a b c)`<br>**Result:** `false` |
| `join(list1, list2, [separator, bracketed])` | Appends `list2` to the end of `list1`. `separator` can be `auto`, `comma`, or `space`. `auto` is default (will use the separator in the first list). `bracketed` can be `auto`, `true`, or `false`. `auto` is default. |
|                                    | **Example:** `join(a b c, d e f)`<br>**Result:** `a b c d e f`<br>**Example:** `join((a b c), (d e f), comma)`<br>**Result:** `a, b, c, d, e, f`<br>**Example:** `join(a b c, d e f, $bracketed: true)`<br>**Result:** `[a b c d e f]` |
| `length(list)`                     | Returns the length of the list.                                                                            |
|                                    | **Example:** `length(a b c)`<br>**Result:** `3`                                                           |
| `list-separator(list)`             | Returns the list separator used, as a string. Can be either `space` or `comma`.                            |
|                                    | **Example:** `list-separator(a b c)`<br>**Result:** `"space"`<br>**Example:** `list-separator(a, b, c)`<br>**Result:** `"comma"` |
| `nth(list, n)`                     | Returns the nth element in the list.                                                                       |
|                                    | **Example:** `nth(a b c, 3)`<br>**Result:** `c`                                                           |
| `set-nth(list, n, value)`          | Sets the nth list element to the value specified.                                                          |
|                                    | **Example:** `set-nth(a b c, 2, x)`<br>**Result:** `a x c`                                                |
| `zip(lists)`                       | Combines lists into a single multidimensional list.                                                        |
|                                    | **Example:** `zip(1px 2px 3px, solid dashed dotted, red green blue)`<br>**Result:** `1px solid red, 2px dashed green, 3px dotted blue` |

# Sass Map Functions

In Sass, the map data type represents one or more key/value pairs.

Sass maps are immutable (they cannot change). So, the map functions that return a map, will return a new map, and not change the original map.

The following table lists all map functions in Sass:

| Function                         | Description & Example                                                                                     |
|----------------------------------|-----------------------------------------------------------------------------------------------------------|
| `map-get(map, key)`              | Returns the value for the specified key in the map.                                                       |
|                                  | **Example:**<br>`$font-sizes: ("small": 12px, "normal": 18px, "large": 24px)`<br>`map-get($font-sizes, "small")`<br>**Result:** `12px` |
| `map-has-key(map, key)`          | Checks whether map has the specified key. Returns true or false.                                          |
|                                  | **Example:**<br>`$font-sizes: ("small": 12px, "normal": 18px, "large": 24px)`<br>`map-has-key($font-sizes, "big")`<br>**Result:** `false` |
| `map-keys(map)`                  | Returns a list of all keys in map.                                                                        |
|                                  | **Example:**<br>`$font-sizes: ("small": 12px, "normal": 18px, "large": 24px)`<br>`map-keys($font-sizes)`<br>**Result:** `"small", "normal", "large"` |
| `map-merge(map1, map2)`          | Appends map2 to the end of map1.                                                                          |
|                                  | **Example:**<br>`$font-sizes: ("small": 12px, "normal": 18px, "large": 24px)`<br>`$font-sizes2: ("x-large": 30px, "xx-large": 36px)`<br>`map-merge($font-sizes, $font-sizes2)`<br>**Result:** `"small": 12px, "normal": 18px, "large": 24px, "x-large": 30px, "xx-large": 36px` |
| `map-remove(map, keys...)`       | Removes the specified keys from map.                                                                      |
|                                  | **Example:**<br>`$font-sizes: ("small": 12px, "normal": 18px, "large": 24px)`<br>`map-remove($font-sizes, "small")`<br>**Result:** `("normal": 18px, "large": 24px)`<br>`map-remove($font-sizes, "small", "large")`<br>**Result:** `("normal": 18px)` |
| `map-values(map)`                | Returns a list of all values in map.                                                                      |
|                                  | **Example:**<br>`$font-sizes: ("small": 12px, "normal": 18px, "large": 24px)`<br>`map-values($font-sizes)`<br>**Result:** `12px, 18px, 24px` |

# Sass Color Functions

## 1. Sass Set Color Functions

- `rgb(red, green, blue)`
- `rgba(red, green, blue, alpha)`
- `hsl(hue, saturation, lightness)`

## 2. Sass Get Color Functions

- `red(color)`

  **Example:**
  ```scss
  red(#7fffd4);
  // Result: 127

  red(red);
  // Result: 255
  
## 3. Sass Manipulate Color Functions
- `adjust-hue(color, degrees)`
- `mix(color1, color2, weight)`

