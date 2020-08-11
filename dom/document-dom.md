# Document DOM

## Properties

### activeElement

The activeElement property returns the currently focused element in the document.

Note: This property is read-only.

Tip: To give focus to an element, use the `element.focus()` method.

Tip: To find out if the document has focus, use the `document.hasFocus()` method.

```javascript
var x = document.activeElement.tagName;
```

### body

The body property sets or returns the document's body.

On return, this property returns the `<body>` element of the current document.

On set, this property overwrites all child elements inside the existing `<body>` element, and replaces it with the new, specified content.

Tip: The difference between this property and the `document.documentElement` property, is that the `document.body` element returns the `<body>` element, while the `document.documentElement` returns the `<html>` element.

```javascript
document.body.style.backgroundColor = "yellow";
```

## Methods

### getElementById\(\)

The `getElementById()` method returns the element that has the ID attribute with the specified value.

This method is one of the most common methods in the HTML DOM, and is used almost every time you want to manipulate, or get info from, an element on your document.

Returns `null` if no elements with the specified ID exists.

An ID should be unique within a page. However, if more than one element with the specified ID exists, the `getElementById()` method returns the first element in the source code.

```javascript
var x = document.getElementById("demo");   // Get the element with id="demo"
x.style.color = "red";                     // Change the color of the element
```

### getElementsByClassName\(\)

The `getElementsByClassName()` method returns a collection of all elements in the document with the specified class name, as an **HTMLCollection** object.

The HTMLCollection object represents a collection of **nodes**. The nodes can be accessed by index numbers. The index starts at 0.

Tip: You can use the `length` property of the HTMLCollection object to determine the number of elements with a specified class name, then you can loop through all elements and extract the info you want.

```javascript
var x = document.getElementsByClassName("example color");
var y = document.getElementsByClassName("example").length;
var i;
for (i = 0; i < x.length; i++) {
  x[i].style.backgroundColor = "red";
}
```

### getElementsByTagName\(\)

The `getElementsByTagName()` method returns a collection of all elements in the document with the specified tag name, as an **HTMLCollection** object.

The **HTMLCollection** object represents a collection of nodes. The nodes can be accessed by index numbers. The index starts at 0.

Tip: The parametervalue `"*"` returns all elements in the document.

Tip: You can use the `length` property of the HTMLCollection object to determine the number of elements with the specified tag name, then you can loop through all elements and extract the info you want.

```javascript
var x = document.getElementsByTagName("LI");
var x = document.getElementsByTagName("LI").length;
document.getElementsByTagName("P")[0].innerHTML = "Hello World!";
```

### querySelector\(\)

The `querySelector()` method returns the first element that matches a specified CSS selector\(s\) in the document.

Note: The `querySelector()` method only returns the first element that matches the specified selectors. To return all the matches, use the `querySelectorAll()` method instead.

If the selector matches an ID in document that is used several times \(Note that an "id" should be unique within a page and should not be used more than once\), it returns the first matching element.

```javascript
// Get the first <p> element in the document:
document.querySelector("p");
// Get the first <p> element in the document with class="example":
document.querySelector("p.example");
// Change the text of an element with id="demo":
document.querySelector("#demo").innerHTML = "Hello World!";
// Get the first <p> element in the document where the parent is a <div> element.
document.querySelector("div > p");
// Get the first <a> element in the document that has a "target" attribute:
document.querySelector("a[target]");
```

### querySelectorAll\(\)

The `querySelectorAll()` method returns all elements in the document that matches a specified CSS selector\(s\), as a static NodeList object.

The **NodeList** object represents a collection of **nodes**. The nodes can be accessed by index numbers. The index starts at 0.

Tip: You can use the `length` property of the NodeList object to determine the number of elements that matches the specified selector, then you can loop through all elements and extract the info you want.

```javascript
var x = document.querySelectorAll(".example");
```

### addEventListener\(\)

The `document.addEventListener()` method attaches an event handler to the document.

Tip: Use the `document.removeEventListener()` method to remove an event handler that has been attached with the `addEventListener() method`.

Tip: Use the `element.addEventListener()` method to attach an event handler to a specified element.

```javascript
document.addEventListener("click", function(){
  document.getElementById("demo").innerHTML = "Hello World";
});
```

### removeEventListener\(\)

The `document.removeEventListener()` method removes an event handler that has been attached with the `document.addEventListener()` method.

Note: To remove event handlers, the function specified with the `addEventListener()` method must be an external, "named" function, like in the example above \(`myFunction`\).

Anonymous functions, like "`document.removeEventListener("event", function(){ myScript });`" will not work.

Tip: Use the `element.addEventListener()` and `element.removeEventListener()` methods to add/remove event handlers to/from a specified element.

```javascript
document.removeEventListener("mousemove", myFunction);
```

### creatElement\(\)

The `createElement()` method creates an Element Node with the specified name.

Tip: After the element is created, use the `element.appendChild()` or `element.insertBefore()` method to insert it to the document.

```javascript
var btn = document.createElement("BUTTON");   // Create a <button> element
btn.innerHTML = "CLICK ME";                   // Insert text
document.body.appendChild(btn);               // Append <button> to <body>
```

### createTextNode\(\)

HTML elements often consists of both an element node and a text node.

The `createTextNode()` method creates a Text Node with the specified text.

Tip: Use the `createElement()` method to create an Element Node with the specified name.

Tip: After the Text Node is created, use the `element.appendChild()` or `element.insertBefore()` method to append it to an element.

```javascript
var h = document.createElement("H1")                // Create a <h1> element
var t = document.createTextNode("Hello World");     // Create a text node
h.appendChild(t);                                   // Append the text to <h1>
```

### hasFocus\(\)

The `hasFocus()` method returns a Boolean value indicating whether the document \(or any element inside the document\) has focus.

```javascript
var x = document.getElementById("demo");
if (document.hasFocus()) {
  x.innerHTML = "The document has focus.";
} else {
  x.innerHTML = "The document DOES NOT have focus.";
}
```

