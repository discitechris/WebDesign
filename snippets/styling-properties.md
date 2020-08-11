# Styling Properties

## border-radius

You can give any element “rounded corners” by applying a border-radius through CSS. You’ll only notice if there is a color change involved. For instance, if the element has a background-color or border that is different than the element it’s over.

It’s really not necesssary anymore, but for the absolute best possible browser support, you could prefix with **`-webkit-`** and **`-moz-`**

```css
.round {
  /* Safari 3-4, iOS 1-3.2, Android 1.6- */
  -webkit-border-radius: 12px; 

  /* Firefox 1-3.6 */
  -moz-border-radius: 12px; 

  /* Opera 10.5, IE 9, Safari 5, Chrome, Firefox 4, iOS 4, Android 2.1+ */
  /* always keep the non-prefixed last */
  border-radius: 12px; 
  border-radius: 5px 10px 15px 20px; /* top left, top right, bottom right, bottom left */
  border-radius: 50%; /* circle */
}
```

For more info [**border-radius**](https://css-tricks.com/almanac/properties/b/border-radius/)\*\*\*\*

## box-shadow

Used in casting shadows \(often called “Drop Shadows”, like in Photoshop\) from elements.

You can apply multiple box-shadows by comma separating

```css
.shadow {
  -webkit-box-shadow: 3px 3px 5px 6px #ccc;  /* Safari 3-4, iOS 4.0.2 - 4.2, Android 2.3+ */
  -moz-box-shadow:    3px 3px 5px 6px #ccc;  /* Firefox 3.5 - 3.6 */
  box-shadow:         3px 3px 5px 6px #ccc;  /* Opera 10.5, IE 9, Firefox 4+, Chrome 6+, iOS 5 */
  box-shadow: [horizontal (x) offset] [vertical (y) offset] [blur radius] [optional spread radius] [color];
}
/* inner Shadow */
.shadow {
   -moz-box-shadow:    inset 0 0 10px #000000;
   -webkit-box-shadow: inset 0 0 10px #000000;
   box-shadow:         inset 0 0 10px #000000;
}
.one-edge-shadow {
    /* One-Side Only */
  box-shadow: 0 8px 6px -6px black;
}
{
    /* Multiple box-shadows */
box-shadow: 
  inset 5px 5px 10px #000000, 
  inset -5px -5px 10px blue;
}
```

Values:

* **horizontal offset** \(required\) of the shadow, positive means the shadow will be on the right of the box, a negative offset will put the shadow on the left of the box.
* **vertical offset** \(required\) of the shadow, a negative one means the box-shadow will be above the box, a positive one means the shadow will be below the box.
* **blur radius** \(required\), if set to 0 the shadow will be sharp, the higher the number, the more blurred it will be, and the further out the shadow will extend. For instance a shadow with 5px of horizontal offset that also has a 5px blur radius will be 10px of total shadow.
* **spread radius** \(optional\), positive values increase the size of the shadow, negative values decrease the size. Default is 0 \(the shadow is same size as blur\).
* **Color** \(required\) – takes any color value, like hex, named, rgba or hsla. If the color value is omitted, box shadows are drawn in the foreground color \(text color\). But be aware, older WebKit browsers \(pre Chrome 20 and Safari 6\) ignore the rule when color is omitted.

For more info [**box-shadows**](https://css-tricks.com/almanac/properties/b/box-shadow/)\*\*\*\*

## background

property in CSS allows you to control the background of any element \(what paints underneath the content in that element\). It is a shorthand property

```css
body {
  background:
     url(sweettexture.jpg)    /* image */
     top center / 200px 200px /* position / size */
     no-repeat                /* repeat */
     fixed                    /* attachment */
     padding-box              /* origin */
     content-box              /* clip */
     red;                     /* color */
}
```

Values:

You can use any combination of these properties that you like, in almost any order

multiple backgrounds, which layer over the top of each other. Any property related to backgrounds can take a comma separated list

### background-image

```css
body {
  background: linear-gradient(black, white);
}
body {
  background:
    url(logo.png) bottom center no-repeat,
    url(background-pattern.png) repeat;
}
html {
  background: url(greatimage.jpg), url(wonderfulimage.jpg);
  background-size: 300px 100px, cover;
  /* first image is 300x100, second image covers the whole area */
}
```

### background-position

allows you to move a background image \(or gradient\) around within its container.

```css
html {
  background-position: 100px 5px; 
}
```

Values:

* Length values \(e.g. **100px 5px**\)
* Percentages \(e.g. **100% 5%**\)
* Keywords \(e.g. **top right**\)

### background-size

most useful — and most complex — of the background properties. There are many variations and different syntaxes you can use for this property, all of which have different use cases.

```css
html {
  background: url(greatimage.jpg);
  background-size: 300px 100px; 
}
```

Values:

* keyword syntax -  **`cover`** & **`contain`** default keyword — **`auto`**
* one-value syntax - length values
* the two-value syntax - length values
* multiple background syntax.

### background-repeat

```css
html {
  background-image: url(logo.png);
  background-repeat: repeat-x || repeat || repeat-y || no repeat || space || round; 
}
```

### background-attachment

specifies how to move the background relative to the **viewport**.

```css
  background-image: url(logo.png);
  background-attachment: scroll || fixed || local;
```

Values:

* **`scroll`** is the default value. It scrolls with the main view, but stays fixed inside the local view.
* **`fixed`** stays fixed no matter what. It’s kind of like a physical window: moving around the window changes your perspective, but it doesn’t change where things are outside of the window.
* **`local`** was invented because the default scroll value acts like a fixed background. It scrolls both with the main view and the local view. There are some pretty cool things you can do with it.

### background-origin

defines where to paint the background: across the whole element, inside the border, or inside the padding.

Values: **`border-box`**, **`padding-box`**, **`content-box`** and **`inherit`**. is similar to background-clip, except it resizes the background rather than clipping it.

### background-clip

lets you control how far a background image or color extends beyond an element’s padding or content.

```css
.frame {
  background-clip: padding-box;
}
```

Values: **`border-box`**, **`padding-box`**, **`content-box`** and **`inherit`**.

### background-color

applies solid colors as background on an element.

```css
html {
  background-color: #82a43a; 
}
```

## transition

shorthand property used to represent up to four transition-related longhand properties

transition properties allow elements to change values over a specified duration, animating the property changes, rather than having them occur immediately.

You may **comma separate** value sets to do different transitions on different properties:

```css
.example {
    transition: [transition-property] [transition-duration] [transition-timing-function] [transition-delay];
}

div {
  transition: background-color 0.5s ease;
  background-color: red;
}
div:hover {
  background-color: green;
}
div {
  transition: background 0.2s ease,
              padding 0.8s linear;
}
```

### transition-duration

Used to define the duration of a specified transition. That is, the length of time it will take for the targeted element to transition between two defined states.

Values:

* A valid time value \(defined in **seconds** or **milliseconds**\)
* A **comma-separated** list of time values, for transitioning multiple properties on a single element

### transition-timing-function

is used to define a function that describes how a transition will proceed over its duration, allowing a transition to change speed during its course.

Values:

* predefined keyword value - 
  * **`ease`** 
  * **`linear`** 
  * **`ease-in`** 
  * **`ease-out`** 
  * **`ease-in-out`** 
  * **`step-start`**
  * **`step-end`**
* a stepping function
  * a positive integer and an optional value of either start or end. If no second parameter is included, it will default to end. **`steps(4, start)`** 
* **cubic Bézier** curve.

### transition-delay

is used to define a length of time to delay the start of a transition.

A common use case is stagging transitions:

Values:

* A valid time value defined in seconds or milliseconds e.g. **1.3s** or **125ms**
* A **comma-separated** list of time values, for defining separate delay values on multiple transitions for a single element e.g. **1s** background-color, **350ms** transform



### transform

allows you to visually manipulate an element by skewing, rotating, translating, or scaling

Even with a declared height and width, this element will now be scaled to twenty times its original size:

```css
.element {
  width: 20px;
  height: 20px;
  transform: scale(20);
}
```

Giving this function two values will stretch it horizontally by the first and vertically by the second.

```css
.element {
  transform: scale(2, .5);
}
/* can be more specific using shorthand functions */
.element {
  transform: scaleX(2);
  transform: scaleY(.5);
}
```

Values:

* **`scale()`** : Affects the size of the element.
  * This also applies to the **font-size**, **padding**, **height**, and **width** of an element, too.
  * It’s also a a shorthand function for the **`scaleX`** and **`scaleY`** functions.
* **`skewX()`** and **`skewY()`**: Tilts an element to the left or right, like turning a rectangle into a parallelogram.
  * **`skew()`** is a shorthand that combines **`skewX()`** and **`skewY`** by accepting both values.
* **`translate()`**: Moves an element sideways or up and down.
* **`rotate()`**: Rotates the element clockwise from its current position.
* **`matrix()`**: A function that is probably not intended to be written by hand, but combines all transforms into one.
* **`perspective()`**: Doesn’t affect the element itself, but affects the transforms of descendent elements’ 3D transforms, allowing them all to have a consistent depth perspective.

With a space-separated list you can add multiple values to the transform property:

```css
.element {
  width: 20px;
  height: 20px;
  transform: scale(20) skew(-20deg);
}
```

Most of the above properties have 3D versions of them.

```css
.element {
transform : translate3d(x, y, z)
translateZ(z)
scale3d(sx, sy, sz)
scaleZ(sz)
}
```

### transform-origin

The transform-origin property is used in conjunction with CSS transforms, letting you change the point of origin of a transform.

the transform-origin property can take up to two space-separated keyword or length values for a 2D transform and up to three values for a 3D transform.

By **default**, the origin of a transform is “**50% 50%**”, which is exactly in the **center** of any given element. for example: Changing the origin to “top left” causes the element to use the top left corner of the element as a rotation point.

```css
.box {
  transform: rotate(360deg);
  transform-origin: top left;
}
```

Values:

* lengths
* percentages
* keywords : **top**, **left**, **right**, **bottom**, and **center**.

## shape-outside

Controls how content will wrap around a floated element’s bounding-box. Typically this is so that text can reflow over a shape such as a circle, ellipse or a polygon

It’s _important to note that this property will only work on floated elements for now_, although this is likely to change in the future. The shape-outside property can also be manipulated with transitions or animations.

Values:

* **`circle()`** : for making circular shapes.
* **`ellipse()`** : for making elliptical shapes.
* **`inset()`** : for making rectangular shapes.
* **`polygon()`** : for creating any shape with 3 or more vertices.
* **`url()`** : identifies which image should be used to wrap text around.
* **`initial`** : the float area is unaffected.
* **`inherit`** : inherits shape-outside value from parent.

The following values identify which reference of the box model should be used for positioning the shape within:

* **`margin-box`**
* **`padding-box`**
* **`border-box`** These values should be appended to the end, for instance: **`shape-outside: circle(50% at 0 0) padding-box`**.

  By **default** the margin-box reference will be used.

## clip-path

Allows you to specify a specific region of an element to display, rather than showing the complete area.

The most common use case would be an image, but it’s not limited to that. You could just as easily apply **`clip-path`** to a paragraph tag and only a portion of the text.

```css
.clip-me {  
  clip-path: inset(10px 20px 30px 40px); /* or "none" */
  /* values are from-top, from-right, from-bottom, from-left */
}
/* Other possible values */
.clip-me { 

  /* referencing path from an inline SVG <clipPath> */
  clip-path: url(#c1); 

  /* referencing path from external SVG */
  clip-path: url(path.svg#c1);

  /* polygon */
  clip-path: polygon(5% 5%, 100% 0%, 100% 75%, 75% 75%, 75% 100%, 50% 75%, 0% 75%);

  /* circle */
  clip-path: circle(30px at 35px 35px);

  /* ellipse */
  clip-path: ellipse(65px 30px at 125px 40px);

  /* inset-rectangle() may replace inset() ? */
  /* rectangle() coming in SVG 2 */

  /* rounded corners... not sure if a thing anymore */
  clip-path: inset(10% 10% 10% 10% round 20%, 20%);

}
```

Example SVG clip path:

```markup
<clipPath id="clipping">
  <circle cx="150" cy="150" r="50" />
  <rect x="150" y="150" width="100" height="100" />
</clipPath>
```



## mask-image

A mask in CSS hides part of the element is applied to.

```css
.el {
  mask-image: url(star.svg);
}
```

For more info - [**mask-image**](https://css-tricks.com/almanac/properties/m/mask-image/)

## perspective

gives an element a 3D-space by affecting the distance between the Z plane and the user.

The strength of the effect is determined by the value. The smaller the value, the closer you get from the Z plane and the more impressive the visual effect. The greater the value, the more subtle will be the effect.

Important: Please note the **`perspective`** property doesn’t affect how the element is rendered; it simply enables a 3D-space for children elements. This is the main difference between the **`transform: perspective()`** function and the **`perspective`** property. The first gives element depth while the later creates a 3D-space shared by all its transformed children

```css
/**
 * Syntax
 * perspective: none | &lt;length&gt; 
 */

.parent {
    perspective: 1000px;
}

.child {
    transform: rotateY(50deg);
}
```

For more info - [**perspective**](https://css-tricks.com/almanac/properties/p/perspective/)

The **`perspective-origin`** property determines the origin for the **`perspective`** property. Think of it as the vanishing point of the current 3D-space.

Note as for the **`perspective`** property, **`perspective-origin`** has to be defined on the parent element in order to give the transformed children depth.

The **`perspective-origin`** property doesn’t do anything by itself. It has to be defined on an element along with **`perspective`**.

## object-fit

defines how an element responds to the height and width of its content box. It’s intended for images, videos and other embeddable media formats in conjunction with the **`object-position`** property. Used by itself, **`object-fit`** lets us crop an inline image by giving us fine-grained control over how it squishes and stretches inside its box.

Values:

* **`fill`** : this is the default value which stretches the image to fit the content box, regardless of its aspect-ratio.
* **`contain`** : increases or decreases the size of the image to fill the box whilst preserving its aspect-ratio.
* **`cover`** : the image will fill the height and width of its box, once again maintaining its aspect ratio but often cropping the image in the process.
* **`none`** : image will ignore the height and width of the parent and retain its original size.
* **`scale-down`** : the image will compare the difference between **`none`** and **`contain`** in order to find the smallest concrete object size.

```css
img {
  height: 120px;
}

.cover {
  width: 260px;
  object-fit: cover;
}
```

The **`object-position`** property is used in conjunction with **`object-fit`** property and defines how an element such as a video or image is positioned with X/Y coordinates inside its content-box. This property takes two numerical values, such as 0 10% or 0 10px. In those examples, the first number indicates that the image should be placed at the left of the content box \(0\), the second that it should be positioned 10% or 10px from the top. It is also possible to use negative values.

The **default** value for **`object-position`** is **`50% 50%`** when using the **`object-fit`** property on an image, so that by default all images are positioned in the center of their content box, like so:

```css
img {
  object-fit: none;
  object-position: 50% 50%; /* default value: image is centered*/
  object-position: 0 0; /* positioned top left of the content box */
}
```

## visibility

has two different functions. It hides rows and columns of a table, and it also hides an element _without changing the layout_.

Values:

* visible
* hidden
* collapse
* inherit

```css
p {
  visibility: hidden;
}
tr {
  /* Dont use this ever */
  visibility: collapse;
}
```

## cursor

controls what the mouse cursor will look like when it is located over the element in which this property is set. Obviously, it only is relevant in browsers/operating systems in which there is a mouse and cursor. They are used essentially for UX – as they convey the idea of certain functionality. So try not to break that affordance =\).

There are a bunch of them:

```css
.auto            { cursor: auto; }
.default         { cursor: default; }
.none            { cursor: none; }
.context-menu    { cursor: context-menu; }
.help            { cursor: help; }
.pointer         { cursor: pointer; }
.progress        { cursor: progress; }
.wait            { cursor: wait; }
.cell            { cursor: cell; }
.crosshair       { cursor: crosshair; }
.text            { cursor: text; }
.vertical-text   { cursor: vertical-text; }
.alias           { cursor: alias; }
.copy            { cursor: copy; }
.move            { cursor: move; }
.no-drop         { cursor: no-drop; }
.not-allowed     { cursor: not-allowed; }
.all-scroll      { cursor: all-scroll; }
.col-resize      { cursor: col-resize; }
.row-resize      { cursor: row-resize; }
.n-resize        { cursor: n-resize; }
.e-resize        { cursor: e-resize; }
.s-resize        { cursor: s-resize; }
.w-resize        { cursor: w-resize; }
.ns-resize       { cursor: ns-resize; }
.ew-resize       { cursor: ew-resize; }
.ne-resize       { cursor: ne-resize; }
.nw-resize       { cursor: nw-resize; }
.se-resize       { cursor: se-resize; }
.sw-resize       { cursor: sw-resize; }
.nesw-resize     { cursor: nesw-resize; }
.nwse-resize     { cursor: nwse-resize; }
```

You can also have the cursor be an image:

```css
.custom {
  cursor: url(images/my-cursor.png), auto;
}
```

Some WebKit only cursors:

```css
-webkit-zoom-in
-webkit-zoom-out
-webkit-zoom-grab
-webkit-zoom-grabbing
```

## filter

CSS Filters are a powerful tool that authors can use to achieve varying visual effects \(sort of like Photoshop filters for the browser\). The CSS filter property provides access to effects like blur or color shifting on an element’s rendering before the element is displayed. Filters are commonly used to adjust the rendering of an image, a background, or a border.

```css
.filter-me {
  /* The syntax is: */
  filter: drop-shadow() | none
}
  /*  single filter  */
  .blur-me {
  filter: blur(20px);
}
/* multiple filters */
  .do-more-things {
  filter: blur(20px) grayscale(20%);
}
```

Values:

* **`blur()`**
* **`brightness()`**
* **`contrast()`**
* **`drop-shadow()`**
* **`grayscale()`**
* **`hue-rotate()`**
* **`invert()`**
* **`opacity()`**
* **`saturate()`**
* **`sepia()`**
* **`url()`** – for applying SVG filters
* **`custom()`** – “coming soon”

