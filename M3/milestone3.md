# Milestone 3

## 1. Forms, Lists and Tables

### 1.1 Forms

- HTML forms collect user input, often sent to a server for processing.
- The `<form>` element contains different types of input elements.

#### Input Types

| Type | Description |
|------|-------------|
| `<input type="text">` | Single-line text input field |
| `<input type="radio">` | Radio button (for selecting one of many choices) |
| `<input type="checkbox">` | Checkbox (for selecting zero or more of many choices) |
| `<input type="submit">` | Submit button (for submitting the form) |
| `<input type="button">` | Clickable button |

#### Label

- The `<label>` tag defines a label for form elements.
- Useful for screen-reader users.

```html
<form>
  <label for="fname">First name:</label><br>
  <input type="text" id="fname" name="fname"><br>
  <label for="lname">Last name:</label><br>
  <input type="text" id="lname" name="lname">
</form>
```

#### Radio Buttons and Checkboxes

- `<input type="radio">` defines a radio button.
- `<input type="checkbox">` defines a checkbox.

#### Submit Button

```html
<form action="/action_page.php">
  <label for="fname">First name:</label><br>
  <input type="text" id="fname" name="fname" value="John"><br>
  <label for="lname">Last name:</label><br>
  <input type="text" id="lname" name="lname" value="Doe"><br><br>
  <input type="submit" value="Submit">
</form>
```

#### Form Attributes

- `action`: Defines the action to be performed when the form is submitted.
- `target`: Specifies where to display the response after submitting the form.
- `method`: Specifies the HTTP method for submitting form data.
- `autocomplete`: Specifies whether a form should have autocomplete on or off.

#### Select Element

- Defines a drop-down list.
- `<option>` defines selectable options.
- Use `size` attribute to specify visible values.
- Use `multiple` attribute to allow multiple selections.

```html
<label for="cars">Choose a car:</label>
<select id="cars" name="cars" size="4" multiple>
  <option value="volvo">Volvo</option>
  <option value="saab">Saab</option>
  <option value="fiat">Fiat</option>
  <option value="audi">Audi</option>
</select>
```

#### Textarea

- Defines a multi-line input field.

```html
<textarea name="message" rows="10" cols="30">
The cat was playing in the garden.
</textarea>
```

#### Fieldset and Legend

- `<fieldset>` groups related data in a form.
- `<legend>` defines a caption for the `<fieldset>`.

```html
<form action="/action_page.php">
  <fieldset>
    <legend>Personalia:</legend>
    <label for="fname">First name:</label><br>
    <input type="text" id="fname" name="fname" value="John"><br>
    <label for="lname">Last name:</label><br>
    <input type="text" id="lname" name="lname" value="Doe"><br><br>
    <input type="submit" value="Submit">
  </fieldset>
</form>
```

### 1.2 Lists

#### Unordered HTML List

- Starts with `<ul>` tag.
- Each list item starts with `<li>` tag.
- Can style with `list-style-type` CSS property.

```html
<ul style="list-style-type:none;">
  <li>Coffee</li>
  <li>Tea</li>
  <li>Milk</li>
</ul>
```

#### Ordered HTML List

- Starts with `<ol>` tag.
- Each list item starts with `<li>` tag.
- Can use `type` attribute to define marker type.

```html
<ol type="1">
  <li>Coffee</li>
  <li>Tea</li>
  <li>Milk</li>
</ol>
```

### 1.3 Tables

- Defined by `<table>` tag.
- Each table cell is defined by `<td>` and `</td>` tags.
- `<th>` is used for table headers.
- Use `colspan` to make a cell span multiple columns.
- Use `rowspan` to make a cell span multiple rows.

```html
<table>
  <tr>
    <th>Name</th>
    <td>Jill</td>
  </tr>
  <tr>
    <th rowspan="2">Phone</th>
    <td>555-1234</td>
  </tr>
  <tr>
    <td>555-8745</td>
  </tr>
</table>
```

## 2. Accessibility

- Use semantic HTML elements.
- Provide text alternatives for non-text content.
- Ensure keyboard navigation.
- Use ARIA (Accessible Rich Internet Applications) attributes wisely.
- Label form elements properly.
- Maintain logical focus order.
- Test with assistive technologies.

## 3. SEO (Search Engine Optimization)

### 3.1 Title Tags

```html
<title>Learn HTML - Basics, Elements, and SEO</title>
```

### 3.2 Meta Descriptions

```html
<meta name="description" content="Learn the basics of HTML, including elements, attributes, and best practices for SEO.">
```

### 3.3 Headings

Use `<h1>` to `<h6>` tags to define headings and subheadings.

### 3.4 Alt Attributes for Images

```html
<img src="html-basics.png" alt="HTML Basics Tutorial">
```

### 3.5 URL Structure

Use clean, readable URLs with keywords related to page content.

### 3.6 Structured Data and Schema Markup

Use JSON-LD for structured data.

## 4. HTML APIs

### 4.1 Geolocation

```javascript
function getLocation() {
  if (navigator.geolocation) {
    navigator.geolocation.getCurrentPosition(showPosition);
  } else {
    myElement.innerHTML = "Geolocation is not supported by this browser.";
  }
}
```

### 4.2 Web Storage API

```javascript
// Store data
localStorage.setItem("username", "JohnDoe");
// Retrieve data
var username = localStorage.getItem("username");
console.log(username);
```

### 4.3 Fetch API

```javascript
fetch('https://api.example.com/data')
  .then(response => response.json())
  .then(data => console.log(data))
  .catch(error => console.error('Error:', error));
```

### 4.4 Notification API

```javascript
Notification.requestPermission().then(function(result) {
  if (result === 'granted') {
    var notification = new Notification('Hello, World!');
  }
});
```

### 4.5 Drag and Drop API

```html
<div id="draggable" draggable="true">Drag me!</div>
<div id="dropzone">Drop here</div>
<script>
  var draggable = document.getElementById('draggable');
  var dropzone = document.getElementById('dropzone');
  draggable.ondragstart = function(event) {
    event.dataTransfer.setData('text', 'Dragged element');
  };
  dropzone.ondragover = function(event) {
    event.preventDefault();
  };
  dropzone.ondrop = function(event) {
    event.preventDefault();
    var data = event.dataTransfer.getData('text');
    dropzone.textContent = data;
  };
</script>
```

## 5. HTML Comments

- HTML comments are not displayed in the browser.
- Syntax: `<!-- Comment goes here -->`
- Can be used to hide content temporarily.

```html
<!-- <p>This is another paragraph </p> -->
```

- Can hide part of a paragraph:

```html
<p>This <!-- great text --> is a paragraph.</p>
```
```
