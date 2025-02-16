# TECH3015 Lecture 08

2020/21

===

## MODULE TUTORS

- **Thom Corah** (Module Leader)  
Location: GH6.62  
Email: tcorah@dmu.ac.uk  
Tel: 0116 207 8088

- **Dave Everitt** (lectures)  
Email: deveritt@dmu.ac.uk

===

## TOPICS TODAY

- **natural flow** of `HTML` elements
  * block / inline
- **customizing** or taking elements *out of flow*
  * floating
  * **positioning**
- **centering**
  * horizontal / vertical
  * flex

===

## Natural/Normal Flow
<!-- .slide: class="crammed" -->

**How does your <code>HTML</code> look without <code>CSS</code>?**

- all html elements are either **block** or **inline**
- inline elements wrap lines, just as text would
- you can change the **display** property of elements
- if unsure inspect element in the browser

---

### Block-level elements
<!-- .slide: class="crammed" -->

> "A block-level element always starts on a new line and takes up the full width available (stretches out to the left and right as far as it can)." [*]<!-- .element: data-preview-link -->

```css
div {
  display: block;
}
```

E.g. `<header>,<nav>,<div>,<section>,<h1>,<p>,<ul>,<form>,<table>,<figure>,<footer>…`

[*]: https://developer.mozilla.org/en-US/docs/Web/HTML/Block-level_elements

---

### Inline elements
<!-- .slide: class="crammed" -->

> "An inline element does not start on a new line and only takes up as much width as necessary." [*]

```css
span {
  display: inline;
}
```

E.g. `<a>,<span>,<code>,<button>,<strong>,<em>,<img>,<video>,<input>…`

[*]: https://developer.mozilla.org/en-US/docs/Web/HTML/Inline_elements

---

### Display Property
<!-- .slide: class="crammed" -->

