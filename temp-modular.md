<style>
  /* unique styles for this presentation */
	.borders div div {
		line-height: 2.5em;
		font-size: 0.8em;
		width: 700px;
		margin-top: 1em;
	}
	.border div {
		border: 4px solid #666; 
	}
	.borders .square div {
		height: 2.5em;
		width: 2.5em;
	}
	.radius-demo {
		width: 100%;
		text-align: center;
	}
	.radius-demo-div-l div {
		text-align: right;
		padding-right: 1em;
	}
	.radius-10 {
		background: #fcc;
		border-radius: 10px;
	}
	.radius-100 {
		background: #cfc;
		border-top-left-radius: 100%;
	}
	.radius-50 {
		background: #ccf;
		border-top-left-radius: 50%;
		border-bottom-left-radius: 50%;
	}
	.round {
		border-radius: 50%;
	}
</style>

<!-- BOX MODEL INTRODUCTION -->

## BOX MODEL **1**
<!-- .slide: class="left-align" -->

All **HTML tags** create a box or `block`:

![A diagram of the box model](images/boxmodel.png)


## BOX MODEL **2**

The **box dimensions** are controlled by the:

- **margin:** space ***outside***
- **padding:** space ***inside***
- **border:** line ***around***

*inline HTML* (e.g. `a` or `span`) also makes a box, but **may not show margin or padding** unless you set it’s CSS as `display: block;` or `display: inline-block;`


## BOX MODEL **3**: MARGIN

The **margin** makes an invisible **space around** an element  
usually set in **pixels**, **ems** or **percentages**:  
`1px`, `.5em`, `5%`

Can be zero: `margin: 0;`

**NOTE**: the following elements have **default margins**:  
`body`, `h1..h6`, `p`, `blockquote`, `form`, `fieldset`, and the list elements: `ul`, `ol`, `dl`, `dd`. You can reset these with CSS.


## BOX MODEL **4**: PADDING

**Padding** is **inside** the box, **around** the box **content**

padding includes the **background colour** and **background image** of a box

usually set in **pixels**, **ems** or **percentages**:  
`1px`, `.5em`, `5%`

Can be zero: `padding: 0;`


## BOX MODEL **5**: BORDER

The **border** goes **around the outside** of the box

best set in **pixels**, and easiest to set in one declaration:

`border: 1px solid silver;`  
`border-bottom: 3px dotted #999;`

Can be zero: `border-bottom: none;`


## BOX MODEL **6**: 3D

If you could **see HTML boxes**, they'd look like this!  
Note the **layers** are **nested** just as in the **HTML**

![3D box model image](images/3dview.png)

===

<!-- BOX MODEL SYNTAX -->

## BOX-MODEL **SYNTAX**: 1
<!-- .slide: class="left-align" -->

By default, **padding and border** are **added** to the width and height of a box:

```css
main {
  width: 70%;
  padding: 1em;
  border: 2px;
}
```

width is 70% **+** 2em **+** 4px


## BOX-MODEL **SYNTAX**: 2

With `box-sizing` set to to `border-box` the **padding and border** are **included** in the width and height, making measurements easier:

```css
main {
  box-sizing: border-box;
  width: 70%;
  padding: 1em;
  border: 2px;
}
```

`border-box` means width **remains 70%**  
(not 70% + 2em + 4px)


## BOX MODEL **SYNTAX**: 3

## For both **margin** and **padding**

```css
header {
  margin: 2px; /* a 2-pixel margin all round */
  padding-top: 1em; /* one line of padding at top */
  margin-left: 5%; /* 5% of available space to left */
}
/* you can use: -top -right -bottom -left */
```


## BOX-MODEL **SYNTAX**: 4

**CSS shorthand**
- **4** values: **top, right, bottom, left** (clockface)
- **3** values: **top, left-right, bottom**
- **2** values: **top-bottom, left-right**

```css
header {
  padding: 1em 10px .5em 5px;
  /* 4: top right bottom left: */
  padding: 1em 10px .5em; /* an em is one line-height */
  /* 3: top 1em, l-r 10 pixels, bottom .5em */
  margin: 1em 0;
  /* 2: one line top+bottom, none left-right: */
}
```


## BOX-MODEL **SYNTAX**: 5

Set top, right, bottom, left, then **reset one**

```css
header {
  margin: 10px; /* 10 pixels all round… */
  margin-top: 0; /* …but no top margin */
}
```
The second line comes *after*—so **overrides**—the first


## BOX-MODEL **SYNTAX**: 6

To **centre** an block element by itself, set the  
**left** and **right** margins to `auto`:

```css
header {
  margin: 0 auto; /* zero top-bottom, auto l-r */
}
```
`auto` fills the available space to the left and right equally.

This is also a common way to **centre a page design** in the **browser window**, although current designs prefer to **fill the browser window** completely.


## BOX-MODEL **SYNTAX**: 7

`display: inline-block` turns **inline elements** into **blocks that line up horizontally**, often for `a` or `li` tags in menus or the `img` tag for images.

```css
a {
  display: inline-block;
}
/* 'block' makes inline 'a' elements into blocks */
```

