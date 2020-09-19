# Display

Every element on a web page is a rectangular box. The display property in CSS determines just how that rectangular box behaves. There are only a handful of values that are commonly used:

```css
div {
  display: inline;        /* Default of all elements, unless UA stylesheet overrides */
  display: inline-block;  /* Characteristics of block, but sits on a line */
  display: block;         /* UA stylesheet makes things like <div> and <section> block */
  display: run-in;        /* Not particularly well supported or common */
  display: none;          /* Hide */
}
```

Values:

### **`inline`**

* The default value
* Think of elements like `<span>`, `<em>`, or `<b>` and how wrapping text in those elements within a string of text doesn’t break the flow of the text.
* An inline element will accept margin and padding, but the element still sits inline as you might expect. Margin and padding will only push other elements horizontally away, not vertically.
* An inline element will not accept **`height`** and **`width`**. It will just ignore it.

### **`inline-block`**

* very similar to inline in that it will set inline with the natural flow of text \(on the “baseline”\).
* The difference is that you are able to set a **`width`** and **`height`** which will be respected.

### **`block`**

* A number of elements are set to `block` by the browser UA stylesheet.
* They are usually container elements, like `<div>`, `<section>`, and `<ul>`. Also text “blocks” like `<p>` and `<h1>`.
* Block level elements do not sit inline but break past them.
* By default \(without setting a width\) they take up as much horizontal space as they can.

### **`flex`**

* property is also used for new fangled layout methods like Flexbox.

### **`flow-root`**

* display value creates a new “block formatting context”, but is otherwise like block.
* A new BFC helps with things like clearing floats, removing the need for hacks to do that.

### **`grid`**

* Grid layout will also be initially set by the display property.

  **`none`**

* Entirely removes the element from the page.
* Note that while the element is still in the DOM, it is removed visually and any other conceivable way 
* \(you can’t tab to it or its children, it is ignored by screen readers, etc\).

