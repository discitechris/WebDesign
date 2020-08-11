# Document Object Model

In the DOM, all HTML elements are defined as objects.

The programming interface is the properties and methods of each object.

A **`property`** is a _value_ that you can get or set \(like changing the content of an HTML element\).

A **`method`** is an _action_ you can do \(like add or deleting an HTML element\).

```markup
<html>
<body>

<p id="demo"></p>

<script>
document.getElementById("demo").innerHTML = "Hello World!";
</script>

</body>
</html>
```

In the example above, **`getElementById`** is a **method**, while **`innerHTML`** is a **property**.

## Methods

A **`method`** is an _action_ you can do \(like add or deleting an HTML element\).

### getElementById

he most common way to access an HTML element is to use the **`id`** of the element. and **`id`** are unique in an html.

```javascript
document.getElementById(id)
var myElement = document.getElementById("intro");
```

If the element is found, the method will return the element as an object \(in myElement\).

If the element is not found, myElement will contain **`null`**.

### getElementsByTagName

```javascript
document.getElementsByTagName(name)
var x = document.getElementsByTagName("p");
// This example finds the element with id="main", and then finds all <p> elements inside "main":
var x = document.getElementById("main");
var y = x.getElementsByTagName("p");
```

### getElementsByClassName

If you want to find all HTML elements with the same class name

returns a list of all elements

```javascript
document.getElementsByClassName(name)
var x = document.getElementsByClassName("intro");
```

### querySelectorAll

If you want to find **all** HTML elements that match a specified CSS selector \(**`id`**, **`class names`**, **`types`**, **`attributes`**, values of **`attributes`**, etc\), use the **`querySelectorAll()`** method.

```javascript
// returns a list of all <p> elements with class="intro".
var x = document.querySelectorAll("p.intro");
```

### setAttribute

Change the attribute value of an HTML element

```javascript
element.setAttribute(attribute, value)
```

### createElement

Create an HTML element

```javascript
document.createElement(element)
```

### removeChild

Remove an HTML element

```javascript
document.removeChild(element)
```

### appendChild

Add an HTML element

```javascript
document.appendChild(element)
```

### replaceChild

Replace an HTML element

```javascript
document.replaceChild(new, old)
```

### write

Write into the HTML output stream

```javascript
document.write(text)
document.write(Date());
```

Note: Never use **`document.write()`** after the document is loaded. It will overwrite the document.

## Properties

### innerHTML

The easiest way to get the content of an element is by using the **`innerHTML`** property.

Note: The innerHTML property can be used to get or change any HTML element, including `<html>` and `<body>`.

### attribute

Change the attribute value of an HTML element

```javascript
element.attribute = new value
document.getElementById("myImage").src = "landscape.jpg";
```

### style.property

Change the style of an HTML element

```javascript
element.style.property = new style
document.getElementById("p2").style.color = "blue";
```

## Events Handlers

Adding event handler code to an onclick event

```javascript
document.getElementById(id).onclick = function(){code}
```

```markup
<!DOCTYPE html>
<html>
<body>

<h1 id="id1">My Heading 1</h1>

<button type="button"
onclick="document.getElementById('id1').style.color = 'red'">
Click Me!</button>

</body>
</html>
```

