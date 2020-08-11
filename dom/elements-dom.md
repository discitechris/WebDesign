# Elements DOM

## Elements

### Create Element

```javascript
let li = document.createElement('li');
```

### Add class

```javascript
li.className = 'collection-item';
```

### Add id

```javascript
li.id = 'new-item';
```

### Add Attribute

```javascript
li.setAttribute = ('title', 'newItem');
```

### Create Text Node and Append

```javascript
li.appendChild(document.createTextNode('Hello World'));
```

### Append `li` as child to `ul`

```javascript
document.querySelector('ul-collection').appendChild(li);
```

### appendChild\(\)

The `appendChild()` method appends a node as the last child of a node.

Tip: If you want to create a new paragraph, with text, remember to create the text as a Text node which you append to the paragraph, then append the paragraph to the document.

Tip: Use the `insertBefore()` method to insert a new child node before a specified, existing, child node.

```javascript
var node = document.createElement("LI");                 // Create a <li> node
var textnode = document.createTextNode("Water");         // Create a text node
node.appendChild(textnode);                              // Append the text to <li>
document.getElementById("myList").appendChild(node);     // Append <li> to <ul> with id="myList"


// Move a list item from one list to another:
var node = document.getElementById("myList2").lastChild;
document.getElementById("myList1").appendChild(node);
```

### Add innerHTML

```javascript
link.innerHTML ='<i class="fa-fa icon"> </i>'
```

## Removing & Replacing Elements

```javascript
// create Element
const newHeading = document.creatElement('h2');
// Adding an Id
newHeading.id = "task-title";
// new text Node
newHeading.appendChild(document.createTextNode('Task List'));
//get the old Heading
const oldHeading = document.getElementById('task-title');
// parent
const cardAction =document.querySelector('.card-Acton');
```

### Replace

```javascript
cardAction.replaceChild(newHeading, oldHeading);
```

## Remove Element

```javascript
const lis = document.querySelectorAll('li');
const list = document.querySelector('ul');
```

### Remove List item

```javascript
lis[0].remove();
```

### Remove child Element

```javascript
list.removeChild(lis[3]);
```

### Add \| Remove Classes

```javascript
const firstLi = document.querySelector('li:first-child');
const link = firstLi.children[0];
link.className;
link.classList;
link.classList[0];
link.classList.add('test');
link.classList.remove('test');
```

### Add \| Remove \| check Attribute

```javascript
link.getAttribute('href');
link.setAttribute('href','http://google.com');
link.setAttribute('href','google');
link.hasAttribute('title');
link.removeAttribute('title');
```

## Reference List

