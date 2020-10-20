# Block Element Modifier

## Block 🧶 

Standalone entity that is meaningful on its own.

**Examples**

**`header`**, **`container`**, **`menu`**, **`checkbox`**, **`input`**

Encapsulates a standalone entity that is meaningful on its own. While blocks can be nested and interact with each other, semantically they remain equal; there is no precedence or hierarchy. Holistic entities without DOM representation \(such as controllers or models\) can be blocks as well.

### **Naming**

Block names may consist of Latin letters, digits, and dashes. To form a CSS class, add a short prefix for namespacing: `.block`

#### **HTML**

Any DOM node can be a block if it accepts a class name.

```text
<div class="block">...</div>
```

**CSS**

* Use class name selector only
* No tag name or ids
* No dependency on other blocks/elements on a page

```text
.block { color: #042; }
```

## Element 🔵 

A part of a block that has no standalone meaning and is semantically tied to its **block**.

**Examples**

**`menu item`**, **`list item`**, **`checkbox caption`**, **`header title`**

### **Naming**

Element names may consist of Latin letters, digits, dashes and underscores. CSS class is formed as block name plus two underscores plus element name: `.block__elem`

**HTML**

Any DOM node within a block can be an element. Within a given block, all elements are semantically equal.

```text
<div class="block">
	  ...
	  <span class="block__elem"></span>
	</div>
```

**CSS**

* Use class name selector only
* No tag name or ids
* No dependency on other blocks/elements on a page

**Good**

```text
.block__elem { color: #042; }
```

**Bad**

```text
.block .block__elem { color: #042; }
	div.block__elem { color: #042; }
```

## Modifier 🔴 

A flag on a block or element. Use them to change appearance or behavior.

**Examples**

**`disabled`**, **`highlighted`**, **`checked`**, **`fixed`**, **`size big`**, **`color yellow`**

### **Naming**

Modifier names may consist of Latin letters, digits, dashes and underscores. CSS class is formed as block’s or element’s name plus two dashes: `.block--mod` or `.block__elem--mod` and `.block--color-black` with `.block--color-red`. Spaces in complicated modifiers are replaced by dash.

**HTML**

Modifier is an extra class name which you add to a block/element DOM node. Add modifier classes only to blocks/elements they modify, and keep the original class:**Good**

```text
<div class="block block--mod">...</div>
	<div class="block block--size-big
		block--shadow-yes">...</div>
```

**Bad**

```text
<div class="block--mod">...</div>
```

**CSS**

Use modifier class name as selector:

```text
.block--hidden { }
```

To alter elements based on a block-level modifier:

```text
.block--mod .block__elem { }
```

Element modifier:

```text
.block__elem--mod { }
```

## Example

Suppose you have block form with modifiers `theme: "xmas"` and `simple: true` and with elements `input` and `submit`, and element `submit` with its own modifier `disabled: true` for not submitting form while it is not filled:

**HTML**

```text
<form class="form form--theme-xmas form--simple">
  <input class="form__input" type="text" />
  <input
    class="form__submit form__submit--disabled"
    type="submit" />
</form>
```

**CSS**

```text
.form { }
.form--theme-xmas { }
.form--simple { }
.form__input { }
.form__submit { }
.form__submit--disabled { }
```

![Block  ](../.gitbook/assets/bem.jpg)

#### Block 🧶 Element 🔵 Modifier 🔴 

