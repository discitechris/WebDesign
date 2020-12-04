# Reference List

## **Boiler-Plate**

```css
, :before, *:after { 
-webkit-box-sizing: border-box;
-moz-box-sizing: border-box; 
 box-sizing: border-box; 
 }
```

## Basic selectors

### [Universal selector](https://developer.mozilla.org/en-US/docs/Web/CSS/Universal_selectors)

The CSS universal selector \(\*\) matches elements of any type In other words, it selects all elements. Optionally, it may be restricted to a specific namespace or to all namespaces.

* **Syntax:** `*` `ns|*` `*|*`
* **Example:** `*` will match all the elements of the document.

```css
/* Selects all elements */
* {
  color: green;
}
```

### [Type selectors](https://developer.mozilla.org/en-US/docs/Web/CSS/Type_selectors)

The CSS type selector matches elements by node name. In other words, it selects all elements of the given type within a document.

* **Syntax:** `elementname`
* **Example:** `input` will match any `<input>` element, 

```css
span {
  background-color: skyblue;
}
```

### [Class selectors](https://developer.mozilla.org/en-US/docs/Web/CSS/Class_selectors)

The CSS class selector matches elements based on the contents of their class attribute.

* **Syntax:** `.classname`
* **Example:** `.index` will match any element that has a class of `"index"`.

```markup
<p class="fancy">This paragraph has red text and "fancy" styling.</p>
```

```css
.fancy {
  font-weight: bold;
  text-shadow: 4px 4px 3px #77f;
}
```

### [ID selectors](https://developer.mozilla.org/en-US/docs/Web/CSS/ID_selectors)

The CSS ID selector matches an element based on the value of its `id` attribute. In order for the element to be selected, its `id` attribute must match exactly the value given in the selector.

* **Syntax:** `#idname`
* **Example:** `#toc` will match the element that has the ID `"toc"`.

```markup
<div id="identified">This div has a special ID on it!</div>
```

```css
#identified {
  background-color: skyblue;
}
```

### [Attribute selectors](https://developer.mozilla.org/en-US/docs/Web/CSS/Attribute_selectors)

The CSS attribute selector matches elements based on the presence or value of a given attribute. Selects all elements that have the given attribute.

* **Syntax:** `[attr]` `[attr=value]` `[attr~=value]` `[attr|=value]` `[attr^=value]` `[attr$=value]` `[attr*=value]`
* **Example:** `[autoplay]` will match all elements that have the `autoplay` attribute set \(to any value\).

```css
/* <a> elements with a title attribute */
a[title] {
  color: purple;
}
```

## Grouping selectors

### [Selector list](https://developer.mozilla.org/en-US/docs/Web/CSS/Selector_list)

The CSS selector list \(`,`\) selects all the matching nodes. To reduce the size of style sheets, one can group selectors in comma-separated lists.

* **Syntax:** `A , B`
* **Example:** `div, span` will match both `<span>` and `<div>` elements.

```css
h1, h2, h3, h4, h5, h6 { font-family: helvetica; }

#main,
.content,
article {
  font-size: 1.1em;
}
```

## Combinators

### [Descendant combinator](https://developer.mozilla.org/en-US/docs/Web/CSS/Descendant_combinator)

The ``` (space) combinator selects nodes that are descendants of the first element. The descendant combinator — typically represented by a single space (`` \`\) character — combines two selectors such that elements matched by the second selector are selected if they have an ancestor \(parent, parent's parent, parent's parent's parent, etc\) element matching the first selector. Selectors that utilize a descendant combinator are called descendant selectors.

* **Syntax:** `A B`
* **Example:** `div span` will match all `<span>` elements that are inside a `<div>` element.

```css
li li {
  list-style-type: circle;
}
```

### [Child combinator](https://developer.mozilla.org/en-US/docs/Web/CSS/Child_combinator)

The child combinator \(`>`\) is placed between two CSS selectors. It matches only those elements matched by the second selector that are the direct children of elements matched by the first.

* **Syntax:** `A > B`
* **Example:** `ul > li` will match all `<li>` elements that are nested directly inside a `<ul>` element.

```css
div > span {
  background-color: DodgerBlue;
}
```

### [General sibling combinator](https://developer.mozilla.org/en-US/docs/Web/CSS/General_sibling_combinator)

The general sibling combinator \(`~`\) separates two selectors and matches the second element only if it follows the first element \(though not necessarily immediately\), and both are children of the same parent element.

* **Syntax:** `A ~ B`
* **Example:** `p ~ span` will match all `<span>` elements that follow a `<p>`, immediately or not.

```css
p ~ span {
  color: red;
}
```

### [Adjacent sibling combinator](https://developer.mozilla.org/en-US/docs/Web/CSS/Adjacent_sibling_combinator)

The adjacent sibling combinator \(`+`\) separates two selectors and matches the second element only if it _immediately_ follows the first element, and both are children of the same parent element.

* **Syntax:** `A + B`
* **Example:** `h2 + p` will match all `<p>` elements that directly follow an `<h2>`.

```css
li:first-of-type + li {
  color: red;
}
```

## Pseudo

### [Pseudo classes](https://developer.mozilla.org/en-US/docs/Web/CSS/Pseudo-classes)

The `:` pseudo allow the selection of elements based on state information that is not contained in the document tree. A CSS pseudo-class is a keyword added to a selector that specifies a special state of the selected element\(s\). For example, `:hover` can be used to change a button's color when the user's pointer hovers over it.

**Example:** `a:visited` will match all `<a>` elements that have been visited by the user.

```css
/* Any button over which the user's pointer is hovering */
button:hover {
  color: blue;
}
```

### [Pseudo elements](https://developer.mozilla.org/en-US/docs/Web/CSS/Pseudo-elements)

A CSS pseudo-element is a keyword added to a selector that lets you style a specific part of the selected element\(s\). For example, `::first-line` can be used to change the font of the first line of a paragraph. The `::` pseudo represent entities that are not included in HTML.

**Example:** `p::first-line` will match the first line of all `<p>` elements.

```css
/* The first line of every <p> element. */
p::first-line {
  color: blue;
  text-transform: uppercase;
}
```

