# Child \(flex items\) properties

* **ALIGNMENT:**       **`align-self`**
* **ORDERING:**           **`order`**
* **FLEXIBILITY:**        **`flex`** \(**`flex-grow`**, **`flex-shrink`**, **`flex-basis`**\)

### **order**

By default, flex items are laid out in the source order. However, the order property controls the order in which they appear in the flex container.

![](../../.gitbook/assets/flex-order.svg)

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

![](../../.gitbook/assets/flex-grow.svg)

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

![](../../.gitbook/assets/align-self.svg)

```css
.item {
  align-self: auto; /*or*/ align-self: flex-start; /*or*/ align-self: flex-end; /*or*/ align-self: center; /*or*/ align-self: baseline; /*or*/ align-self: stretch;
}
```

