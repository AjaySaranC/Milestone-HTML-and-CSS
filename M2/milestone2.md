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



#### 1.5 DOM Events
- **The onload and onunload Events:**
  - Triggered when the user enters or leaves the page.
  - Can be used to check visitor's browser type and version:
    ```html
    <body onload="checkCookies()">
    ```

- **Onchange Event:**
  - Often used for input field validation:
    ```html
    <input type="text" id="fname" onchange="upperCase()">
    ```

- **EventListener:**
  - Attaches an event handler without overwriting existing ones:
    ```javascript
    document.getElementById("myBtn").addEventListener("click", displayDate);

    function displayDate() {
      document.getElementById("demo").innerHTML = Date();
    }
    ```
  - Can be removed using `removeEventListener()`.

- **Multiple Event Handlers:**
  ```javascript
  var x = document.getElementById("myBtn");
  x.addEventListener("click", myFunction);
  x.addEventListener("click", someOtherFunction);
  ```

- **Event Handler on Window Object:**
  ```javascript
  window.addEventListener("resize", function(){
    document.getElementById("demo").innerHTML = Math.random();
  });
  ```

- **Passing Parameters:**
  ```javascript
  let p1 = 5;
  let p2 = 7;
  document.getElementById("myBtn").addEventListener("click", function() {
    myFunction(p1, p2);
  });
  ```

- **Event Bubbling and Capturing:**
  - Bubbling: Inner to outer
  - Capturing: Outer to inner
  - Default is bubbling (false), set to true for capturing:
    ```javascript
    document.getElementById("myDiv").addEventListener("click", function() {
      alert("You clicked the orange element!");
    }, true); // Use capturing
    ```

#### 1.6 DOM Nodes
- Everything in an HTML document is a node.
- Nodes have hierarchical relationships.
- **Accessing Node Values:**
  ```javascript
  myTitle = document.getElementById("demo").innerHTML;
  // or
  myTitle = document.getElementById("demo").firstChild.nodeValue;
  ```

- **Common Node Properties:**
  - `document.body`: The body of the document
  - `document.documentElement`: The full document
  - `nodeName`: Specifies the name of a node

- **Creating and Appending Nodes:**
  ```javascript
  const para = document.createElement("p");
  const node = document.createTextNode("This is new.");
  para.appendChild(node);

  const element = document.getElementById("div1");
  element.appendChild(para);
  ```

- **Node Manipulation Methods:**
  - `appendChild()`: Adds at end
  - `insertBefore()`: Adds at beginning
  - `remove()`: Removes a node
  - `replaceChild()`: Replaces a node

- **HTML Collections:**
  ```javascript
  const myCollection = document.getElementsByTagName("p");
  document.getElementById("demo").innerHTML = "The innerHTML of the second paragraph is: " + myCollection[1].innerHTML;
  ```
```
