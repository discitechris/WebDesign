# CSS

## CSS selectors

## Basic selectors

### [Universal selector](https://developer.mozilla.org/en-US/docs/Web/CSS/Universal_selectors)

The CSS universal selector \(\*\) matches elements of any type In other words, it selects all elements. Optionally, it may be restricted to a specific namespace or to all namespaces.

* **Syntax:** `*` `ns|*` `*|*`
* **Example:** `*` will match all the elements of the document.

```css
/* Selects all elements */
* {
  color: green;
}
```

### [Type selectors](https://developer.mozilla.org/en-US/docs/Web/CSS/Type_selectors)

The CSS type selector matches elements by node name. In other words, it selects all elements of the given type within a document.

* **Syntax:** `elementname`
* **Example:** `input` will match any `<input>` element, 

```css
span {
  background-color: skyblue;
}
```

### [Class selectors](https://developer.mozilla.org/en-US/docs/Web/CSS/Class_selectors)

The CSS class selector matches elements based on the contents of their class attribute.

* **Syntax:** `.classname`
* **Example:** `.index` will match any element that has a class of `"index"`.

```markup
<p class="fancy">This paragraph has red text and "fancy" styling.</p>
```

```css
.fancy {
  font-weight: bold;
  text-shadow: 4px 4px 3px #77f;
}
```

### [ID selectors](https://developer.mozilla.org/en-US/docs/Web/CSS/ID_selectors)

The CSS ID selector matches an element based on the value of its `id` attribute. In order for the element to be selected, its `id` attribute must match exactly the value given in the selector.

* **Syntax:** `#idname`
* **Example:** `#toc` will match the element that has the ID `"toc"`.

```markup
<div id="identified">This div has a special ID on it!</div>
```

```css
#identified {
  background-color: skyblue;
}
```

### [Attribute selectors](https://developer.mozilla.org/en-US/docs/Web/CSS/Attribute_selectors)

The CSS attribute selector matches elements based on the presence or value of a given attribute. Selects all elements that have the given attribute.

* **Syntax:** `[attr]` `[attr=value]` `[attr~=value]` `[attr|=value]` `[attr^=value]` `[attr$=value]` `[attr*=value]`
* **Example:** `[autoplay]` will match all elements that have the `autoplay` attribute set \(to any value\).

```css
/* <a> elements with a title attribute */
a[title] {
  color: purple;
}
```

## Grouping selectors

### [Selector list](https://developer.mozilla.org/en-US/docs/Web/CSS/Selector_list)

The CSS selector list \(`,`\) selects all the matching nodes. To reduce the size of style sheets, one can group selectors in comma-separated lists.

* **Syntax:** `A , B`
* **Example:** `div, span` will match both `<span>` and `<div>` elements.

```css
h1, h2, h3, h4, h5, h6 { font-family: helvetica; }

#main,
.content,
article {
  font-size: 1.1em;
}
```

## Combinators

### [Descendant combinator](https://developer.mozilla.org/en-US/docs/Web/CSS/Descendant_combinator)

The ``` (space) combinator selects nodes that are descendants of the first element. The descendant combinator — typically represented by a single space (`` \`\) character — combines two selectors such that elements matched by the second selector are selected if they have an ancestor \(parent, parent's parent, parent's parent's parent, etc\) element matching the first selector. Selectors that utilize a descendant combinator are called descendant selectors.

* **Syntax:** `A B`
* **Example:** `div span` will match all `<span>` elements that are inside a `<div>` element.

```css
li li {
  list-style-type: circle;
}
```

### [Child combinator](https://developer.mozilla.org/en-US/docs/Web/CSS/Child_combinator)

The child combinator \(`>`\) is placed between two CSS selectors. It matches only those elements matched by the second selector that are the direct children of elements matched by the first.

* **Syntax:** `A > B`
* **Example:** `ul > li` will match all `<li>` elements that are nested directly inside a `<ul>` element.

```css
div > span {
  background-color: DodgerBlue;
}
```

### [General sibling combinator](https://developer.mozilla.org/en-US/docs/Web/CSS/General_sibling_combinator)

The general sibling combinator \(`~`\) separates two selectors and matches the second element only if it follows the first element \(though not necessarily immediately\), and both are children of the same parent element.

* **Syntax:** `A ~ B`
* **Example:** `p ~ span` will match all `<span>` elements that follow a `<p>`, immediately or not.

```css
p ~ span {
  color: red;
}
```

### [Adjacent sibling combinator](https://developer.mozilla.org/en-US/docs/Web/CSS/Adjacent_sibling_combinator)

The adjacent sibling combinator \(`+`\) separates two selectors and matches the second element only if it _immediately_ follows the first element, and both are children of the same parent element.

* **Syntax:** `A + B`
* **Example:** `h2 + p` will match all `<p>` elements that directly follow an `<h2>`.

```css
li:first-of-type + li {
  color: red;
}
```

## Pseudo

### [Pseudo classes](https://developer.mozilla.org/en-US/docs/Web/CSS/Pseudo-classes)

The `:` pseudo allow the selection of elements based on state information that is not contained in the document tree. A CSS pseudo-class is a keyword added to a selector that specifies a special state of the selected element\(s\). For example, `:hover` can be used to change a button's color when the user's pointer hovers over it.

**Example:** `a:visited` will match all `<a>` elements that have been visited by the user.

```css
/* Any button over which the user's pointer is hovering */
button:hover {
  color: blue;
}
```

### [Pseudo elements](https://developer.mozilla.org/en-US/docs/Web/CSS/Pseudo-elements)

A CSS pseudo-element is a keyword added to a selector that lets you style a specific part of the selected element\(s\). For example, `::first-line` can be used to change the font of the first line of a paragraph. The `::` pseudo represent entities that are not included in HTML.

**Example:** `p::first-line` will match the first line of all `<p>` elements.

```css
/* The first line of every <p> element. */
p::first-line {
  color: blue;
  text-transform: uppercase;
}
```

## Categorical CSS

### Generated Content

Contents are generated on runtime with CSS while the content is not originally add to the html element contents.

* psuedo element selector - [::before / ::after](https://css-tricks.com/almanac/selectors/a/after-and-before/)
  * property/attribute - [content](https://css-tricks.com/almanac/properties/c/content)

### Media Queries

Media queries are useful when you want to modify your site or app depending on a device's general type \(such as print vs. screen\) or specific characteristics and parameters \(such as screen resolution or browser viewport width\).

A **viewport** represents a polygonal \(normally rectangular\) area in computer graphics that is currently being viewed. In web browser terms, it refers to the part of the document you're viewing which is currently visible in its window \(or the screen, if the document is being viewed in full screen mode\). Content outside the viewport is not visible onscreen until scrolled into view.

The portion of the viewport that is currently visible is called the visual viewport. This can be smaller than the layout viewport, such as when the user has pinched-zoomed. The layout viewport remains the same, but the visual viewport became smaller.

#### Targeting media types

Media types describe the general category of a given device. Although websites are commonly designed with screens in mind, you may want to create styles that target special devices such as printers or audio-based screenreaders. For example, this CSS targets printers:

```css
@media print { ... }
/*You can also target multiple devices. For instance, this @media rule uses two media queries to target both screen and print devices:*/
@media screen, print { ... }

