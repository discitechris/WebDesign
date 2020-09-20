# Float

* Floated elements _**remain a part of the flow of the web page**_**.**
* This is distinctly different than page elements that use **absolute positioning.**
* If this **parent** element contained **nothing** but **floated elements**, the **height** of it would literally **collapse to nothing.**
  *  We fix it by clearing the float **after** the floated elements in the container but **before** the close of the container.

Values:

* **`none`**
* **`left`**
* **`right`**
* **`inherit`**

{% hint style="info" %}
**NOTE:**    An element that is floated is automatically **`display: block;`**
{% endhint %}

For more info about float[  👉](https://css-tricks.com/all-about-floats/)

## clear

An element that has the clear property set on it will not move up adjacent to the float like the float desires, but will move itself down past the float.

Values:

*  **`both`** is most commonly used, which clears floats coming from either direction.
*  **`left`** and **`right`** can be used to only clear the float from one direction respectively
*  **`none`** is the **default**
*  **`inherit`**

property is directly related to floats. If the element can fit horizontally in the space next to another element which is floated, it will. Unless you apply clear to that element in the same direction as the float. Then the element will move down below the floated element.

A common way to clear floats is to apply a pseudo element to a container element which clears the float.

for more info: Clear [👉 ](https://css-tricks.com/almanac/properties/c/clear/)

