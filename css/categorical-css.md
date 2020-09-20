# Categorical CSS

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