@media screen and (max-width: 600px){
  #presentation {
    background red;
  }
}
@media screen and (orientation: portrait){
  #presentation {
    background yellow;
  }
}
```

#### Media Queries syntax:

"**only**" leaves out older browsers

```css
media="only print and (color)"
`
```

"**and**" - both parts must be true

```css
media="only screen and (orientation: portrait)"
```

"**not**" - if untrue

```css
media="not screen and (color)"
```

**Comma** separates selectors - any part can be true

```css
media="print, screen and (min-width: 480px)"
```

Media types describe the general category of a device. Except when using the `not` or `only` logical operators, the media type is optional and the `all` type will be implied.

* **all** — Suitable for all devices.
* **print** — Intended for paged material and documents viewed on a screen in print preview mode.
* **screen** — Intended primarily for screens.
* **speech** — Intended for speech synthesizers.

#### Media Queries in link

You can give specific css stylesheets for specific screen sizes for example;

```css
<link rel='stylesheet' media='screen and (min-width: 240px) and (max-width: 480px)' href='css/smartphone.css' />
```

#### Media queries properties

* \(min/max\)-width: viewport width
* \(min/max\)-height: viewport height
* orientation: portrait\(h&gt;w\) \| landscape\(w&gt;h\)
* \(min/max\)-aspect-ratio: width/height
* \(min/max\)-resolution: 72dpi

### Flexbox

The main idea behind the flex layout is to give the container the ability to alter its items’ width/height \(and order\) to best fill the available space \(mostly to accommodate to all kind of display devices and screen sizes\). A flex container expands items to fill available free space or shrinks them to prevent overflow.

Most importantly, the flexbox layout is direction-agnostic as opposed to the regular layouts \(block which is vertically-based and inline which is horizontally-based\). While those work well for pages, they lack flexibility \(no pun intended\) to support large or complex applications \(especially when it comes to orientation changing, resizing, stretching, shrinking, etc.\).

**Note:** Flexbox layout is most appropriate to the components of an application, and small-scale layouts, while the Grid layout is intended for larger scale layouts.

#### Major Features:

* The first layout elements – but not designed to lay out

  whole web pages

* Features flex-containers \(row\)/parent element and flex-items \(cells\)/child elements. Both are

  required to work.

* Excels at vertical centering and equal heights
* Very easy to reorder boxes

#### Major disadvantages:

* Wasn’t designed to be locked down for layouts! Works in

  1 dimension only.

* Browser support and syntax is challenging.

#### Components of Flexbox:

* **Creation:** `display`
* **Direction:** `flex-flow` \(`flex-direction`, `flex-wrap`\)
* **Alignment:** `justify-content`, `align-items`, `align-self`, `align-content`
* **Ordering:** `order`
* **Flexibility:** `flex` \(`flex-grow`, `flex-shrink`, `flex-basis`\)

### Properties for the Parent \(flex container\)

#### `display`

This defines a flex container; inline or block depending on the given value. It enables a flex context for all its direct children.

```css
.container {
display: flex; /*or*/ display: inline-flex;
}
```

#### `flex-direction`

This establishes the main-axis, thus defining the direction flex items are placed in the flex container. Flexbox is \(aside from optional wrapping\) a single-direction layout concept. Think of flex items as primarily laying out either in horizontal rows or vertical columns.

```css
.container {
  flex-direction: row; /*or*/ flex-direction: row-reverse;
  flex-direction: column; /*or*/ flex-direction: columnreverse;
}
```

#### `flex-wrap`

By default, flex items will all try to fit onto one line. You can change that and allow the items to wrap as needed with this property. flex-direction orders the individual items. flex-wrap orders the rows/columns created.

```css
.container {
  flex-wrap: wrap; /*or*/ flex-wrap: nowrap; /*or*/ flex-wrap: wrap-reverse;
}
```

#### `flex-flow`

`flex-flow` applies to the parent flex container element. This is a shorthand for the `flex-direction` and `flex-wrap` properties, which together define the `flex` container’s main and cross axis. Just because the row/column is reversed does not mean the wrap has to be reversed. The default value is `row` `nowrap`.

```css
.container {
  flex-flow: row wrap; /*or*/ flex-flow: row-reverse wrap;
  flex-flow: column nowrap /*or*/; flex-flow: column-reverse; 
  flex-flow: wrap-reverse, etc
}
```

#### `justify-content`

This defines the alignment along the main axis. It helps distribute extra free space leftover when either all the flex items on a line are inflexible, or are flexible but have reached their maximum size. It also exerts some control over the alignment of items when they overflow the line.

```css
.container {
  justify-content: flex-start; /*or*/ justify-content: flex-end;
  justify-content: center; /*or*/ justify-content: spacebetween;
  justify-content: space-around; /*or*/ justify-content: space-evenly;
}
```

