## Milestone 5

### 1.Selectors and Combinators:

# 1.1 Selectors:
Selectors are used in finding the html elements.Can be divided into
- Simple selector
- Combinators
- Pseudo class selectors
- Pseudo elements selector

Simple Selectors:
 based on name ,id, classname.
 - id:
 ```css
  #para1 {
    text-align: center;
    color: red;
  }
```

-element:
 ```css
  p {
    text-align: center;
    color: red;
  }
```

- class selector:
  
 ```css
  .center {
    text-align: center;
    color: red;
  }
```
We can also call the element of specific class.
 ```css
  p.center {
    text-align: center;
    color: red;
  }
```
- Universal Selector:
  The universal selector (*) selects all HTML elements on the page.
  ```css
      * {
        text-align: center;
        color: blue;
      }


# 1.2 Combinators:
Explains the relationship between the selectors.Includes
- descendant selector (space):
   matches all elements descendants of a specified element .
    ```css
        div p {
              background-color: yellow;
         }

  ```

- child selector (>):
  The child selector selects all elements that are the children of a specified element.
   ```css
  div > p {
    background-color: yellow;
  }
  ```

- adjacent sibling selector (+):
  include the immediate element below to it (Siblins)
   ```css
  div + p {
    background-color: yellow;
  }


- general sibling selector (~):
 all elements that are next siblings of a specified element.
 ```css
  div ~ p {
  background-color: yellow;
}
```

## 2.Pseudo Classes and Elements:
Used in specifying special states
- visited
- hover
- focus

```css
  selector:pseudo-class {
    property: value;
  }
```
Anchor Pseudo class:

```css

<html>
<head>
<style>
a:link {
  color: red;
}


a:visited {
  color: green;
}

a:hover {
  color: hotpink;
}

a:active {
  color: blue;
}
</style>
</head>
<body>

<p><b><a href="" target="_blank">This is a link</a></b></p>

</body>
</html>

```

The :first-child Pseudo class:
Matches the firstchild of another element
ex:
```css
  p:first-child {
    color: blue;
  }
```
the above snippet targets all the <p> tag first element inside an element.





