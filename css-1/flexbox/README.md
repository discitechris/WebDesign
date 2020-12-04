# Flexbox

* The main idea behind the flex layout is to give the container the ability to alter its items’ width/height \(and order\) to best fill the available space \(mostly to accommodate to all kind of display devices and screen sizes\).
* A flex container expands items to fill available free space or shrinks them to prevent overflow.
* the flexbox layout is direction-agnostic as opposed to the regular layouts \(block which is vertically-based and inline which is horizontally-based\). 
* While those work well for pages, they lack flexibility to support large or complex applications \(especially when it comes to orientation changing, resizing, stretching, shrinking, etc.\)

{% hint style="info" %}
**NOTE:**     **Flexbox** layout is most appropriate to the _**components of an application, and small-scale layouts**_, while the **Grid** layout is intended for _**larger scale layouts**_.
{% endhint %}

## **Major Features:**

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

![](../../.gitbook/assets/flex-terminology.svg)

### **Components of Flexbox:**

* **Creation:** **`display`**
* **Direction:** **`flex-flow`** \(**`flex-direction`**, **`flex-wrap`**\)
* **Alignment:** **`justify-content`**, **`align-items`**, **`align-self`**, **`align-content`**
* **Ordering:** **`order`**
* **Flexibility:** **`flex`** \(**`flex-grow`**, **`flex-shrink`**, **`flex-basis`**\)