There are also two additional keywords you can pair with these values: `safe` and `unsafe`. Using `safe` ensures that however you do this type of positioning, you can’t push an element such that it renders off-screen \(e.g. off the top\) in such a way the content can’t be scrolled too \(called “data loss”\).

#### `align-items`

This defines the default behavior for how flex items are laid out along the cross axis on the current line. Think of it as the justify-content version for the cross axis \(perpendicular to the main-axis\).

```css
.container {
  align-items: flex-start; /*or*/ align-items: flex-end;
  align-items: center /*or*/ align-items: baseline;
  align-items: stretch;
}
```

#### `align-content`

This aligns a flex container’s lines within when there is extra space in the cross-axis, similar to how `justify-content` aligns individual items within the main-axis.

```css
.container {
  align-content: flex-start; /*or*/ align-content: flex-end;
  align-content: center; /*or*/ align-content: space-between;
  align-content: space-around; /*or*/ align-content: space-evenly;
  align-content: stretch;
}
```

### Properties for the Child \(flex items\)

#### `order`

By default, flex items are laid out in the source order. However, the order property controls the order in which they appear in the flex container.

```css
.item {
  order: <integer>; /* default is 0 */
  order: -1; /* places above the default or 0th order */
  order: 99;
}
```

#### `flex-grow`

This defines the ability for a flex item to grow if necessary. It accepts a unitless value that serves as a proportion. It dictates what amount of the available space inside the flex container the item should take up.

If all items have `flex-grow` set to `1`, the remaining space in the container will be distributed equally to all children. If one of the children has a value of `2`, the remaining space would take up twice as much space as the others \(or it will try to, at least\).

Negative numbers are invalid.

```css
.item {
  flex-grow: <number>; /* default 0 */
  flex-grow: 1; /*or*/ flex-grow: 3;
}
```

#### `flex-shrink`

This defines the ability for a flex item to shrink if necessary.

Negative numbers are invalid.

```css
.item {
  flex-shrink: <number>; /* default 1 */
  flex-shrink: 3;
}
```

#### `flex-basis`

This defines the default size of an element before the remaining space is distributed. It can be a `length` \(e.g. `20%`, `5rem`, etc.\) or a keyword. The `auto` keyword means “look at my width or height property”. The `content` keyword means “size it based on the item’s content”

If set to `0`, the extra space around content isn’t factored in. If set to `auto`, the extra space is distributed based on its `flex-grow` value

```css
.item {
  flex-basis: <length> | auto; /* default auto */
  flex-basis: 20%;
}
```

#### `flex`

This is the shorthand for `flex-grow`, `flex-shrink` and `flex-basis` combined. The second and third parameters \(`flex-shrink` and `flex-basis`\) are optional. The default is `0` `1` `auto`, but if you set it with a single number value, it’s like `<number>` `1` `0`.

**It is recommended that you use this shorthand property** rather than set the individual properties. The shorthand sets the other values intelligently.

```css
.item {
  flex: none | [ <'flex-grow'> <'flex-shrink'>? || <'flex-basis'> ];
  flex: 0 1 20%;
  flex: 1;
}
```

#### `align-self`

This allows the default alignment \(or the one specified by `align-items`\) to be overridden for individual flex items. in other words overides alignment set on parent.

Please see the `align-items` explanation to understand the available values.

Note that `float`, `clear` and `vertical-align` have no effect on a flex item.

```css
.item {
  align-self: auto; /*or*/ align-self: flex-start; /*or*/ align-self: flex-end; /*or*/ align-self: center; /*or*/ align-self: baseline; /*or*/ align-self: stretch;
}
```

### 

### Grid

Grid Layout is the most powerful layout system available in CSS. It is a 2-dimensional system, meaning it can handle both columns and rows, unlike flexbox which is largely a 1-dimensional system. You work with Grid Layout by applying CSS rules both to a parent element \(which becomes the Grid Container\) and to that element’s children \(which become Grid Items\).

### Properties for the Parent \(Grid Container\)

#### display

Defines the element as a grid container and establishes a new grid formatting context for its contents.

Values:

**grid** – generates a block-level grid

**inline-grid** – generates an inline-level grid

```css
.container {
  display: grid | inline-grid;
}
```

#### grid-template-columns / grid-template-rows

Defines the columns and rows of the grid with a space-separated list of values. The values represent the track size, and the space between them represents the grid line.

Values:

**`<track-size>`** – can be a length, a percentage, or a fraction of the free space in the grid \(using the `fr` unit\)

**`<line-name>`** – an arbitrary name of your choosing

```css
.container {
  grid-template-columns:  ... |   ...;
  grid-template-rows:  ... |   ...;
  grid-template-columns: 40px 50px auto 50px 40px;
  grid-template-rows: 25% 100px auto;
  grid-template-columns: 1fr 1fr 1fr;
  grid-template-columns: 1fr 50px 1fr 1fr;
}
```

#### grid-template-areas

Defines a grid template by referencing the names of the grid areas which are specified with the `grid-area` property. Repeating the name of a grid area causes the content to span those cells. A period signifies an empty cell. The syntax itself provides a visualization of the structure of the grid.

Values:

**`<grid-area-name>`** – the name of a grid area specified with grid-area

**\(`.`\)** – a period signifies an empty grid cell

**`none`** – no grid areas are defined

```css
.container {
  grid-template-areas: 
    " | . | none | ..."
    "...";
}
.item-a {
  grid-area: header;
}
.item-b {
  grid-area: main;
}
.item-c {
  grid-area: sidebar;
}
.item-d {
  grid-area: footer;
}

.container {
  display: grid;
  grid-template-columns: 50px 50px 50px 50px;
  grid-template-rows: auto;
  grid-template-areas: 
    "header header header header"
    "main main . sidebar"
    "footer footer footer footer";
}
```

#### grid-template

A shorthand for setting `grid-template-rows`, `grid-template-columns`, and `grid-template-areas` in a single declaration.

