## Milestone 2

### 1. HTML

- HTML is the standard language used to create and structure content on the World Wide Web.
- **Structure Components:**
  - `<!DOCTYPE html>`: Defines the document type and HTML version.
  - `<html>`: Root element that contains all other elements.
  - `<head>`: Contains meta-information.
  - `<meta charset="UTF-8">`: Specifies the character encoding for the document.

### 2. DOM (Document Object Model)

- The DOM defines a standard for accessing documents.
- Stands for Document Object Model. The browser creates a DOM when the webpage is loaded.
- **Finding HTML Elements with JavaScript:**
  - Finding by ID:
     ```javascript
    var element = document.getElementById('myDiv');
     ```
  - Finding by Tag Name:
    ```javascript
    var elements = document.getElementsByTagName('p');
    ```
  - Finding by Class Name:
    ```javascript
    var elements = document.getElementsByClassName('myClass');
    ```
  - Using CSS Selector:
     ```javascript
     var elements = document.querySelectorAll('.myClass');
    ```
  - HTML Object Collections:
    ```javascript
    var forms = document.forms;
    ```

#### 1.1 DOM Methods

- Property is a value (changing elements) and method (actions).
- `innerHTML`: Useful for getting and setting content to an HTML element.

#### 1.2 DOM Document

- **Finding HTML Elements:**
  ```javascript
  document.getElementById()
  ```, etc.
- **Changing HTML Elements:**
   ```javascript
  element.innerHTML = newHTMLContent;
   ```
  ```javascript
  element.attribute = newValue;
  ```
- **Adding and Deleting Elements:**
  ```javascript
  document.createElement(element);`
  paragraph.parentNode.removeChild(paragraph);
  ```
- **Replacing an Element:**
  - Example: 
    ```javascript
    var oldParagraph = document.getElementById('oldParagraph');
    oldParagraph.parentNode.replaceChild(newParagraph, oldParagraph);
    ```
- **Attribute Change:**
  ```javascript
  document.getElementById("myImage").src = "landscape.jpg";
  ```
- Using `document.write()` after the document has loaded will overwrite the document, so it is not a good practice.

#### 1.3 DOM Forms

- **Retrieving Data from Form:**
  - Using `document.forms["myForm"]["fname"].value;` or `document.forms.myForm`.
- The browser automatically validates empty fields.
- **Data Validation:**
  - Purpose: Ensures required fields are filled with valid data.
  - Server and Client-Side Validation.
  - **Validation with HTML Input Attributes:** `disabled`, `max`, `min`, `pattern`, `required`, `type`.

#### 1.4 DOM CSS and Others

- **Changing a CSS Property:** `
  ```javascript
  document.getElementById("p2").style.color = "blue";
  ```
- CSS changes triggered by events, e.g., `onclick="document.getElementById('id1').style.color = 'red'"`.
- **HTML Events Using DOM:** 
  ```html
  <script>
  document.getElementById("myBtn").onclick = displayDate;
  </script>
