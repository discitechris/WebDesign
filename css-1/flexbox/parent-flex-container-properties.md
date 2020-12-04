# Parent \(flex container\) properties

* **DISPLAY:         `flex` / `inline-flex`**   
* **DIRECTION:    `flex-flow`** \(**`flex-direction`**, **`flex-wrap`**\)
* **ALIGNMENT:   `justify-content`** \(main-axis\) **`align-items`** \(flex-items cross-axis on current line\)                                         
*                            **`align-content`**\( individual items main-axis\)

\*\*\*\*

### **display**

This defines a flex container; inline or block depending on the given value. It enables a flex context for all its direct children.

```css
.container {
display: flex; /*or*/ display: inline-flex;
}
```

### **flex-direction**

This establishes the main-axis, thus defining the direction flex items are placed in the flex container. Flexbox is \(aside from optional wrapping\) a single-direction layout concept. Think of flex items as primarily laying out either in horizontal rows or vertical columns.

![](../../.gitbook/assets/flex-direction.svg)

```css
.container {
  flex-direction: row; /*or*/ flex-direction: row-reverse;
  flex-direction: column; /*or*/ flex-direction: columnreverse;
}
```

### **flex-wrap**

By default, flex items will all try to fit onto one line. You can change that and allow the items to wrap as needed with this property. flex-direction orders the individual items. flex-wrap orders the rows/columns created.

![](../../.gitbook/assets/flex-wrap.svg)

```css
.container {
  flex-wrap: wrap; /*or*/ flex-wrap: nowrap; /*or*/ flex-wrap: wrap-reverse;
}
```

### **justify-content**

This defines the alignment along the main axis. It helps distribute extra free space leftover when either all the flex items on a line are inflexible, or are flexible but have reached their maximum size. It also exerts some control over the alignment of items when they overflow the line.

![](../../.gitbook/assets/flex-justify-content.svg)

```css
.container {
  justify-content: flex-start; /*or*/ justify-content: flex-end;
  justify-content: center; /*or*/ justify-content: spacebetween;
  justify-content: space-around; /*or*/ justify-content: space-evenly;
}
```

There are also two additional keywords you can pair with these values: `safe` and `unsafe`. Using `safe` ensures that however you do this type of positioning, you can’t push an element such that it renders off-screen \(e.g. off the top\) in such a way the content can’t be scrolled too \(called “data loss”\).

### **align-items**

This defines the default behavior for how flex items are laid out along the cross axis on the current line. Think of it as the justify-content version for the cross axis \(perpendicular to the main-axis\).

![](../../.gitbook/assets/flex-align-items.svg)

```css
.container {
  align-items: flex-start; /*or*/ align-items: flex-end;
  align-items: center /*or*/ align-items: baseline;
  align-items: stretch;
}
```

### **align-content**

This aligns a flex container’s lines within when there is extra space in the cross-axis, similar to how `justify-content` aligns individual items within the main-axis.

![](../../.gitbook/assets/flex-align-content.svg)

```css
.container {
  align-content: flex-start; /*or*/ align-content: flex-end;
  align-content: center; /*or*/ align-content: space-between;
  align-content: space-around; /*or*/ align-content: space-evenly;
  align-content: stretch;
}
```

## 