Values:

**none** – sets all three properties to their initial values

 **/**  – sets `grid-template-columns` and `grid-template-rows` to the specified values, respectively, and sets `grid-template-areas` to `none`

```css
.container {
  grid-template: none | <grid-template-rows> / <grid-template-columns>;
}
```

#### column-gap / row-gap

Specifies the size of the grid lines. You can think of it like setting the width of the gutters between the columns/rows.

Values:

**`<line-size>`** – a length value

```css
.container {
  column-gap: <line-size>;
  row-gap: <line-size>;
  column-gap: 10px;
  row-gap: 15px;
}
```

#### gap / grid-gap

A shorthand for `row-gap` and `column-gap`

Values:

**`<grid-row-gap> <grid-column-gap>`** – length values

```css
.container {
  /* standard */
  gap: <grid-row-gap> <grid-column-gap>;
  gap: 15px 10px;

  /* old */
  grid-gap: <grid-row-gap> <grid-column-gap>;
  grid-gap: 15px 10px;
}
```

#### justify-items

Aligns grid items along the inline \(row\) axis \(as opposed to `align-items` which aligns along the block \(column\) axis\). This value applies to all grid items inside the container.

Values:

**start** – aligns items to be flush with the start edge of their cell

**end** – aligns items to be flush with the end edge of their cell

**center** – aligns items in the center of their cell

**stretch** – fills the whole width of the cell \(this is the default\)

```css
.container {
  justify-items: start | end | center | stretch;
}
```

#### align-items

Aligns grid items along the block \(column\) axis \(as opposed to `justify-items` which aligns along the inline \(row\) axis\). This value applies to all grid items inside the container.

Values:

**start** – aligns items to be flush with the start edge of their cell

**end** – aligns items to be flush with the end edge of their cell

**center** – aligns items in the center of their cell

**stretch** – fills the whole height of the cell \(this is the default\)

```css
.container {
  align-items: start | end | center | stretch;
}
```

#### place-items

place-items sets both the align-items and justify-items properties in a single declaration.

Values:

**`<align-items> / <justify-items>`** – The first value sets align-items, the second value justify-items. If the second value is omitted, the first value is assigned to both properties.

#### justify-content

Sometimes the total size of your grid might be less than the size of its grid container. This could happen if all of your grid items are sized with non-flexible units like `px`. In this case you can set the alignment of the grid within the grid container. This property aligns the grid along the inline \(row\) axis \(as opposed to `align-content` which aligns the grid along the block \(column\) axis\).

Values:

**start** – aligns the grid to be flush with the start edge of the grid container

**end** – aligns the grid to be flush with the end edge of the grid container

**center** – aligns the grid in the center of the grid container

**stretch** – resizes the grid items to allow the grid to fill the full width of the grid container

**space-around** – places an even amount of space between each grid item, with half-sized spaces on the far ends

**space-between** – places an even amount of space between each grid item, with no space at the far ends

**space-evenly** – places an even amount of space between each grid item, including the far ends

```css
.container {
  justify-content: start | end | center | stretch | space-around | space-between | space-evenly;
}
```

#### align-content

Sometimes the total size of your grid might be less than the size of its grid container. This could happen if all of your grid items are sized with non-flexible units like px. In this case you can set the alignment of the grid within the grid container. This property aligns the grid along the block \(column\) axis \(as opposed to justify-content which aligns the grid along the inline \(row\) axis\).

Values:

**start** – aligns the grid to be flush with the start edge of the grid container

**end** – aligns the grid to be flush with the end edge of the grid container

**center** – aligns the grid in the center of the grid container

**stretch** – resizes the grid items to allow the grid to fill the full height of the grid container

**space-around** – places an even amount of space between each grid item, with half-sized spaces on the far ends

**space-between** – places an even amount of space between each grid item, with no space at the far ends **space-evenly** – places an even amount of space between each grid item, including the far ends

```css
.container {
  align-content: start | end | center | stretch | space-around | space-between | space-evenly;
}
```

#### place-content

place-content sets both the `align-content` and `justify-content` properties in a single declaration.

Values:

`<align-content> / <justify-content>` – The first value sets `align-content`, the second value `justify-content`. If the second value is omitted, the first value is assigned to both properties. All major browsers except Edge support the place-content shorthand property.

#### grid-auto-columns / grid-auto-rows

Specifies the size of any auto-generated grid tracks \(aka implicit grid tracks\). Implicit tracks get created when there are more grid items than cells in the grid or when a grid item is placed outside of the explicit grid Values:

`<track-size>` – can be a length, a percentage, or a fraction of the free space in the grid \(using the `fr` unit\)

```css
.container {
  grid-template-columns: 60px 60px;
  grid-template-rows: 90px 90px;
  grid-auto-columns: 60px;
}
.item-a {
  grid-column: 1 / 2;
  grid-row: 2 / 3;
}
.item-b {
  grid-column: 5 / 6;
  grid-row: 2 / 3;
}
```

#### grid-auto-flow

If you have grid items that you don’t explicitly place on the grid, the auto-placement algorithm kicks in to automatically place the items. This property controls how the auto-placement algorithm works.

Values:

**row** – tells the auto-placement algorithm to fill in each row in turn, adding new rows as necessary \(default\)

**column** – tells the auto-placement algorithm to fill in each column in turn, adding new columns as necessary

**dense** – tells the auto-placement algorithm to attempt to fill in holes earlier in the grid if smaller items come up later

Note:

**dense** only changes the visual order of your items and might cause them to appear out of order, which is bad for accessibility.

```css
.container {
  grid-auto-flow: row | column | row dense | column dense;
}
```

#### Special Functions and Keywords

* When sizing rows and columns, you can use all the lengths you are used to, like px, rem, %, etc, but you also have keywords like `min-content`, `max-content`, `auto`, and perhaps the most useful, fractional units. `grid-template-columns: 200px 1fr 2fr min-content;`
* You also have access to a function which can help set boundaries for otherwise flexible units. For example to set a column to be 1fr, but shrink no further than 200px: `grid-template-columns: 1fr minmax(200px, 1fr);`
* There is `repeat()` function, which saves some typing, like making 10 columns: `grid-template-columns: repeat(10, 1fr);`
* Combining all of these things can be extremely powerful, like `grid-template-columns: repeat(auto-fill, minmax(200px, 1fr));`

### Properties for the Children \(Grid Items\)

Note: `float`, `display: inline-block`, `display: table-cell`,`vertical-align` and `column-*` properties have no effect on a grid item.

#### grid-column / grid-row

Shorthand for grid-column-start + grid-column-end, and grid-row-start + grid-row-end, respectively.

Values:

**`<start-line> / <end-line>`** – each one accepts all the same values as the longhand version, including span

If no end line value is declared, the item will span 1 track by default.

```css
.item-c {
  grid-column: 3 / span 2;
  grid-row: third-line / 4;
  grid-column: 1 / 4;
  grid-row: 1 / 2;
}
```

#### grid-area

Gives an item a name so that it can be referenced by a template created with the `grid-template-areas` property. Alternatively, this property can be used as an even shorter shorthand for `grid-row-start` + `grid-column-start` + `grid-row-end` + `grid-column-end`.

Values:

**`<name>`** – a name of your choosing

**`<row-start> / <column-start> / <row-end> / <column-end>`** – can be numbers or named lines

```css
.item {
  grid-area: <name> | <row-start> / <column-start> / <row-end> / <column-end>;
  grid-area: header;
}
```

#### justify-self

Aligns a grid item inside a cell along the inline \(row\) axis \(as opposed to `align-self` which aligns along the block \(column\) axis\). This value applies to a grid item inside a single cell.

Values:

**start** – aligns the grid item to be flush with the start edge of the cell

**end** – aligns the grid item to be flush with the end edge of the cell

**center** – aligns the grid item in the center of the cell

**stretch** – fills the whole width of the cell \(this is the default\)

```css
.item {
  justify-self: start | end | center | stretch;
  justify-self: start;
}
```

#### align-self

Aligns a grid item inside a cell along the block \(column\) axis \(as opposed to `justify-self` which aligns along the inline \(row\) axis\). This value applies to the content inside a single grid item.

Values:

**start** – aligns the grid item to be flush with the start edge of the cell

**end** – aligns the grid item to be flush with the end edge of the cell

**center** – aligns the grid item in the center of the cell

**stretch** – fills the whole height of the cell \(this is the default\)

```css
.item {
  align-self: start | end | center | stretch;
}
```

#### place-self

`place-self` sets both the `align-self` and `justify-self` properties in a single declaration.

Values:

**auto** – The “default” alignment for the layout mode.

**`<align-self> / <justify-self>`** – The first value sets align-self, the second value justify-self. If the second value is omitted, the first value is assigned to both properties.

```css
.item-a {
  place-self: center;
  place-self: center stretch;
}
```

### CSS Properties Reference

### A Selector

* [**::before / ::after**](https://css-tricks.com/almanac/selectors/a/after-and-before/)
  * Necessarry Property :[content](https://css-tricks.com/almanac/properties/c/content)
* [**:active**](https://css-tricks.com/almanac/selectors/a/active/)
* [**:any-link**](https://css-tricks.com/almanac/selectors/a/any-link/)
* [**Adjacent sibling**](https://css-tricks.com/almanac/selectors/a/adjacent-sibling/)
* [**attribute**](https://css-tricks.com/almanac/selectors/a/attribute/)

### A Properties

* [**align-content**](https://css-tricks.com/almanac/properties/a/align-content)
* [**align-items**](https://css-tricks.com/almanac/properties/a/align-items)
* [**align-self**](https://css-tricks.com/almanac/properties/a/align-self)
* [**all**](https://css-tricks.com/almanac/properties/a/all)
* [**animation**](https://css-tricks.com/almanac/properties/a/animation)
* [**appearance**](https://css-tricks.com/almanac/properties/a/appearance)

### B Selector

* [**:blank**](https://css-tricks.com/almanac/selectors/b/blank)

### B Properties

* [**backdrop-filter**](https://css-tricks.com/almanac/properties/b/backdrop-filter)
* [**backface-visibility**](https://css-tricks.com/almanac/properties/b/backface-visibility)
* [**background**](https://css-tricks.com/almanac/properties/b/background)
* [**background-attachment**](https://css-tricks.com/almanac/properties/b/background-attachment)
* [**background-blend-mode**](https://css-tricks.com/almanac/properties/b/background-blend-mode)
* [**background-clip**](https://css-tricks.com/almanac/properties/b/background-clip)
* [**background-color**](https://css-tricks.com/almanac/properties/b/background-color)
* [**background-image**](https://css-tricks.com/almanac/properties/b/background-image)
* [**background-origin**](https://css-tricks.com/almanac/properties/b/background-origin)
* [**background-position**](https://css-tricks.com/almanac/properties/b/background-position)
* [**background-repeat**](https://css-tricks.com/almanac/properties/b/background-repeat)
* [**background-size**](https://css-tricks.com/almanac/properties/b/background-size)
* [**bleed**](https://css-tricks.com/almanac/properties/b/bleed)
* [**block-overflow**](https://css-tricks.com/almanac/properties/b/block-overflow)
* [**border**](https://css-tricks.com/almanac/properties/b/border)
* [**border-collapse**](https://css-tricks.com/almanac/properties/b/border-collapse)
* [**border-image**](https://css-tricks.com/almanac/properties/b/border-image)
* [**border-radius**](https://css-tricks.com/almanac/properties/b/border-radius)
* [**border-spacing**](https://css-tricks.com/almanac/properties/b/border-spacing)
* [**bottom**](https://css-tricks.com/almanac/properties/b/bottom)
* [**box-decoration-break**](https://css-tricks.com/almanac/properties/b/box-decoration-break)
* [**box-shadow**](https://css-tricks.com/almanac/properties/b/box-shadow)
* [**box-sizing**](https://css-tricks.com/almanac/properties/b/box-sizing)
* [**break-inside**](https://css-tricks.com/almanac/properties/b/break-inside)

### C Selector

* [**:checked**](https://css-tricks.com/almanac/selectors/c/checked)
* [**Child**](https://css-tricks.com/almanac/selectors/c/child)
* [**Class**](https://css-tricks.com/almanac/selectors/c/class/) ****⭐ **01**

### C Properties

* [**caption-side**](https://css-tricks.com/almanac/properties/c/caption-side)
* [**caret-color**](https://css-tricks.com/almanac/properties/c/caret-color)
* [**clear**](https://css-tricks.com/almanac/properties/c/clear)
* [**clip-path**](https://css-tricks.com/almanac/properties/c/clip-path)
* [**color**](https://css-tricks.com/almanac/properties/c/color)
* [**color-adjust**](https://css-tricks.com/almanac/properties/c/color-adjust)
* [**column-count**](https://css-tricks.com/almanac/properties/c/column-count)
* [**column-fill**](https://css-tricks.com/almanac/properties/c/column-fill)
* [**column-gap**](https://css-tricks.com/almanac/properties/c/column-gap)
* [**column-rule**](https://css-tricks.com/almanac/properties/c/column-rule)
* [**column-span**](https://css-tricks.com/almanac/properties/c/column-span)
* [**column-width**](https://css-tricks.com/almanac/properties/c/column-width)
* [**columns**](https://css-tricks.com/almanac/properties/c/columns)
* [**content**](https://css-tricks.com/almanac/properties/c/content)
* [**counter-increment**](https://css-tricks.com/almanac/properties/c/counter-increment)
* [**counter-reset**](https://css-tricks.com/almanac/properties/c/counter-reset)
* [**cursor**](https://css-tricks.com/almanac/properties/c/cursor)

### D Selector

* [**:default**](https://css-tricks.com/almanac/selectors/d/default)
* [**:dir\(\)**](https://css-tricks.com/almanac/selectors/d/dir)
* [**:disabled**](https://css-tricks.com/almanac/selectors/d/disabled)
* [**Descendant**](https://css-tricks.com/almanac/selectors/d/descendant) ****⭐ **04**

### D Properties

* [**direction**](https://css-tricks.com/almanac/properties/d/direction)
* [**display**](https://css-tricks.com/almanac/properties/d/display)

### E Selector

* [**:empty**](https://css-tricks.com/almanac/selectors/e/empty)
* [**:enabled**](https://css-tricks.com/almanac/selectors/e/enabled)

### E Properties

* [**empty-cells**](https://css-tricks.com/almanac/properties/e/empty-cells)

### F Selector

* [**::first-letter**](https://css-tricks.com/almanac/selectors/f/first-letter)
* [**::first-line**](https://css-tricks.com/almanac/selectors/f/first-line)
* [**:first-child**](https://css-tricks.com/almanac/selectors/f/first-child)
* [**:first-of-type**](https://css-tricks.com/almanac/selectors/f/first-of-type)
* [**:focus**](https://css-tricks.com/almanac/selectors/f/focus)
* [**:focus-visible**](https://css-tricks.com/almanac/selectors/f/focus-visible)
* [**:focus-within**](https://css-tricks.com/almanac/selectors/f/focus-within)

### F Properties

* [**fill**](https://css-tricks.com/almanac/properties/f/fill)
* [**filter**](https://css-tricks.com/almanac/properties/f/filter)
* [**flex**](https://css-tricks.com/almanac/properties/f/flex)
* [**flex-basis**](https://css-tricks.com/almanac/properties/f/flex-basis)
* [**flex-direction**](https://css-tricks.com/almanac/properties/f/flex-direction)
* [**flex-flow**](https://css-tricks.com/almanac/properties/f/flex-flow)
* [**flex-grow**](https://css-tricks.com/almanac/properties/f/flex-grow)
* [**flex-shrink**](https://css-tricks.com/almanac/properties/f/flex-shrink)
* [**flex-wrap**](https://css-tricks.com/almanac/properties/f/flex-wrap)
* [**float**](https://css-tricks.com/almanac/properties/f/float)
* [**font**](https://css-tricks.com/almanac/properties/f/font)
* [**font-display**](https://css-tricks.com/almanac/properties/f/font-display)
* [**font-family**](https://css-tricks.com/almanac/properties/f/font-family)
* [**font-feature-settings**](https://css-tricks.com/almanac/properties/f/font-feature-settings)
* [**font-size**](https://css-tricks.com/almanac/properties/f/font-size)
* [**font-size-adjust**](https://css-tricks.com/almanac/properties/f/font-size-adjust)
* [**font-stretch**](https://css-tricks.com/almanac/properties/f/font-stretch)
* [**font-style**](https://css-tricks.com/almanac/properties/f/font-style)
* [**font-variant**](https://css-tricks.com/almanac/properties/f/font-variant)
* [**font-variant-numeric**](https://css-tricks.com/almanac/properties/f/font-variant-numeric)
* [**font-weight**](https://css-tricks.com/almanac/properties/f/font-weight)

### G Selector

* [**General sibling**](https://css-tricks.com/almanac/selectors/g/general-sibling)

### G Properties

* [**grid-row / grid-column**](https://css-tricks.com/almanac/properties/g/grid-row-column)
* [**grid-template-columns / grid-template-rows**](https://css-tricks.com/almanac/properties/g/grid-rows-columns)

### H Selector

* [**:hover**](https://css-tricks.com/almanac/selectors/h/hover)

### H Properties

* [**hanging-punctuation**](https://css-tricks.com/almanac/properties/h/hanging-punctuation)
* [**height**](https://css-tricks.com/almanac/properties/h/height)
* [**hyphens**](https://css-tricks.com/almanac/properties/h/hyphenate)

### I Selector

* [**:in-range**](https://css-tricks.com/almanac/selectors/i/in-range)
* [**:indeterminate**](https://css-tricks.com/almanac/selectors/i/indeterminate)
* [**:invalid**](https://css-tricks.com/almanac/selectors/i/invalid)
* [**:is\(\)**](https://css-tricks.com/almanac/selectors/i/is)
* [**ID**](https://css-tricks.com/almanac/selectors/i/id) ****⭐ **02**

### I Properties

* [**image-rendering**](https://css-tricks.com/almanac/properties/i/image-rendering)
* [**initial-letter**](https://css-tricks.com/almanac/properties/i/initial-letter)
* [**isolation**](https://css-tricks.com/almanac/properties/i/isolation)

### J Properties \(No Selector\)

* [**justify-content**](https://css-tricks.com/almanac/properties/j/justify-content)

### L Selector

* [**:lang\(\)**](https://css-tricks.com/almanac/selectors/l/lang)
* [**:last-child**](https://css-tricks.com/almanac/selectors/l/last-child)
* [**:last-of-type**](https://css-tricks.com/almanac/selectors/l/last-of-type)
* [**:link**](https://css-tricks.com/almanac/selectors/l/link)

### L Properties

* [**left**](https://css-tricks.com/almanac/properties/l/left)
* [**letter-spacing**](https://css-tricks.com/almanac/properties/l/letter-spacing)
* [**line-clamp**](https://css-tricks.com/almanac/properties/l/line-clamp)
* [**line-height**](https://css-tricks.com/almanac/properties/l/line-height)
* [**list-style**](https://css-tricks.com/almanac/properties/l/list-style)

### M Selector

* [**::marker**](https://css-tricks.com/almanac/selectors/m/marker)
* [**:matches\(\)**](https://css-tricks.com/almanac/selectors/m/matches)

### M Properties

* [**margin**](https://css-tricks.com/almanac/properties/m/margin)
* [**max-height**](https://css-tricks.com/almanac/properties/m/max-height)
* [**max-width**](https://css-tricks.com/almanac/properties/m/max-width)
* [**min-height**](https://css-tricks.com/almanac/properties/m/min-height)
* [**min-width**](https://css-tricks.com/almanac/properties/m/min-width)
* [**mix-blend-mode**](https://css-tricks.com/almanac/properties/m/mix-blend-mode)

### N Selector \(No Properties\)

* [**:not\(\)**](https://css-tricks.com/almanac/selectors/n/not)
* [**:nth-child**](https://css-tricks.com/almanac/selectors/n/nth-child)
* [**:nth-last-child**](https://css-tricks.com/almanac/selectors/n/nth-last-child)
* [**:nth-last-of-type**](https://css-tricks.com/almanac/selectors/n/nth-last-of-type)
* [**:nth-of-type**](https://css-tricks.com/almanac/selectors/n/nth-of-type)

### O Selector

* [**:only-child**](https://css-tricks.com/almanac/selectors/o/only-child)
* [**:only-of-type**](https://css-tricks.com/almanac/selectors/o/only-of-type)
* [**:optional**](https://css-tricks.com/almanac/selectors/o/optional)
* [**:out-of-range**](https://css-tricks.com/almanac/selectors/o/out-of-range)

### O Properties

* [**object-fit**](https://css-tricks.com/almanac/properties/o/object-fit)
* [**object-position**](https://css-tricks.com/almanac/properties/o/object-position)
* [**offset-anchor**](https://css-tricks.com/almanac/properties/o/offset-anchor)
* [**offset-distance**](https://css-tricks.com/almanac/properties/o/offset-distance)
* [**offset-path**](https://css-tricks.com/almanac/properties/o/offset-path)
* [**offset-rotate**](https://css-tricks.com/almanac/properties/o/offset-rotate)
* [**opacity**](https://css-tricks.com/almanac/properties/o/opacity)
* [**order**](https://css-tricks.com/almanac/properties/o/order)
* [**orphans**](https://css-tricks.com/almanac/properties/o/orphans)
* [**outline**](https://css-tricks.com/almanac/properties/o/outline)
* [**outline-offset**](https://css-tricks.com/almanac/properties/o/outline-offset)
* [**overflow**](https://css-tricks.com/almanac/properties/o/overflow)
* [**overflow-anchor**](https://css-tricks.com/almanac/properties/o/overflow-anchor)
* [**overflow-wrap**](https://css-tricks.com/almanac/properties/o/overflow-wrap)
* [**overscroll-behavior**](https://css-tricks.com/almanac/properties/o/overscroll-behavior)

### P Selector

* [**::placeholder**](https://css-tricks.com/almanac/selectors/p/placeholder)
* [**:placeholder-shown**](https://css-tricks.com/almanac/selectors/p/placeholder-shown)

### P Properties

* [**padding**](https://css-tricks.com/almanac/properties/p/padding)
* [**page-break**](https://css-tricks.com/almanac/properties/p/page-break)
* [**perspective**](https://css-tricks.com/almanac/properties/p/perspective)
* [**perspective-origin**](https://css-tricks.com/almanac/properties/p/perspective-origin)
* [**place-items**](https://css-tricks.com/almanac/properties/p/place-items)
* [**pointer-events**](https://css-tricks.com/almanac/properties/p/pointer-events)
* [**position**](https://css-tricks.com/almanac/properties/p/position)

### Q Properties \(No Selector\)

* [**quotes**](https://css-tricks.com/almanac/properties/q/quotes)

### R Selector

* [**:read-write / :read-only**](https://css-tricks.com/almanac/selectors/r/read-write-read)
* [**:required**](https://css-tricks.com/almanac/selectors/r/required)
* [**:root**](https://css-tricks.com/almanac/selectors/r/root)

### R Properties

* [**resize**](https://css-tricks.com/almanac/properties/r/resize)
* [**right**](https://css-tricks.com/almanac/properties/r/right)

### S Selector

* [**::selection**](https://css-tricks.com/almanac/selectors/s/selection)

### S Properties

* [**scroll-behavior**](https://css-tricks.com/almanac/properties/s/scroll-behavior)
* [**scroll-margin**](https://css-tricks.com/almanac/properties/s/scroll-margin)
* [**scroll-padding**](https://css-tricks.com/almanac/properties/s/scroll-padding)
* [**scroll-snap-align**](https://css-tricks.com/almanac/properties/s/scroll-snap-align)
* [**scroll-snap-stop**](https://css-tricks.com/almanac/properties/s/scroll-snap-stop)
* [**scroll-snap-type**](https://css-tricks.com/almanac/properties/s/scroll-snap-type)
* [**scrollbar**](https://css-tricks.com/almanac/properties/s/scrollbar)
* [**scrollbar-color**](https://css-tricks.com/almanac/properties/s/scrollbar-color)
* [**scrollbar-gutter**](https://css-tricks.com/almanac/properties/s/scrollbar-gutter)
* [**scrollbar-width**](https://css-tricks.com/almanac/properties/s/scrollbar-width)
* [**shape-outside**](https://css-tricks.com/almanac/properties/s/shape-outside)
* [**speak**](https://css-tricks.com/almanac/properties/s/speak)
* [**stroke**](https://css-tricks.com/almanac/properties/s/stroke)
* [**stroke-dasharray**](https://css-tricks.com/almanac/properties/s/stroke-dasharray)
* [**stroke-dashoffset**](https://css-tricks.com/almanac/properties/s/stroke-dashoffset)
* [**stroke-linecap**](https://css-tricks.com/almanac/properties/s/stroke-linecap)
* [**stroke-linejoin**](https://css-tricks.com/almanac/properties/s/stroke-linejoin)
* [**stroke-width**](https://css-tricks.com/almanac/properties/s/stroke-width)

### T Selector

* [**:target**](https://css-tricks.com/almanac/selectors/t/target)
* [**Type**](https://css-tricks.com/almanac/selectors/t/type)  ****⭐**03**

### T Properties

* [**tab-size**](https://css-tricks.com/almanac/properties/t/tab-size)
* [**table-layout**](https://css-tricks.com/almanac/properties/t/table-layout)
* [**text-align**](https://css-tricks.com/almanac/properties/t/text-align)
* [**text-align-last**](https://css-tricks.com/almanac/properties/t/text-align-last)
* [**text-decoration**](https://css-tricks.com/almanac/properties/t/text-decoration)
* [**text-decoration-color**](https://css-tricks.com/almanac/properties/t/text-decoration-color)
* [**text-decoration-line**](https://css-tricks.com/almanac/properties/t/text-decoration-line)
* [**text-decoration-skip**](https://css-tricks.com/almanac/properties/t/text-decoration-skip)
* [**text-decoration-skip-ink**](https://css-tricks.com/almanac/properties/t/text-decoration-skip-ink)
* [**text-decoration-style**](https://css-tricks.com/almanac/properties/t/text-decoration-style)
* [**text-indent**](https://css-tricks.com/almanac/properties/t/text-indent)
* [**text-justify**](https://css-tricks.com/almanac/properties/t/text-justify)
* [**text-overflow**](https://css-tricks.com/almanac/properties/t/text-overflow)
* [**text-rendering**](https://css-tricks.com/almanac/properties/t/text-rendering)
* [**text-shadow**](https://css-tricks.com/almanac/properties/t/text-shadow)
* [**text-stroke**](https://css-tricks.com/almanac/properties/t/text-stroke)
* [**text-transform**](https://css-tricks.com/almanac/properties/t/text-transform)
* [**text-underline-position**](https://css-tricks.com/almanac/properties/t/text-underline-position)
* [**top / bottom / left / right**](https://css-tricks.com/almanac/properties/t/top-right-bottom-left)
* [**touch-action**](https://css-tricks.com/almanac/properties/t/touch-action)
* [**transform**](https://css-tricks.com/almanac/properties/t/transform)
* [**transform-origin**](https://css-tricks.com/almanac/properties/t/transform-origin)
* [**transform-style**](https://css-tricks.com/almanac/properties/t/transform-style)
* [**transition**](https://css-tricks.com/almanac/properties/t/transition)
* [**transition-delay**](https://css-tricks.com/almanac/properties/t/transition-delay)
* [**transition-duration**](https://css-tricks.com/almanac/properties/t/transition-duration)
* [**transition-property**](https://css-tricks.com/almanac/properties/t/transition-property)
* [**transition-timing-function**](https://css-tricks.com/almanac/properties/t/transition-timing-function)

### U Selector

* [**:user-invalid**](https://css-tricks.com/almanac/selectors/u/user-invalid)
* [**Universal**](https://css-tricks.com/almanac/selectors/u/universal)

### U Properties

* [**unicode-bidi**](https://css-tricks.com/almanac/properties/u/unicode-bidi)
* [**unicode-range**](https://css-tricks.com/almanac/properties/u/unicode-range)
* [**user-select**](https://css-tricks.com/almanac/properties/u/user-select)

### V Selector

* [**:valid**](https://css-tricks.com/almanac/selectors/v/valid)
* [**:visited**](https://css-tricks.com/almanac/selectors/v/visited)

### V Properties

* [**vertical-align**](https://css-tricks.com/almanac/properties/v/vertical-align)
* [**visibility**](https://css-tricks.com/almanac/properties/v/visibility)

### W Properties \(No Selector\)

* [**white-space**](https://css-tricks.com/almanac/properties/w/whitespace)
* [**widows**](https://css-tricks.com/almanac/properties/w/widows)
* [**width**](https://css-tricks.com/almanac/properties/w/width)
* [**will-change**](https://css-tricks.com/almanac/properties/w/will-change)
* [**word-break**](https://css-tricks.com/almanac/properties/w/word-break)
* [**word-spacing**](https://css-tricks.com/almanac/properties/w/word-spacing)
* [**writing-mode**](https://css-tricks.com/almanac/properties/w/writing-mode)

### Z Properties \(No Selector\)

* [**z-index**](https://css-tricks.com/almanac/properties/z/z-index)
* [**zoom**](https://css-tricks.com/almanac/properties/z/zoom)

**Identifers List**

