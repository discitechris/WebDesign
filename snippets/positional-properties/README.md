# Positional Properties

## Overflow

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

