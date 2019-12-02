# TECH3015 Lecture 09

2019-2020

---

## MODULE TUTORS

- **Thom Corah** (Module Leader)  
Location: GH6.62  
Email: tcorah@dmu.ac.uk  
Tel: 0116 207 8088

- **Fania Raczinski** (labs)  
Email: fania.raczinski@dmu.ac.uk

- **Dave Everitt** (lectures)  
Email: deveritt@dmu.ac.uk


## MODULE STRUCTURE

- **Term 1, Assignment 1:** IA, design and wireframes, accessibility, interaction design, graphic design, **recap web languages**
- **Term 2, Assignment 2:** HTML5, CSS3, JavaScript ES6, APIs, animation, HTML validation, accessibility testing, Responsive Web Design and code, Progressive Web Apps


## ASSIGNMENT DEADLINES

- **Assignment 1 (40%):**  
midday (12pm) on Friday 13 December 2019

- **Assignment 2 (60%):**  
midday (12pm) Friday 3rd April 2020

[Full marking criteria for Coursework 1](https://daveeveritt.github.io/TECH3015/coursework-01.html#marking-criteria)  
(Assignment 2 criteria to follow)

---

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

All **HTML tags** create a box or `block`:

![A diagram of the box model](https://raw.githubusercontent.com/DaveEveritt/TECH3015/master/imgs/layout/boxmodel.png)


## BOX MODEL **2**

**NOTE**: the following elements have **default margins**:

`body`, `h1..h6`, `p`, `blockquote`, `form`, `fieldset`,  
and the list elements: `ul`, `ol`, `dl`, `dd`. 

You can reset these with CSS.


## BOX MODEL **3**

**Padding** is **inside** the box, **around** the box **content**

padding includes the **background colour** and **background image** of a box


## BOX-MODEL **4**

By default, **padding and border** are **added** to the width and height of a box:

```css
main {
  width: 70%;
  padding: 1em;
  border: 2px;
}
```

width is 70% **+** 2em **+** 4px


## BOX-MODEL **5**

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


## BOX-MODEL **6**

**CSS shorthand** for a single border style all around:

```css
img {
  border: 1px #555 dotted;
  /* a grey dotted border */
}
```


## BOX-MODEL **7**

Boxes can be rounded with `border-radius`:

```css
aside {
  border-radius: 2px; /* slight corner curves */
}

img {
  border-radius: 50%; /* totally round */
}
```


## BOX-MODEL **8**

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
	<h2>BOX-MODEL <strong>9</strong></h2>
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
	<h2>BOX-MODEL <strong>10</strong></h2>
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

---

<!-- FLEXBOX -->

## FLEXBOX **1**

**CSS flexbox** enables the **arrangement of boxes** inside a container:

```css
.my-boxes {
  display: flex;
}
```


## FLEXBOX **2**

**horizontal alignment**: use `justify-content:`:

- `flex-start` group items to **left** (the start) of container
- `flex-end` group items to **right** of container
- `center` group items in the **center** of a container
- `space-between` **distribute** items: first/last are left/right others are equally between
- `space-around` **distribute** and space items **evenly**


## FLEXBOX **3**

**vertical alignment**: use `align-items:`:

- `flex-start` across top
- `flex-end` across bottom
- `center` in center
- `baseline` across baseline
- `stretch` space items or stretch item to fill


## FLEXBOX **4**

**order of boxes**: use `flex-direction:`:

- `row` flow left to right
- `row-reverse` flow right to left
- `column` stack top to bottom
- `column-reverse` stack bottom to top


## FLEXBOX **5**

In this example, the **parent element** `.my-boxes`  
contains several **child elements** to arrange:

```css
.my-boxes {
  display: flex; /* set to display as flexbox */
  justify-content: space-around; /* even spacing */
  align-items: center; /* align vertical center */
  flex-direction: row-reverse; /* wrap last-first */
}
```


## FLEXBOX **6**

The HTML needs a **selector** e.g. `class="my-boxes"` for the CSS to **identify the element**:

```html
<section class="my-boxes">
  <div>Box one</div>
  <div>Box two</div>
  <div>Box three</div>
</section>
```


## FLEXBOX **7**

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
<p>How this code looks. <strong>Note</strong> the order of the boxes:</p>

<div class="my-boxes">
  <div>Box one</div>
  <div>Box two</div>
  <div>Box three</div>
</div>

<p>Try the CSS game <a href="http://www.flexboxdefense.com/">Flexbox Defence</a>.</p>



[![flexbox cheat sheet](https://raw.githubusercontent.com/DaveEveritt/TECH3015/master/imgs/layout/flexbox-cheat.png)](https://darekkay.com/dev/flexbox-cheatsheet.html)

---

## DEMO

Now for a demo…

if you're **not here now** see the Panopto recording or [see the demo file code](https://raw.githubusercontent.com/DaveEveritt/TECH3015/master/layout.html)
