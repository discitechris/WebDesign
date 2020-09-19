# Position

can help you manipulate the location of an element

Relative to its original position the element above will now be nudged down from the top by 20px.

```css
.element {
  position: relative;
  top: 20px;
}
```

## static

 every element has a static position by **default**, so the element will stick to the normal page flow.

* if there is a **`left`** / **`right`** / **`top`** / **`bottom`** / **`z-index`** set then there will be _**no effect**_  on that element.
*  **`z-index`** on any element, which **doesn’t work** with **statically positioned elements**.

## **relative**

means is “relative to itself”. an element’s original position remains in the flow of the document, just like the static value.

* But now **`left`** / **`right`** / **`top`** / **`bottom`** / **`z-index`** will work.
*  If you set **`position: relative;`** on an element but **no** other positioning attributes \(**`top`**, **`left`**, **`bottom`** or **`right`**\), it will have **no effect on it’s positioning** at all, it will be exactly **same as`position: static;`**
*  Even if you don’t set a **`z-index`** value, this element will now appear **on top** of any other statically positioned element.
* It **limits the scope of absolutely positioned child elements**. Any element that is a child of the relatively positioned element can be absolutely positioned within that block. 
* The positional properties “nudge” the element from the original position in that direction.

## **absolute**

 the element is removed from the flow of the document and other elements will behave as if it’s not even there whilst all the other 

* if there is a **`left`** / **`right`** / **`top`** / **`bottom`** / **`z-index`**positional properties will work on it.
* Absolute positioned elements that have **no** **`width`** set on them behave a bit strangely. Their width is only as wide as it needs to be to hold the content.
* allows you to literally place any page element exactly where you want it.
* Remember that the positional properties values will be **relative** to the **next parent element** with **relative \(or absolute\) positioning**.
  *  If there is **no** such parent, it will default all the way back up to the **`<html>`** element itself meaning it will be **placed relative** to the **page itself.**

## **fixed**

 the element is removed from the flow of the document like absolutely positioned elements.

* In fact they behave almost the same, only fixed positioned elements are always **relative to the document**, not any particular parent, and are **unaffected by scrolling**.

## **sticky** **\(experimental\)**

*  the element is treated like a **relative value** until the scroll location of the viewport **reaches a specified threshold**, at which point the element takes a **fixed position** where it is told to stick.

## **inherit** 

 the position value doesn’t cascade, so this can be used to specifically force it to, and inherit the positioning value from its parent.

For more info [position](https://css-tricks.com/almanac/properties/p/position/)

