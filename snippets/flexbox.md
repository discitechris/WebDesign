# Flexbox

The main idea behind the flex layout is to give the container the ability to alter its items’ width/height \(and order\) to best fill the available space \(mostly to accommodate to all kind of display devices and screen sizes\). A flex container expands items to fill available free space or shrinks them to prevent overflow.

**Note:** **Flexbox** layout is most appropriate to the _**components of an application, and small-scale layouts**_, while the **Grid** layout is intended for _**larger scale layouts**_.

## **Major Features:**

* Features flex-containers \(row\)/parent element and flex-items \(cells\)/child elements. Both are

  required to work.

* Excels at vertical centering and equal heights
* Very easy to reorder boxes

![](../.gitbook/assets/flex-terminology.svg)

### **Components of Flexbox:**

* **Creation:** `display`
* **Direction:** `flex-flow` \(`flex-direction`, `flex-wrap`\)
* **Alignment:** `justify-content`, `align-items`, `align-self`, `align-content`
* **Ordering:** `order`
* **Flexibility:** `flex` \(`flex-grow`, `flex-shrink`, `flex-basis`\)

## Parent \(flex container\) properties

**display: flex / inline-flex   ❖  flex-direction ❖ flex-wrap** 

**❖ justify-content \(main-axis\)**

**❖ align-items \(flex-items cross-axis on current line\)**

**❖ align-content \( individual items main-axis\)**

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

![](../.gitbook/assets/flex-direction.svg)

```css
.container {
  flex-direction: row; /*or*/ flex-direction: row-reverse;
  flex-direction: column; /*or*/ flex-direction: columnreverse;
}
```

### **flex-wrap**

By default, flex items will all try to fit onto one line. You can change that and allow the items to wrap as needed with this property. flex-direction orders the individual items. flex-wrap orders the rows/columns created.

![](../.gitbook/assets/flex-wrap.svg)

```css
.container {
  flex-wrap: wrap; /*or*/ flex-wrap: nowrap; /*or*/ flex-wrap: wrap-reverse;
}
```

### **justify-content**

This defines the alignment along the main axis. It helps distribute extra free space leftover when either all the flex items on a line are inflexible, or are flexible but have reached their maximum size. It also exerts some control over the alignment of items when they overflow the line.

![](../.gitbook/assets/flex-justify-content.svg)

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

![](../.gitbook/assets/flex-align-items.svg)

```css
.container {
  align-items: flex-start; /*or*/ align-items: flex-end;
  align-items: center /*or*/ align-items: baseline;
  align-items: stretch;
}
```

### **align-content**

This aligns a flex container’s lines within when there is extra space in the cross-axis, similar to how `justify-content` aligns individual items within the main-axis.

![](../.gitbook/assets/flex-align-content.svg)

```css
.container {
  align-content: flex-start; /*or*/ align-content: flex-end;
  align-content: center; /*or*/ align-content: space-between;
  align-content: space-around; /*or*/ align-content: space-evenly;
  align-content: stretch;
}
```

## Child \(flex items\) properties

### **order**

By default, flex items are laid out in the source order. However, the order property controls the order in which they appear in the flex container.

![](../.gitbook/assets/flex-order.svg)

```css
.item {
  order: <integer>; /* default is 0 */
  order: -1; /* places above the default or 0th order */
  order: 99;
}
```

### **flex-grow**

This defines the ability for a flex item to grow if necessary. It accepts a unitless value that serves as a proportion. It dictates what amount of the available space inside the flex container the item should take up.

If all items have `flex-grow` set to `1`, the remaining space in the container will be distributed equally to all children. If one of the children has a value of `2`, the remaining space would take up twice as much space as the others \(or it will try to, at least\).

Negative numbers are invalid.

![](../.gitbook/assets/flex-grow.svg)

```css
.item {
  flex-grow: <number>; /* default 0 */
  flex-grow: 1; /*or*/ flex-grow: 3;
}
```

### **flex-shrink**

This defines the ability for a flex item to shrink if necessary.

Negative numbers are invalid.

```css
.item {
  flex-shrink: <number>; /* default 1 */
  flex-shrink: 3;
}
```

### **flex-basis**

This defines the default size of an element before the remaining space is distributed. It can be a `length` \(e.g. `20%`, `5rem`, etc.\) or a keyword. The `auto` keyword means “look at my width or height property”. The `content` keyword means “size it based on the item’s content”

If set to `0`, the extra space around content isn’t factored in. If set to `auto`, the extra space is distributed based on its `flex-grow` value

```css
.item {
  flex-basis: <length> | auto; /* default auto */
  flex-basis: 20%;
}
```

### **flex**

This is the shorthand for `flex-grow`, `flex-shrink` and `flex-basis` combined. The second and third parameters \(`flex-shrink` and `flex-basis`\) are optional. The default is `0` `1` `auto`, but if you set it with a single number value, it’s like `<number>` `1` `0`.

**It is recommended that you use this shorthand property** rather than set the individual properties. The shorthand sets the other values intelligently.

```css
.item {
  flex: none | [ <'flex-grow'> <'flex-shrink'>? || <'flex-basis'> ];
  flex: 0 1 20%;
  flex: 1;
}
```

### **align-self**

This allows the default alignment \(or the one specified by `align-items`\) to be overridden for individual flex items. 

in other words **overrides alignment** set on **parent**.

Please see the `align-items` explanation to understand the available values.

**Note** that `float`, `clear` and `vertical-align` have no effect on a flex item.

![](../.gitbook/assets/align-self.svg)

```css
.item {
  align-self: auto; /*or*/ align-self: flex-start; /*or*/ align-self: flex-end; /*or*/ align-self: center; /*or*/ align-self: baseline; /*or*/ align-self: stretch;
}
```

