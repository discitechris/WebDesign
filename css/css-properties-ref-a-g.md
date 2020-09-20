# CSS Properties Ref \(A - G\)

## ⮜⮜⮜⮜⮜ A SELECTOR ⮞⮞⮞⮞⮞

### [**::before / ::after**](https://css-tricks.com/almanac/selectors/a/after-and-before/) ****

* **DEFINITION :** allows you to insert content onto a page without it needing to be in the HTML.
* **NECESSARY PROPERTY :** [content](https://css-tricks.com/almanac/properties/c/content)

### [**:active**](https://css-tricks.com/almanac/selectors/a/active/)

* **DEFINITION :** changes the appearance of a link while it is being activated \(being clicked on or otherwise activated\).
* **PERKS:** can be applied to any element.

## ⭪⭪⭪⭪⭪⭪⭪  A PROPERTIES ⭬⭬⭬⭬⭬⭬⭬

### [**animation**](https://css-tricks.com/almanac/properties/a/animation)

*  **DEFINITION:**  used to animate many other CSS properties such as **`color`**, **`background-color`**, **`height`**, or **`width`**. Each animation needs to be defined with the **`@keyframes`** [at-rule](https://css-tricks.com/at-rule-css/) which is then called with the **`animation`** property,
* comma-separate the values to declare **multiple animations**
* **NECESSARY COMPANIONS:  `@keyframes`**
* **SUB-PROPERTIES:** 
  * **`animation-name`:** declares the name of the **`@keyframes`** at-rule to manipulate.
  * **`animation-duration`:** the length of time it takes for an animation to complete one cycle.
    * **`Xs (4s)`** or **`Xms (3.5ms)`**
  * **`animation-timing-function`:** establishes preset acceleration curves such as **`ease`** or **`linear`**.
    * **`ease`**, **`ease-out`**, **`ease-in`**, **`ease-in-out`**, **`linear`**, **`cubic-bezier(x1, y1, x2, y2)`** \(e.g. **`cubic-bezier(0.5, 0.2, 0.3, 1.0)`**\)
  *  **`animation-delay`**: the time between the element being loaded and the start of the animation sequence 
    * **`Xs (4s) or Xms (3.5ms)`**
  * **`animation-direction`**: sets the direction of the animation after the cycle. Its default resets on each cycle.
    * **`normal`**, **`alternate`**
  * **`animation-iteration-count`:** the number of times the animation should be performed.
    * **`X (5)` , `infinite`**
  * **`animation-fill-mode` :** sets which values are applied before/after the animation.
    * For example, you can set the last state of the animation to remain on screen, or you can set it to switch back to before when the animation began.
    * **`forwards`**, **`backwards`**, **`both`**, **`none`**
  * **`animation-play-state`:** pause/play the animation.
    * **`paused`**, **`running`**

## ⭪⭪⭪⭪⭪⭪⭪  B PROPERTIES ⭬⭬⭬⭬⭬⭬⭬

### [**backdrop-filter**](https://css-tricks.com/almanac/properties/b/backdrop-filter)

*  **DEFINITION:** used to apply [**`filter`**](css-properties-ref-a-g.md#filter) effects \(**`grayscale`**, **`contrast`**, **`blur`**, etc\) to the background/backdrop of an element. 
  *  can apply multiple **`<filter-function>`**s to a backdrop example.**`backdrop-filter: grayscale(0.5) opacity(0.8)`**
* **SUB-PROPERTIES:** 
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
  * **`url()`** – \(for applying SVG filters\)

### [**backface-visibility**](https://css-tricks.com/almanac/properties/b/backface-visibility)

* **DEFINITION:** relates to 3D transforms. With 3D transforms, you can manage to rotate an element so what we think of as the **“front”** of an element no longer faces the screen. eg \(mirrored text\)
* **SUB-PROPERTIES:**
  * **`visible`** \(**default**\) – the element will always be visible even when not facing the screen.
  * **`hidden`** – the element is _not_ visible when not facing the screen.
  * **`inherit`** – the property will gets its value from the its parent element.
  * **`initial`**– sets the property to its default, which is **`visible`**.

### [**background-attachment**](https://css-tricks.com/almanac/properties/b/background-attachment)

* **DEFINITION:** specifies how to move the background relative to the viewport. background of any element \(what paints underneath the content in that element\).
* **SUB-PROPERTIES:**   three values: **`scroll`**, **`fixed`**, and **`local`**. 

### [**background-blend-mode**](https://css-tricks.com/almanac/properties/b/background-blend-mode)

*  **DEFINITION:** defines how an element’s **`background-image`** should blend with its **`background-color`**
* **NECESSARY COMPANIONS:  `background-image`, `background-color`**
* **SUB-PROPERTIES:** 
  * **`initial`**: the default value with no blending.
  * **`inherit`**: inherits the blend mode of the parent element.
  * **`<blend-mode>`**: a value that will change the **background-image** depending on its **background-color**.
    *  **`normal`**: the **background-color** will not bleed through the **background-image**. 
    * **`multiply`**: the **background-image** and **background-color** are multiplied and typically this leads to a darker image than before.
    *  **`screen`**: both **image** and **color** is inverted, multiplied and then inverted again.
    *  **`overlay`**: the **background-color** is mixed with the **background-image** to reflect the lightness or darkness of the backdrop.
    *  **`darken`**: if the **background-image** is darker than the **background-color** then the image is replaced, otherwise it is left as it was.
    *  **`lighten`**: if the background-image is lighter than the background-color then the image is replaced, otherwise it is left as it was.
    *  **`color-dodge`**: the background-color is divided by the inverse of the background-image. This is very similar to the screen blend mode.
    *  **`color-burn`**: the background-color is inverted, divided by the background-image and inverted again. This is similar to multiply.
    *  **`hard-light`**: if the background-image is lighter than the background-color then the result is multiply or if it is lighter then the result is screen.
    *  **`soft-light`**: the final result is similar to **`hard-light`** but softer 
    *  **`difference`**: the result by subtracting the darker color of the **background-image** and the **background-color** from the lightest one. Often the image will have a very high contrast.
    *  **`exclusion`**: the result is very similar to **`difference`** yet with a little lower contrast.
    * **`hue`**: the result is the hue of the background-image combined with the luminosity and saturation of the background-color.
    *  **`saturation`**: keeps the saturation of the background-image whilst mixing the hue and luminosity of the background-color.
    *  **`color`**: keeps hue and saturation of background-image and the luminosity of the background-color. 
    *  **`luminosity`**: luminosity of the top color is preserved whilst using the saturation and hue of the background-color.

### [**background-clip**](https://css-tricks.com/almanac/properties/b/background-clip)

* **DEFINITION:** lets you control how far a **`background-image`** or **`background-color`** extends beyond an element’s padding or content.
* **NECESSARY COMPANIONS:  `background-image`  OR `background-color`**
* **SUB-PROPERTIES:**
  * **`border-box`** \(**default**\)  : This allows the background to extend all the way to the outside edge of the element’s border.
  * **`padding-box`** clips the background at the outside edge of the element’s padding and does not let it extend into the border.
  * **`content-box`**clips the background at the edge of the content box.
  * **`inherit`** applies the **`background-clip`** setting of the parent to the selected element.

### [**background-color**](https://css-tricks.com/almanac/properties/b/background-color)

* **DEFINITION:** applies solid colors as background on an element.
* **SUB-PROPERTIES:**  color is to use HEX, RGB, RGBa, HSL, or HSLa

### [**background-image**](https://css-tricks.com/almanac/properties/b/background-image)

* **DEFINITION:** applies a graphic \(e.g. PNG, SVG, JPG, GIF, WEBP\) or gradient to the background of an element.
* There are two different types of images you can include with CSS: regular images and gradients.
* **SUB-PROPERTIES:** regular images \(**url**\) and gradients \(**linear-gradient**\) etc



### [**background-origin**](https://css-tricks.com/almanac/properties/b/background-origin)

* **DEFINITION:** defines where to paint the background: across the whole **element**, inside the **border**, or inside the **padding**
*  **`background-origin`** is similar to **`background-clip`**, except it ****_**resizes**_ ****the background **rather** **than clipping it.**
*  **`background-size: cover`** and **`background-repeat: no-repeat`** applied. If that wasn’t the case, the image would repeat underneath the **border** or **padding**.
* **SUB-PROPERTIES:**  four values: **`border-box`**, **`padding-box`**, **`content-box`** and **`inherit`**

### [**background-position**](https://css-tricks.com/almanac/properties/b/background-position)

* **DEFINITION:** allows you to move a **background image \(or gradient\)** around within its container.
* **SUB-PROPERTIES:** 
  * Length values \(e.g. `100px 5px`\) **default \(0,0\)**
  * Percentages \(e.g. `100% 5%`\)
  * Keywords \(e.g. `top right`\)
  * recommended format : **`background-position: right 45px bottom 20px;`**

### [**background-repeat**](https://css-tricks.com/almanac/properties/b/background-repeat)

* **DEFINITION:**  If a **`background-image`** property is specified, the **`background-repeat`** property in CSS defines if \(and how\) it will repeat. 
* **SUB-PROPERTIES:**
  * **`repeat`**: tile the image in both directions. This is the default value.
  * **`repeat-x`**: tile the image horizontally
  * **`repeat-y`**: tile the image vertically
  * **`no-repeat`**: don’t tile, just show the image once
  * **`space`**: tile the image in both directions. Never crop the image unless a single image is too large to fit. If multiple images can fit, space them out evenly images always touching the edges.
  * **`round`**: tile the image in both directions. Never crop the image unless a single image is too large to fit. If multiple images can fit with leftover space, squish them or stretch them to fill the space. If it’s less than half one image width left, stretch, if it’s more, stretch.
  * the **two value syntax \(**horizontal vertical**\) : `background-repeat: repeat space`**

### [**background-size**](https://css-tricks.com/almanac/properties/b/background-size)

* **DEFINITION:** one of the most useful — and most complex — of the background properties.
* There are many variations and different syntaxes you can use for this property, all of which have different use cases
* **SUB-PROPERTIES:** 
  * **keywords** : you can use **`cover`**\(covers the entire container\)  and **`contain`** \(show the whole image as it is \)**,**  **default** value \(**`auto`**\) \(actual size of the image and the aspect ratio.\)
  *  **one value** : \(e.g. **`background-size: 400px`**\) it counts for the **width**, and the **height is set to `auto`**. 
  * **two values**: the first sets the background image’s **width** and the second sets the **height.**
  *  _**combine**_ ****any of the **above methods** and apply them to **multiple images,** 

### [**border-collapse**](https://css-tricks.com/almanac/properties/b/border-collapse) **\(related table\)**

### [**border-image**](https://css-tricks.com/almanac/properties/b/border-image)

* **DEFINITION:**  lets you use an image or CSS gradient as the border of an element. **`border-image: url(border.png) 25 25 round;`**

### [**border-radius**](https://css-tricks.com/almanac/properties/b/border-radius)

* **DEFINITION:**  can give any element “rounded corners” by applying a **`border-radius`** through CSS. You’ll only notice if there is a color change involved.
*  Sometimes you can see a **`background-color`** “leak” outside of a border when **`border-radius`** is present. To prevent this you use **`background-clip`**
* **SUB-PROPERTIES:** 
  * If **one** value is set, this radius applies to **all 4 corners**.
  * If **two** values are set, the **first** applies to `top-left` and **`bottom-right`** corner, the **second** applies to **`top-right`** and **`bottom-left`** corner.
  * **Four** values apply to the **`top-left`**, **`top-right`**, **`bottom-right`**, **`bottom-left`** corner in that order.
  * **Three** values: The second value applies to **`top-right`** and also **`bottom-left`**.

### [**border-spacing**](https://css-tricks.com/almanac/properties/b/border-spacing) **\(related table\)**

### [**box-decoration-break**](https://css-tricks.com/almanac/properties/b/box-decoration-break)

* **DEFINITION:**  lets you control how box decorations are drawn across the fragments of a “broken” element. An element can break into fragments at the end of a line, over columns, or at page breaks.
*  **`box-decoration-break`** are: **`background`** \(and its sub-properties\), **`border`**, **`border-radius`**, **`border-image`**, **`box-shadow`**, **`margin`**, and **`padding`**.
* **SUB-PROPERTIES:**
  * **`slice`**: the initial value. Box decorations apply to the element as a whole and break at the edges of the element fragments.
  * **`clone`**: decorations apply to each fragment of the element as if the fragments were unbroken, individual elements. Borders wrap the four edges of each fragment of the element, and backgrounds are redrawn in full for each fragment.

### [**box-shadow**](https://css-tricks.com/almanac/properties/b/box-shadow)

* **DEFINITION:**  Used in casting shadows \(often called “Drop Shadows”, like in Photoshop\) from elements.
* **SUB-PROPERTIES:`box-shadow: [horizontal offset] [vertical offset] [blur radius] [optional spread radius] [color];`**
* **`box-shadow: 3px 3px 5px 6px #ccc;`**

  * **The horizontal offset** \(required\) of the shadow, positive means the shadow will be on the right of the box, a negative offset will put the shadow on the left of the box.
  * **The vertical offset** \(required\) of the shadow, a negative one means the box-shadow will be above the box, a positive one means the shadow will be below the box.
  * **The blur radius** \(required\), if set to 0 the shadow will be sharp, the higher the number, the more blurred it will be, and the further out the shadow will extend. For instance a shadow with 5px of horizontal offset that also has a 5px blur radius will be 10px of total shadow.
  * **The spread radius** \(**optional**\), positive values increase the size of the shadow, negative values decrease the size. Default is 0 \(the shadow is same size as blur\).
  * **Color** \(required\) – takes any color value, like hex, named, rgba or hsla. If the color value is omitted, box shadows are drawn in the foreground color \(text **`color`**\). 

### [**box-sizing**](https://css-tricks.com/almanac/properties/b/box-sizing)

*  **DEFINITION:**  controls how the [box model](https://css-tricks.com/the-css-box-model/) is handled for the element it applies to.
*  One of the more **common ways to use** it is to **apply it to all elements on the page, pseudo elements included** This is often called **“universal box-sizing”**, and it’s a good way to work!  The \(literal\) **`width`** you set is the width you get, without having to perform mental math and manage the complexity that comes from widths that come from multiple properties. 
* **SUB-PROPERTIES:** 

  * **`content-box`**: the **default**. Width and height values apply to the element’s content only. The padding and border are added to the outside of the box.
  * **`padding-box`**: Width and height values apply to the element’s content and its padding. The border is added to the outside of the box.
  * **`border-box`**: Width and height values apply to the content, padding, and border.
  * **`inherit`**: inherits the box sizing of the parent element.

### [**break-inside**](https://css-tricks.com/almanac/properties/b/break-inside) **\(related table\)**

## ⮜⮜⮜⮜⮜ C SELECTOR ⮞⮞⮞⮞⮞

### [**:checked**](https://css-tricks.com/almanac/selectors/c/checked)

* **DEFINITION:**  selects elements when they are in the **selected** \(**toggled** or **checked**\) state. It is only associated with  \(**`<input>`**\) elements of type **radio** and **checkbox** . 
*  The **`:checked`** pseudo-class can be used with hidden inputs and their visible labels to build interactive widgets, such as image galleries.
* So when a **checkbox** is **checked**, and you are targeting the **label** immediately after it:

```css
input[type=checkbox] + label {
  color: #ccc;
  font-style: italic;
} 
input[type=checkbox]:checked + label {
  color: #f00;
  font-style: normal;
} 
```

## ⭪⭪⭪⭪⭪⭪⭪  C PROPERTIES ⭬⭬⭬⭬⭬⭬⭬

### [**caption-side**](https://css-tricks.com/almanac/properties/c/caption-side) **\(related table\)**

### [**clip-path**](https://css-tricks.com/almanac/properties/c/clip-path)

* **DEFINITION:**  allows you to specify a specific region of an element to display, rather than showing the complete area.
*  The most common use case would be an image, but it’s not limited to that. You could just as easily apply **`clip-path`** to a paragraph tag and only a portion of the text.
* **SUB-PROPERTIES: `clip-path: inset(10px 20px 30px 40px)`;** four values in **`inset()`**represent the **top/left** point and the **bottom/right** point, which forms the visible rectangle. Everything outside of that rectangle is hidden.
  * **`clip-path: inset(10px 20px 30px 40px)`**
  * **`clip-path: url(#c1);`  inline svg /external svg**
  * **`clip-path: polygon(5% 5%, 100% 0%, 100% 75%, 75% 75%, 75% 100%, 50% 75%, 0% 75%);`**
  * **`clip-path: circle(30px at 35px 35px);`**
  * **`clip-path: ellipse(65px 30px at 125px 40px);`**

```css
// svg clip-path
<clipPath id="clipping">
  <circle cx="150" cy="150" r="50" />
  <rect x="150" y="150" width="100" height="100" />
</clipPath>
```

### [**color**](https://css-tricks.com/almanac/properties/c/color)

### [**column-count**](https://css-tricks.com/almanac/properties/c/column-count) **\(related table\)**

### [**column-fill**](https://css-tricks.com/almanac/properties/c/column-fill) **\(related table\)**

### [**column-gap**](https://css-tricks.com/almanac/properties/c/column-gap)**\(related table\)**

### [**column-rule**](https://css-tricks.com/almanac/properties/c/column-rule) **\(related table\)**

### [**column-span**](https://css-tricks.com/almanac/properties/c/column-span) **\(related table\)**

### [**column-width**](https://css-tricks.com/almanac/properties/c/column-width) **\(related table\)**

### [**columns**](https://css-tricks.com/almanac/properties/c/columns) **\(related table\)**

### [**content**](https://css-tricks.com/almanac/properties/c/content)

### 

*  **DEFINITION:**  used in conjunction with the pseudo-elements `::before` and `::after`. It is used to literally insert content.
* **SUB-PROPERTIES:** There are four value types it can have.

  * **`String` :** It could also be an empty string,

* [**counter-increment**](https://css-tricks.com/almanac/properties/c/counter-increment)
* [**counter-reset**](https://css-tricks.com/almanac/properties/c/counter-reset)
* [**cursor**](https://css-tricks.com/almanac/properties/c/cursor)

## ⮜⮜⮜⮜⮜ D SELECTOR ⮞⮞⮞⮞⮞

* [**:default**](https://css-tricks.com/almanac/selectors/d/default)
* [**:dir\(\)**](https://css-tricks.com/almanac/selectors/d/dir)
* [**:disabled**](https://css-tricks.com/almanac/selectors/d/disabled)
* [**Descendant**](https://css-tricks.com/almanac/selectors/d/descendant) ****⭐ **04**

## ⭪⭪⭪⭪⭪⭪⭪  D PROPERTIES ⭬⭬⭬⭬⭬⭬⭬

* [**direction**](https://css-tricks.com/almanac/properties/d/direction)
* [**display**](https://css-tricks.com/almanac/properties/d/display)

## ⮜⮜⮜⮜⮜ E SELECTOR ⮞⮞⮞⮞⮞

* [**:empty**](https://css-tricks.com/almanac/selectors/e/empty)
* [**:enabled**](https://css-tricks.com/almanac/selectors/e/enabled)

## ⭪⭪⭪⭪⭪⭪⭪  E PROPERTIES ⭬⭬⭬⭬⭬⭬⭬

* [**empty-cells**](https://css-tricks.com/almanac/properties/e/empty-cells)

## ⮜⮜⮜⮜⮜ F SELECTOR ⮞⮞⮞⮞⮞

* [**::first-letter**](https://css-tricks.com/almanac/selectors/f/first-letter)
* [**::first-line**](https://css-tricks.com/almanac/selectors/f/first-line)
* [**:first-child**](https://css-tricks.com/almanac/selectors/f/first-child)
* [**:first-of-type**](https://css-tricks.com/almanac/selectors/f/first-of-type)
* [**:focus**](https://css-tricks.com/almanac/selectors/f/focus)
* [**:focus-visible**](https://css-tricks.com/almanac/selectors/f/focus-visible)
* [**:focus-within**](https://css-tricks.com/almanac/selectors/f/focus-within)

## ⭪⭪⭪⭪⭪⭪⭪  F PROPERTIES ⭬⭬⭬⭬⭬⭬⭬

* [**fill**](https://css-tricks.com/almanac/properties/f/fill)

### [**filter**](https://css-tricks.com/almanac/properties/f/filter)

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

## ⮜⮜⮜⮜⮜ G SELECTOR ⮞⮞⮞⮞⮞

* [**General sibling**](https://css-tricks.com/almanac/selectors/g/general-sibling)

## ⭪⭪⭪⭪⭪⭪⭪  G PROPERTIES ⭬⭬⭬⭬⭬⭬⭬

* [**grid-row / grid-column**](https://css-tricks.com/almanac/properties/g/grid-row-column)
* [**grid-template-columns / grid-template-rows**](https://css-tricks.com/almanac/properties/g/grid-rows-columns)