There are many different [display types](https://developer.mozilla.org/en-US/docs/Web/CSS/display):

- `none, inline, block, inline-block, table, list-item, flex, grid`
- **flex** and **grid** are for more advanced layouts

[W3Schools Try "The Display Property"](https://www.w3schools.com/cssref/tryit.asp?filename=trycss_display)

[W3Schools Try "Inline-Block"](https://www.w3schools.com/css/tryit.asp?filename=trycss_inline-block_span1)

---

### Examples

**Inline**  
[![](https://raw.githubusercontent.com/TECH3015/lectures/master/imgs/layout/inline2.png)](https://codepen.io/faniae/pen/zYYyMEo)

---

**Block**  
[![](https://raw.githubusercontent.com/TECH3015/lectures/master/imgs/layout/block2.png)](https://codepen.io/faniae/pen/JjjweyN)

---

**Inline + Block**  
[![](https://raw.githubusercontent.com/TECH3015/lectures/master/imgs/layout/mix.png)](https://codepen.io/faniae/pen/yLLGRMx)

---

**Inline-Block**  
[![](https://raw.githubusercontent.com/TECH3015/lectures/master/imgs/layout/inline-block.png)](https://codepen.io/faniae/pen/dyywQBj)

---

**Images**  
[![](https://raw.githubusercontent.com/TECH3015/lectures/master/imgs/layout/images.png)](https://codepen.io/faniae/pen/wvvRQPO)

---

**Figures**  
[![](https://raw.githubusercontent.com/TECH3015/lectures/master/imgs/layout/figures.png)](https://codepen.io/faniae/pen/WNNLaYg)

===

## Customising Flow
<!-- .slide: class="crammed" -->

- by default items are in natural flow of html elements
- take them out of that flow by **floating** or **positioning**

[MDN In Flow and Out of Flow](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Flow_Layout/In_Flow_and_Out_of_Flow)

===

### Floating Elements
<!-- .slide: class="crammed" -->

> "places an element on the **left** or **right** side of its **container**, allowing text and inline elements to **wrap around** it" [*]

- intended mainly in **page layout** for images within text
- turns inline elements into **block**-level elements
- `left, right, none`

```css
img {
  float: right;
}
```

[*]: https://developer.mozilla.org/en-US/docs/Web/CSS/float

---

### Clearing Floats
<!-- .slide: class="crammed" -->

- stops element after float from moving around
- `left, right, both`

```css
p {
  clear: both;
}
```

---

### Examples

**float 2 images right**  
[![](https://raw.githubusercontent.com/TECH3015/lectures/master/imgs/layout/float.png)](https://codepen.io/faniae/pen/PooXXxN)

---

**float images differentely**  
[![](https://raw.githubusercontent.com/TECH3015/lectures/master/imgs/layout/float2.png)](https://codepen.io/faniae/pen/oNNJmNv)

---

**clear right floats**  
[![](https://raw.githubusercontent.com/TECH3015/lectures/master/imgs/layout/clear.png)](https://codepen.io/faniae/pen/GRRPzpj)

===

### Positioning Elements
<!-- .slide: class="crammed" -->

- more varied uses than floats, 
- can position elements in one of 5 ways
- `static, relative, absolute, fixed, sticky`
- you might need `top, bottom, left, right` too

[![](https://raw.githubusercontent.com/TECH3015/lectures/master/imgs/layout/css-positioning-schemes.png)](https://internetingishard.com/html-and-css/advanced-positioning/)

<small>[W3Schools: Position Property](https://www.w3schools.com/css/css_positioning.asp) | [MDN: Positioning](https://developer.mozilla.org/en-US/docs/Learn/CSS/CSS_layout/Positioning)</small>

---

### Static
<!-- .slide: class="crammed" -->

- default
- *not* affected by `top, bottom, left, right`

```css
div {
  position: static;
}
```

---

### Relative
<!-- .slide: class="crammed" -->

- position relative to **original location**
- affected by `top, bottom, left, right`
- if moved, leaves original space empty
- is also used to give a **positioning context**

```css
div:hover {
  position: relative;
  bottom: 2px; /* e.g. move on hover */
  right: 2px;
}
```

---

### Absolute
<!-- .slide: class="crammed" -->

- position relative to **nearest positioned ancestor**
- if no ancestor, then `body` is used as the context (container)
- **ancestor also needs to be positioned** e.g. `relative`
- moves with page when scrolling
- affected by `top, bottom, left, right`

```css
button { /* place in bottom right of a container */
  position: absolute;
  bottom: 0;
  right: 0;
}
```

---

### Fixed
<!-- .slide: class="crammed" -->

- position relative to the **viewport**
- stays fixed **when scrolling**
- affected by `top, bottom, left, right`

```css
nav {
  position: fixed;
  top: 2em;
  left: 10px;
}
```

---

### Sticky
<!-- .slide: class="crammed" -->

- position relative to **user's scroll position**
- stays fixed after scrolling to sticky point
- affected by `top, bottom, left, right`

```css
nav {
  position: sticky;
  top: 10px;
}
```

---

### Examples
<!-- .slide: class="crammed" -->

<iframe width="100%" height="400" src="https://interactive-examples.mdn.mozilla.net/pages/css/position.html" style="background:#ccc"></iframe>

[MDN CSS Demo: position](https://interactive-examples.mdn.mozilla.net/pages/css/position.html)

===

## Centering Things
<!-- .slide: class="crammed" -->

***Can be complicated, BUT...***

```css
div {
  display: flex;
  justify-content: center;
  align-items: center;
}
```

([How to Center in CSS](http://howtocenterincss.com/))

---

### Horizontal **1**
<!-- .slide: class="crammed" -->

> "When the element to be centered is an **inline element** we use `text-align: center` on its parent. When the element is a **block level element** we give it a `width` and set the `left` and `right` `margins` to a value of `auto`." [*]

[*]: https://vanseodesign.com/css/vertical-centering/

---

### Horizontal **2**
<!-- .slide: class="crammed" -->

|                       |                                    |
|:----------------------|-----------------------------------:|
| **text alignment**    | block **positioning**              |
| `text-align: center;` | `width: 50%;`<br>`margin: 0 auto;` |
| inline elements       | block elements                     |
| apply to parent       | apply to self                      |

---

### Horizontal **3**
<!-- .slide: class="crammed" -->

```html
<div>Centered block, left-aligned text</div>
<strong class="center">Inline, centered text (ignored)</strong>
<div class="center">Centered block, centered text</div>
```
[![](https://raw.githubusercontent.com/TECH3015/lectures/master/imgs/layout/center.png)](https://codepen.io/faniae/pen/dyyaOxO)
```css
div {
  background: silver;
  width: 50%;
  margin: 0 auto;
}
.center { text-align: center; }
```

---

### Vertical **1**
<!-- .slide: class="crammed" -->

- `line-height` can be used for **one** line of text
- flexbox's `align-items:center` best for everything
- `vertical-align` only used for tables and images

---

### Examples
<!-- .slide: class="crammed" -->

**one** line only `line-height` trick

[![](https://raw.githubusercontent.com/TECH3015/lectures/master/imgs/layout/line-height.png)](https://codepen.io/faniae/pen/GRRazag)

---
<!-- .slide: class="crammed" -->

`vertical-align` for **inline** image (click example)

```html
<div>
  Centered text with inline svg image <svg>cat</svg>
</div>
```
[![](https://raw.githubusercontent.com/TECH3015/lectures/master/imgs/layout/vertical-align.png)](https://codepen.io/faniae/pen/MWWdxaQ)
```css
div {
  background: cyan;
  line-height: 50px;
  text-align: center;
}
div svg {
  vertical-align: bottom;
}
```

---

<iframe width="100%" height="400" src="https://interactive-examples.mdn.mozilla.net/pages/css/vertical-align.html" style="background:#ccc"></iframe>

[MDN CSS Demo: vertical-align](https://developer.mozilla.org/en-US/docs/Web/CSS/vertical-align)

---

**various vertical centering**  
[![Examples of vertical centering](https://raw.githubusercontent.com/TECH3015/lectures/master/imgs/layout/vertical.png)](https://codepen.io/fania/pen/KKgKvZr)

===

**CSS: Z-INDEX**
<!-- .slide: class="crammed" -->

![CSS z-index oops](https://raw.githubusercontent.com/TECH3015/lectures/master/imgs/humour/eyebrow-z-index.jpg)

<!-- 
https://internetingishard.com/html-and-css/

[5-timeless-website-layouts-and-when-theyre-most-effective](https://www.globalreach.com/blog/2018/01/08/)

https://www.freecodecamp.org/news/an-animated-guide-to-flexbox-d280cf6afc35/ -->
