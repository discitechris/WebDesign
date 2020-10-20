# Block Element Modifier

## Block

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

## Element

A part of a block that has no standalone meaning and is semantically tied to its **block**.

**Examples**

**`menu item`**, **`list item`**, **`checkbox caption`**, **`header title`**

## Modifier

A flag on a block or element. Use them to change appearance or behavior.

**Examples**

**`disabled`**, **`highlighted`**, **`checked`**, **`fixed`**, **`size big`**, **`color yellow`**

