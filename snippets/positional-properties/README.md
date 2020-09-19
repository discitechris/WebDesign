# Positional Properties

## float

Used for positioning and layout on web pages.

* Absolute positioned elements that have **no** **`width`** set on them behave a bit strangely. Their width is only as wide as it needs to be to hold the content.

Values:

* **`none`**
* **`left`**
* **`right`**
* **`inherit`**

{% hint style="info" %}
**NOTE:**    An element that is floated is automatically **`display: block;`**
{% endhint %}

## 

## 

## 

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