[W3Schools: HTML Block and Inline Elements](http://www.w3schools.com/html/html_blocks.asp)


## BOX-MODEL **SYNTAX**: 9

- Learn about the box model with [exercises on W3Schools](http://www.w3schools.com/css/css_boxmodel.asp)
- Adjust sliders on an [Interactive box-model demo](http://guyroutledge.github.io/box-model/)

===

<!-- BOX MODEL BORDER -->

## BOX MODEL **BORDER**: 1

box outline, three parameters:  `width`, `style`, `color`

```css
img {
  border-width: 2px;
  border-style: solid; /* none|solid|dotted|dashed */
  border-color: white;
}
.mybox img {
  border: 2px solid white; /* shorthand */
}
```
…if the image is inside a **figure** tag with a **class "mybox"**:
```
<figure class="mybox">
  <img src="images/mypic.png" alt="my face">
</figure>
```


## BOX-MODEL **BORDER**: 2

Each property can have **one**, **two**, **three** or all  
**four** “clockface” values: **top**, **right**, **bottom**, **left**.

```css
header {
  border-color: white black; /* top, bottom */
  border-width: 2px 0 4px; /* top, r-l, bottom */
  border-style: solid dotted none dashed;
    /* top, right, bottom, left */
}
```


## BOX-MODEL **BORDER**: 3

**CSS shorthand** for a single border style all around:

```css
img {
  border: 1px #555 dotted;
  /* a grey dotted border */
}
```


## BOX-MODEL **BORDER**: 4

Boxes can be rounded with `border-radius`:

```css
aside {
  border-radius: 2px; /* slight corner curves */
}

img {
  border-radius: 50%; /* totally round */
}
```


## BOX-MODEL **BORDER**: 5

Or have one, two or three sides rounded…

```css
img {
  border-top-left-radius: 50%;
  border-bottom-left-radius: 50%;
  /* a semi-circle (if height=width) or half-ellipse */
}
img {
  border-top-right-radius: 100%;
  /* an arc (if height=width) */
}
```


<section class="borders radius-demo left-align">
	<h2>BOX-MODEL <strong>BORDER</strong>: 6</h2>
	<p><strong>border-radius</strong>, rectangles/squares, with<br><code>border-width: 4px; border-color: #666;</code></p>
	<div class="float-l radius-demo-div-l border">
		<div class="radius-10">i’m 10px rounded, that square’s 50% rounded -></div>
		<div class="radius-100">one corner 100% rounded</div>
		<div class="radius-50">two corners 50% rounded</div>
	</div>
	<div class="square float-r border">
		<div class="radius-10 round"></div>
		<div class="radius-100"></div>
		<div class="radius-50"></div>
	</div>
</section>


<section class="borders radius-demo left-align">
	<h2>BOX-MODEL <strong>BORDER</strong>: 7</h2>
	<p><strong>border-radius</strong>, rectangles/squares, <strong>no border-style/color</strong></p>
	<div class="float-l radius-demo-div-l">
		<div class="radius-10">i’m 10px rounded, that square’s 50% rounded -></div>
		<div class="radius-100">one corner 100% rounded</div>
		<div class="radius-50">two corners 50% rounded</div>
	</div>
	<div class="square float-r">
		<div class="radius-10 round"></div>
		<div class="radius-100"></div>
		<div class="radius-50"></div>
	</div>
</secton>


## BOX-MODEL **BORDER**: 8

## more information on borders

Reference: [W3Schools: CSS Borders](http://www.w3schools.com/css/css_border.asp)

Or (if you like) play with [CSS shapes](https://css-tricks.com/examples/ShapesOfCSS/)

===

<!-- FLEXBOX -->

## FLEXBOX **1**: INTRODUCTION

**CSS flexbox** enables the **arrangement of boxes** inside a container:

```css
.my-boxes {
  display: flex;
}
```


## FLEXBOX **2**: HORIZONTAL

for **horizontal alignment** use the `justify-content:` property, with values:

- `flex-start` group items to **left** (the start) of container
- `flex-end` group items to **right** of container
- `center` group items in the **center** of a container
- `space-between` **distribute** items: first/last are left/right others are equally between
- `space-around` **distribute** and space items **evenly**


## FLEXBOX **3**: VERTICAL

for **vertical alignment** use the `align-items:` property, with values:

- `flex-start` across top
- `flex-end` across bottom
- `center` in center
- `baseline` across baseline
- `stretch` space items or stretch item to fill


## FLEXBOX **4**: ORDER

for the **order of boxes** use the `flex-direction:` property, with values:

- `row` flow left to right
- `row-reverse` flow right to left
- `column` stack top to bottom
- `column-reverse` stack bottom to top


## FLEXBOX **5**: EXAMPLE

In this example, the **parent element** `.my-boxes` contains  
several **child elements** to arrange:

```css
.my-boxes {
  display: flex; /* set to display as flexbox */
  justify-content: space-around; /* even spacing */
  align-items: center; /* align vertical center */
  flex-direction: row-reverse; /* wrap last-first */
}
```


## FLEXBOX **6**: EXAMPLE

The HTML just needs a **selector** e.g. `class="my-boxes"` for the CSS to **identify the element** to be **styled as flexbox**:

```html
<section class="my-boxes">
  <div>Box one</div>
  <div>Box two</div>
  <div>Box three</div>
</section>
```


## FLEXBOX **7**: EXAMPLE

<style>
.my-boxes {
  display: flex; /* set to display as flexbox */
  justify-content: space-around; /* even spacing */
  align-items: center; /* align vertical center */
  flex-direction: row-reverse; /* wrap last-first */
  background:#ccc;
  height: 300px;
}
.my-boxes div {
  background: #9c5;
  border: 1px solid #999;
  width: 200px;
  height: 200px;
  text-align: center;
  padding-top: 1em;
}
</style>
<p>The <code>.my-boxes</code> section tag contains the boxes to arrange</p>

<div class="my-boxes">
  <div>Box one</div>
  <div>Box two</div>
  <div>Box three</div>
</div>

<p>Try the CSS game <a href="http://www.flexboxdefense.com/">Flexbox Defence</a>.</p>



[![flexbox cheat sheet](https://raw.githubusercontent.com/DaveEveritt/TECH3015/master/imgs/layout/flexbox-cheat.png)](https://darekkay.com/dev/flexbox-cheatsheet.html)