| Element Events | Description |
| :--- | :--- |
| [`addEventListener()`](https://developer.mozilla.org/en-US/docs/Web/API/EventTarget/addEventListener)\`\` | Attaches an event handler to the specified element |
| [`removeEventListener()`](https://developer.mozilla.org/en-US/docs/Web/API/EventTarget/removeEventListener)\`\` | Removes an event handler that has been attached with the `addEventListener()` method |
| [`appendChild()`](https://developer.mozilla.org/en-US/docs/Web/API/Node/appendChild)\`\` | Adds a new child node, to an element, as the last child node |
| \`\`[`attributes`](https://developer.mozilla.org/en-US/docs/Web/API/Element/attributes)\`\` | Returns a NamedNodeMap of an element's attributes |
| [`getAttribute()`](https://developer.mozilla.org/en-US/docs/Web/API/Element/getAttribute)\`\` | Returns the specified attribute value of an element node |
| [`setAttribute()`](https://developer.mozilla.org/en-US/docs/Web/API/Element/setAttribute)\`\` | Sets or changes the specified attribute, to the specified value |
| [`removeAttribute()`](https://developer.mozilla.org/en-US/docs/Web/API/Element/removeAttribute)\`\` | Removes a specified attribute from an element |
| [`hasAttribute()`](https://developer.mozilla.org/en-US/docs/Web/API/Element/hasAttribute)\`\` | Returns true if an element has the specified attribute, otherwise false |
| [`hasAttributes(`\)](https://developer.mozilla.org/en-US/docs/Web/API/Element/hasAttributes) | Returns true if an element has any attributes, otherwise false |
| [`cloneNode()`](https://developer.mozilla.org/en-US/docs/Web/API/Node/cloneNode)\`\` | Clones an element |
| [`parentNode`](https://developer.mozilla.org/en-US/docs/Web/API/Node/parentNode)\`\` | Returns the parent node of an element |
| [`parentElement`](https://developer.mozilla.org/en-US/docs/Web/API/Node/parentElement)\`\` | Returns the parent element node of an element |
| [`childNodes`](https://developer.mozilla.org/en-US/docs/Web/API/Node/childNodes)\`\` | Returns a collection of an element's child nodes \(including text and comment nodes\) |
| [`replaceChild()`](https://developer.mozilla.org/en-US/docs/Web/API/Node/replaceChild)\`\` | Replaces a child node in an element |
| [`removeChild()`](https://developer.mozilla.org/en-US/docs/Web/API/Node/removeChild)\`\` | Removes a child node from an element |
| [`hasChildNodes()`](https://developer.mozilla.org/en-US/docs/Web/API/Node/hasChildNodes)\`\` | Returns true if an element has any child nodes, otherwise false |
| [`children`](https://developer.mozilla.org/en-US/docs/Web/API/ParentNode/children)\`\` | Returns a collection of an element's child element \(excluding text and comment nodes\) |
| [`firstChild`](https://developer.mozilla.org/en-US/docs/Web/API/Node/firstChild)\`\` | Returns the first child node of an element |
| [`firstElementChild`](https://developer.mozilla.org/en-US/docs/Web/API/ParentNode/firstElementChild)\`\` | Returns the first child element of an element |
| [`lastChild`](https://developer.mozilla.org/en-US/docs/Web/API/Node/lastChild)\`\` | Returns the last child node of an element |
| [`lastElementChild`](https://developer.mozilla.org/en-US/docs/Web/API/ParentNode/lastElementChild)\`\` | Returns the last child element of an element |
| [`nextSibling`](https://developer.mozilla.org/en-US/docs/Web/API/Node/nextSibling)\`\` | Returns the next node at the same node tree level |
| [`nextElementSibling`](https://developer.mozilla.org/en-US/docs/Web/API/NonDocumentTypeChildNode/nextElementSibling)\`\` | Returns the next element at the same node tree level |
| [`previousSibling`](https://developer.mozilla.org/en-US/docs/Web/API/Node/previousSibling)\`\` | Returns the previous node at the same node tree level |
| [`previousElementSibling`](https://developer.mozilla.org/en-US/docs/Web/API/NonDocumentTypeChildNode/previousElementSibling)\`\` | Returns the previous element at the same node tree level |
| [`id`](https://developer.mozilla.org/en-US/docs/Web/API/Element/id)\`\` | Sets or returns the value of the id attribute of an element |
| [`className`](https://developer.mozilla.org/en-US/docs/Web/API/Element/className)\`\` | Sets or returns the value of the class attribute of an element |
| [`classList`](https://developer.mozilla.org/en-US/docs/Web/API/Element/classList)\`\` | Returns the class name\(s\) of an element |
| [`title`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLElement/title)\`\` | Sets or returns the value of the title attribute of an element |
| [`style`](https://developer.mozilla.org/en-US/docs/Web/API/ElementCSSInlineStyle/style)\`\` | Sets or returns the value of the style attribute of an element |
| [`contains()`](https://developer.mozilla.org/en-US/docs/Web/API/Node/contains)\`\` | Returns true if a node is a descendant of a node, otherwise false |
| [`click()`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLElement/click)\`\` | Simulates a mouse-click on an element |
| [`focus(`\)](https://developer.mozilla.org/en-US/docs/Web/API/Element/focus_event) | Gives focus to an element |
| [`blur()`](https://developer.mozilla.org/en-US/docs/Web/API/Element/blur_event)\`\` | Removes focus from an element |
| [`dir`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLElement/dir)\`\` | Sets or returns the value of the dir attribute of an element |
| [`getBoundingClientRect()`](https://developer.mozilla.org/en-US/docs/Web/API/Element/getBoundingClientRect)\`\` | Returns the size of an element and its position relative to the viewport |
| [`getElementsByClassName()`](https://developer.mozilla.org/en-US/docs/Web/API/Element/getElementsByClassName)\`\` | Returns a collection of all child elements with the specified class name |
| [`getElementsByTagName()`](https://developer.mozilla.org/en-US/docs/Web/API/Element/getElementsByTagName)\`\` | Returns a collection of all child elements with the specified tag name |
| [`querySelector()`](https://developer.mozilla.org/en-US/docs/Web/API/Element/querySelector)\`\` | Returns the first child element that matches a specified CSS selector\(s\) of an element |
| [`querySelectorAll()`](https://developer.mozilla.org/en-US/docs/Web/API/Element/querySelectorAll)\`\` | Returns all child elements that matches a specified CSS selector\(s\) of an element |
| [`textContent`](https://developer.mozilla.org/en-US/docs/Web/API/Node/textContent)\`\` | Sets or returns the textual content of a node and its descendants |
| [`innerHTML`](https://developer.mozilla.org/en-US/docs/Web/API/Element/innerHTML)\`\` | Sets or returns the content of an element |
| [`innerText`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLElement/innerText)\`\` | Sets or returns the text content of a node and its descendants |
| [`insertBefore()`](https://developer.mozilla.org/en-US/docs/Web/API/Node/insertBefore)\`\` | "Inserts a new child node before a specified, existing, child node" |
| [`isEqualNode()`](https://developer.mozilla.org/en-US/docs/Web/API/Node/isEqualNode)\`\` | Checks if two elements are equal |
| [`isSameNode()`](https://developer.mozilla.org/en-US/docs/Web/API/Node/isSameNode)\`\` | Checks if two elements are the same node |
| [`remove()`](https://developer.mozilla.org/en-US/docs/Web/API/ChildNode/remove)\`\` | Removes the element from the DOM |
| [`setAttributeNode()`](https://developer.mozilla.org/en-US/docs/Web/API/Element/setAttributeNode)\`\` | Sets or changes the specified attribute node |
| [`removeAttributeNode()`](https://developer.mozilla.org/en-US/docs/Web/API/Element/removeAttributeNode)\`\` | Removes a specified attribute node, and returns the removed node |
| [`scrollIntoView()`](https://developer.mozilla.org/en-US/docs/Web/API/Element/scrollIntoView)\`\` | Scrolls the specified element into the visible area of the browser window |
| [`toString()`](https://developer.mozilla.org/en-US/docs/Web/API/Location/toString)\`\` | Converts an element to a string |

