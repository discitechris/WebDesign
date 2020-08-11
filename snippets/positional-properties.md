# Positional Properties

## float

Used for positioning and layout on web pages.

Values:

* none
* left
* right
* inherit

Note: An element that is floated is automatically **`display: block;`**

## width / height

the width/ height of the element’s content area. This “content” area is the portion inside the **`padding`**, **`border`**, and **`margin`** of an element \(the box model\).

### max/min-height/width

property in CSS is used to set the maximum height of a specified element. Authors may use any of the length values as long as they are a positive value. max-height overrides height, but min-height always overrides max-height.

Values:

* Length values \(e.g. px, em, rem, ex, etc\)
* **`min-content`** value is the smallest measure that would fit around its content if all **soft wrap opportunities** within the box were taken.
* **`max-content`** property refers to the narrowest measure a box could take while fitting around its content – if no soft wrap opportunities within the element were taken.
* **`fit-content`** value is roughly equivalent to margin-left: auto and margin-right: auto in behaviour, except it works for unknown widths.

## margin

defines the outermost portion of the box model, creating space around an element, outside of any defined borders.

Values:

* Length values \(e.g. px, em, rem, ex, etc\) 
* percentages
* auto
* negative values \(with above values\)

```css
.box {
margin: <margin-top> || <margin-right> || <margin-bottom> || <margin-left>
margin-bottom: 20px;
margin-top: 20px;
}
```

## padding

defines the innermost portion of the box model, creating space around an element’s content, inside of any defined margins and/or borders.

```css
.box {
padding: <padding-top> || <padding-right> || <padding-bottom> || <padding-left>
padding-right: 20px;
padding-bottom: 20px;
}
```

Values:

* Length values \(e.g. px, em, rem, ex, etc\) 
* percentages

## display

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

## clear

property is directly related to floats. If the element can fit horizontally in the space next to another element which is floated, it will. Unless you apply clear to that element in the same direction as the float. Then the element will move down below the floated element.

A common way to clear floats is to apply a pseudo element to a container element which clears the float.

for more info: [clear](https://css-tricks.com/almanac/properties/c/clear/)

## border

shorthand syntax, accepts multiple values for drawing a line around the element it is applied to.

```css
border:  <border-width> || <border-style> || <color>
border-bottom: <border-width> || <border-style> || <color>
border-left : <border-width> || <border-style> || <color>
```

Values for border-width:

* **`<length>`** : A numeric value measured in px, em, rem, vh and vw units.
* **`thin`** : The equivalent of 1px
* **`medium`** : The equivalent of 3px
* **`thick`** : The equivalent of 5px

Values for border-style:

* **`solid`** : A solid, continuous line.
* **`none` \(default\)** : No line is drawn.
* **`hidden`** : A line is drawn, but not visible. this can be handy for adding a little extra width to an element without displaying a border.
* **`dashed`** : A line that consists of dashes.
* **`dotted`** : A line that consists of dots.
* **`double`** : Two lines are drawn around the element.
* **`groove`** : Adds a bevel based on the color value in a way that makes the element appear pressed into the document.
* **`ridge`** : Similar to groove, but reverses the color values in a way that makes the element appear raised.
* **`inset`** : Adds a split tone to the line that makes the element appear slightly depressed.
* **`outset`** : Similar to inset, but reverses the colors in a way that makes the element appear slightly raised.

## overflow

controls what happens to content that breaks outside of its bounds: imagine a div in which you’ve explicitly set to be 200px wide, but contains an image that is 300px wide. That image will stick out of the div and be visible by default. Whereas if you set the overflow value to hidden, the image will cut off at 200px.

```css
div {
  overflow:  visible | hidden | scroll | auto | inherit
}
.box {
  overflow-y: hidden;
  overflow-x: scroll;
}
```

Values:

* **`visible`** : content is not clipped when it proceeds outside its box. This is the **default** value of the property
* **`hidden`** : overflowing content will be hidden.
* **`scroll`** : similar to hidden except users will be able to scroll through the hidden content
* **`auto`** : if the content proceeds outside its box then that content will be hidden whilst a scroll bar should be visible for users to read the rest of the content.
* **`initial`** : uses the default value which is visible
* **`inherit`** : sets the overflow to the value of its parent element.

## position

can help you manipulate the location of an element

Relative to its original position the element above will now be nudged down from the top by 20px.

```css
.element {
  position: relative;
  top: 20px;
}
```

Values:

* **`static`** : every element has a static position by **default**, so the element will stick to the normal page flow.
  * if there is a **`left`** / **`right`** / **`top`** / **`bottom`** / **`z-index`** set then there will be no effect on that element.
* **`relative`** : an element’s original position remains in the flow of the document, just like the static value. But now **`left`** / **`right`** / **`top`** / **`bottom`** / **`z-index`** will work.
  * The positional properties “nudge” the element from the original position in that direction.
* **`absolute`** : the element is removed from the flow of the document and other elements will behave as if it’s not even there whilst all the other positional properties will work on it.
* **`fixed`** : the element is removed from the flow of the document like absolutely positioned elements.
  * In fact they behave almost the same, only fixed positioned elements are always relative to the document, not any particular parent, and are unaffected by scrolling.
* **`sticky`** **\(experimental\)**: the element is treated like a relative value until the scroll location of the viewport reaches a specified threshold, at which point the element takes a fixed position where it is told to stick.
* **`inherit`** : the position value doesn’t cascade, so this can be used to specifically force it to, and inherit the positioning value from its parent.

For more info [position](https://css-tricks.com/almanac/properties/p/position/)

## top/bottom/left/right

The **`top`**, **`bottom`**, **`left`**, and **`right`** properties are used with **`position`** to set the placement of an element. They only have an effect on positioned elements, which are elements with the **`position`** property set to anything other than **`static`**. For example: **`relative`**, **`absolute`**, **`fixed`**, or **`sticky`**.

The element will will generally move away from a given side when its value is positive, and towards it when the value is negative.

Values:

* Length values \(e.g. px, em, rem, ex, etc\) 
* a percentage of the of the containing element’s height \(for **`top`** and **`bottom`**\) or width \(for **`left`** and **`right`**\)
* **`auto`**
* **`inherit`**

```css
.container {
  position: relative;
}
.container header {
  position: absolute;
  top: 0;
}
```

## z-index

controls the vertical stacking order of elements that overlap. As in, which one appears as if it is physically closer to you.

z-index only affects elements that have a **`position`** value other than **`static`** \(the default\).

```css
div {
  z-index: 1; /* integer */
}
```

