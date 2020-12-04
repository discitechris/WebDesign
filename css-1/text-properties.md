# Text Properties

## color

Sets the color of a text

Values:

* Named colors: for example, **`“aqua”`**.
* Hex colors: for example, **\#00FFFF** or **\#0FF**.
* RGB and RGBa colors: for example, **rgb\(0, 255, 255\)** and **rgba\(0, 255, 255, .5\)**.
* HSL and HSLa colors: for example, **hsl\(180, 100%, 50%\)** and **hsla\(180, 100%, 50%, .5\)**.

## line-height

Defines the amount of space above and below **`inline`** elements. That is, elements that are set to display: **`inline`** or display: **`inline-block`**.

Values:

* **normal** 
* **none** 
* **number**
* **length**
* **percentage**

## letter-spacing

Property controls the amount of space between each letter in a given element or block of text.

Values:

* font-relative values \(**em**, **rem**\)
* parent-relative values \(**percentage**\)
* absolute values \(**px**\)
* **normal** resets to font's default

{% hint style="info" %}
font-relative values is recommended
{% endhint %}

\*\*\*\*

## **text-align**

Used for aligning the inner content of a block element.

**`text-align-last`** lets you control the alignment of the last \(or only\) line of text right before a forced line break — for example the end of a paragraph or the line right before a **`<br>`** tag.

Values:

* **left** – default value.
* **right**
* **center**
* **justify**

## text-decoration

adds an underline, overline, line-through, or a combination of lines to selected text.

Values:

* **none**
* **underline**
* **line-through**
* **overline**
* **inherit**

```css
p {
  text-decoration: overline underline line-through;
  /* or */
  text-decoration-line: underline;
  text-decoration-style: wavy;
  text-decoration-color: red;

  /* can be shortened to */
  text-decoration: underline wavy red;
}
```

The [**`text-decoration-color`**]() property sets the color of the underline, overline, or line-through on text with the text-decoration property applied. It can also set the underline color on links.

[**`text-decoration-color`**](https://css-tricks.com/almanac/properties/t/text-decoration-skip/) • [**`text-decoration-style`**](https://css-tricks.com/almanac/properties/t/text-decoration-style/)

## text-indent

Specifies how much horizontal space text should be moved before the beginning of the first line of the text content of an element.

Values:

* font-relative values \(**em**, **rem**\)
* parent-relative values \(**percentage**\)
* absolute values \(**px**\)
* **normal** resets to font's default

## text-transform

controls text case and capitalization.

Values:

* **lowercase**
* **UPPERCASE**
* **Capitalize**
* **none**
* **inherit**

## text-shadow

You can apply multiple text shadows by comma separating

```css
p { 
  text-shadow: 1px 1px 1px #000;
  text-shadow: [horizontal (x) offset] [vertical (y) offset] [blur radius] [color];
}
```

## text-overflow

deals with situations where text is clipped when it overflows the element’s box. It can be clipped \(i.e. cut off, hidden\), display an ellipsis \(‘…’, Unicode Range Value U+2026\) or display an author-defined string \(no current browser support for author-defined strings\).

```css
.ellipsis {
  text-overflow: ellipsis;

  /* Required for text-overflow to do anything */
  white-space: nowrap;
  overflow: hidden;
}
```

Note that **`text-overflow`** only occurs when the container’s **`overflow`** property has the value **`hidden`**, **`scroll`** or **`auto`** and **`white-space: nowrap;`**.

