
# OLD OLD OLD

<!-- .slide: class="centre" -->
# TECH3015 Lecture 18

2019-2020

===

## MODULE TUTORS
<!-- .slide: class="left-align" -->

- **Thom Corah** (Module Leader)  
Location: GH6.62  
Email: tcorah@dmu.ac.uk  
Tel: 0116 207 8088

- **Fania Raczinski** (labs)  
Email: fania.raczinski@dmu.ac.uk

- **Dave Everitt** (lectures)  
Email: deveritt@dmu.ac.uk

---

## MODULE STRUCTURE
<!-- .slide: class="left-align" -->

- **Term 1, Assignment 1:** DONE!
- **Term 2, Assignment 2:** HTML5, CSS3, JavaScript ES6, APIs, animation, [HTML validation](https://validator.w3.org/), accessibility testing, [Responsive Web Design](https://developers.google.com/web/fundamentals/design-and-ux/responsive/) and code, Progressive Web Apps

---

## ASSIGNMENT DEADLINES
<!-- .slide: class="left-align" -->

- **Assignment 2 (60%):**  
midday (12pm) Friday 3rd April 2020

[Full marking criteria for Coursework 2](https://tech3015.github.io/lectures/coursework-02.md#marking-criteria)

<style>
.slides {
  --redish: #fc5f8e;
  --blueish: #5fabfc;
  --greenish: #9f9;
}
.svg-anim {
  width: 600px;
  height: 100px;
  border: 1px solid #ccc;
}
.svg-anim circle {
  fill: #5fabfc;
  stroke: white;
  animation: move 3s infinite ease-in-out alternate;
  /* animation: move 3s infinite cubic-bezier(.16,-0.2,.82,1.2) alternate; */
}
@keyframes move {
  from {
    cx: 18;
    cy: 18;
    fill: #fc5f8e;
    stroke: #9f9;
  }
  to {
    cx:584;
    cy: 84;
    fill: #9f9;
    stroke: #fc5f8e;
  }
}
.myclass {
	background: var(--greenish);
	height: 100px;
	width: 100px;
	transition: width 2s;
}
.myclass:hover {
	width: 600px;
}
.myclasswait {
	width: 100px;
	height: 100px;
	background: var(--redish);
	transition: all 2s ease-in-out;
	transition-delay: 2s;
}
.myclasswait:hover {
	background: var(--blueish);
	width: 600px;
}
.reveal .mymenu {
	margin-bottom: 1em;
	text-align: center;
	border-bottom: 4px solid #ccc;
	background: #88c;
	width: 12em;
	color: #ccc;
	line-height: 2em;
	transition: all .6s ease-in-out;
}
.mymenu:hover {
	background: #ccf;
	color: #88c;
	transform: translateY(4px);
	border-bottom: 4px solid #88c;
}
.reveal .heart-container {
	position: relative;
	margin-left: 40%;
}
.reveal .heart {
	width: 100%;
	height: 90px;
	margin: 30px;
	transform: scale(1.25);
	animation: 1.8s pulsate alternate infinite ease-in-out;
}
.heart:before,
.heart:after { 
	position: absolute;
	content: "";
	left: 50px;
	top: 0;
	width: 50px;
	height: 80px;
	background: red;
	border-radius: 50px 50px 0 0;
	transform: rotate(-45deg);
	transform-origin: 0 100%;
}
.heart:after {
	left: 0;
	transform: rotate(45deg);
	transform-origin :100% 100%;
}

@keyframes pulsate {
	0% { transform: scale(1); }
	50% { transform: scale(1.3); }
	100% { transform: scale(1); }
}
</style>

<!-- WEB ANIMATION INTRO -->

===

# WEB ANIMATION
<!-- .slide: class="left-align" -->

## THREE APPROACHES

- **transition** (CSS)
- **animation** (CSS)
- **SVG manipulation** (JavaScript and CSS)

You can also use JavaScript to **add a class** with a transition or animation to an element according to a user action (eventListener). See [what is animatable](https://www.w3schools.com/CSSref/css_animatable.asp).

===

<!-- BROWSER RENDERING -->

# BROWSER RENDERING **1**
<!-- .slide: class="left-align crammed" -->

To **update the screen** a **web browser** goes through the following processes:

1. **(Re)Calculate**: determine which CSS rules apply to which elements
2. **Layout**: generate the dimensions and position for each element on the page
3. **Paint**: fill in the pixels for each element into layers (ready to draw to screen)
4. **Composite Layers**: In this final step, the browser draws the pre-painted layers to the screen.

---

# BROWSER RENDERING **2**
<!-- .slide: class="left-align" -->

Changing a **colour** - e.g. transitioning a `background-color` on **hover** triggers the browser "**paint**" process.

Changing an element’s `height` triggers **layout** (step 2) of all elements that follow it on the page, then **repaint** (step 3) and **redraw** (step 4) all of the affected content.

This is known as **reflow**, and it creates **a lot of work for the browser**. While it’s *difficult to avoid reflows entirely*, keeping them to a minimum is *good practice*.

---

# BROWSER RENDERING **3**
<!-- .slide: class="left-align smalltext" -->

For **optimisation**, especially for **mobile** where the CPU is less powerful, it’s best to **avoid layout** or **paint** animations.

CSS `transform` is the best property to animate, because the GPU (Graphics Processing Unit) can be used (including mobile GPUs). The following are the **least processor-intensive to animate**, and will not force screen redraw:

- [Opacity](https://developer.mozilla.org/en-US/docs/Web/CSS/opacity): `opacity: 0..1;`
- [Position](https://developer.mozilla.org/en-US/docs/Web/CSS/transform-function/translate) `transform: translate(?, ?);` (x, y)
- [Rotation](https://developer.mozilla.org/en-US/docs/Web/CSS/transform-function/rotate): `transform: rotate(?deg);`
- [Scale](https://developer.mozilla.org/en-US/docs/Web/CSS/transform-function/scale): `transform: scale(?, ?)` (x, y)

---

# BROWSER RENDERING **4**
<!-- .slide: class="left-align crammed" -->

The above is for your professional reference—**you don’t have to worry too much about optimisation for the assignment**, but it’s still a good idea to know about it.

**References:**

- [High Performance Animations, Paul Lewis, Paul Irish, 2013](https://www.html5rocks.com/en/tutorials/speed/high-performance-animations/)
- [Silky CSS: Minimizing Repaints & Jank, 2015](https://trendyminds.com/blog/silky-css-minimizing-repaints-jank)
- [CSS triggers: which CSS triggers what browser action](https://csstriggers.com/)
- [What can be transformed (MDN)](https://developer.mozilla.org/en-US/docs/Web/CSS/transform)

===

<!-- CSS TRANSITION -->

# CSS TRANSITION **1**
<!-- .slide: class="left-align" -->

- `transition` goes into the **actual element's styles**
- It does **nothing but mark the element** for transition
- the **styles to transition _to_** go into the element's   
 `:hover`, `:checked`, `:focus`, (etc.) state
- The **transition to these styles** is only triggered on  
 `:hover`, `:checked`, `:focus`, (etc.)

---

# CSS TRANSITION **2**
<!-- .slide: class="left-align" -->

- A transition can be **delayed** e.g.  
 `transition-delay: 2s;`
- A `transition` style can be **triggered by JavaScript**…
- …say by **adding a class** with a `transition`

**CSS `transition` !== CSS `@keyframes` animation**  
they work differently

---

# CSS TRANSITION **3**
<!-- .slide: class="left-align smallcode" -->

```css
.mymenu {
  /* basic style rules here */
  background: #88c;
  color: #ccc;
  border-bottom: 4px solid #ccc;
  transition: all 1s ease-in-out;
}
.mymenu:hover {
  background: #ccf;
  color: #88c;
  transform: translateY(4px);
  border-bottom-color: #88c;
}
```

**NO** vendor prefixes e.g. `-webkit-transition`  
—they're **not required**.

---

# CSS TRANSITION **4**
<!-- .slide: class="left-align" -->

```css
.myclass {
  width: 100px;
  height: 100px;
  background: green;
  transition: width 2s;
}
.myclass:hover {
  width: 600px;
}					
```

---

# CSS TRANSITION **5**
<!-- .slide: class="left-align" -->

```css
.myclasswait {
  width: 100px;
  height: 100px;
  background: red;
  transition: all 2s;
  transition-delay: 2s;
}
.myclasswait:hover {
  background: blue;
  width: 600px;
}					
```

---

<h1>CSS TRANSITION <strong>6</strong></h1>

<div class="mymenu">menu item</div>

<div class="myclass"> </div>
<div class="myclasswait"> </div>

===

<!-- CSS ANIMATION -->

# CSS ANIMATION **1**
<!-- .slide: class="left-align crammed" -->

- Create and **name** a `@keyframes` block for the animations
- Add an `animation` rule with the **name** of your `@keyframes` to the element
- `@keyframes` can run `from` and `to` or be **timed** e.g. at
 0%, 25%, 50%, 75%, 100%
- You can also trigger the animation on e.g.
 `:hover`, `:checked`, `:focus`, etc.

See [Animation](https://css-tricks.com/almanac/properties/a/animation/) (Chris Coyier, 2017)

---

# CSS ANIMATION **2**
<!-- .slide: class="left-align smalltext" -->

## THE **ELEMENT**

```css
.heart {
  width: 100%;
  height: 90px;
  margin: 30px;
  transform: scale(1.25);
  animation: 1.8s pulsate alternate infinite ease-in-out;
}
.heart:before,
.heart:after { 
  /* create heart shape here */
}
```

animation: duration, name, direction, count, timing function

---

# CSS ANIMATION **3**
<!-- .slide: class="left-align" -->

## THE **KEYFRAMES**

```css
@keyframes pulsate {
  0% { transform: scale(1); }
  50% { transform: scale(1.3); }
  100% { transform: scale(1); }
}
```

Adapted from [This Pen](https://codepen.io/Zeaklous/pen/rmDdx)

---

<h1>CSS ANIMATION <strong>4</strong><h1>

<div class="heart-container">
  <div class='heart'></div>
</div>

===

<!-- SVG GRAPHICS -->

# SVG GRAPHICS **1**
<!-- .slide: class="left-align crammed smalltext" -->

**SVG (Scalable Vector Graphics)** is an XML-based format for **drawing in the browser**

- SVG **version 1.1** has had support for ages, **version 2** is pending…
- SVG code is **visible** in the **web inspector** and **view source**
- SVG **has a DOM** of nested elements that can be **styled** with CSS and **manipulated** with JavaScript
- **Tiny** file sizes, **massive** functionality, **programmable**
- full **browser support** (see [caniuse SVG](https://caniuse.com/#search=svg))

Instead of ~~pixels~~, SVGs are a **set of instructions** that **create a vector image** and take far **less memory**

SVG is ideal for **complex graphics** that **load quickly** (e.g. [maps](https://simplemaps.com/resources/svg-maps))

---

# SVG GRAPHICS **2**
<!-- .slide: class="left-align crammed" -->

The [W3C Recommendation, 2011](https://www.w3.org/TR/SVG11/)

Some of the drawing applications that can generate SVG:

- [Boxy SVG](https://boxy-svg.com/) (very cheap/online)
- [Inkscape](https://inkscape.org/) (free)
- [Affinity Designer](https://affinity.serif.com/en-gb/designer/) (inexpensive)
- [Sketch](https://www.sketchapp.com/) (OS X-only, inexpensive)
- Adobe Illustrator (expensive)

See: [SVG getting started (MDN)](https://developer.mozilla.org/en-US/docs/Web/SVG/Tutorial/Getting_Started)

---

# SVG GRAPHICS **3**
<!-- .slide: class="left-align crammed" -->

SVG and HTML Canvas

- **SVG** graphics are **retained mode** and do not need to be re-generated on re-sizing
- **canvas** graphics are **immediate mode**, re-generated each time the element is loaded

[Apple introduced the **canvas** element](https://en.wikipedia.org/wiki/Canvas_element#Intellectual_property_over_canvas),  
**SVG** has been a [standard since before 2011](https://www.w3.org/standards/techs/svg#w3c_all)

See [SVG vs. HTML5 Canvas](https://www.cs.tufts.edu/comp/150IDS/final_papers/ppaleo01.1/FinalReport.html)

---

# SVG GRAPHICS **4**
<!-- .slide: class="left-align crammed" -->

Why are we still at SVG 1.1?

SVG is a **huge specification** with a **small group** working on it, and little input from browser manufacturers, to the frustration of many, **including Adobe**

See:

- [The SVG 2 Conundrum](https://css-tricks.com/svg-2-conundrum/)
- [Is SVG 2 really on life support?](http://libregraphicsworld.org/blog/entry/is-svg-2-really-on-life-support)

---

# SVG GRAPHICS **5**
<!-- .slide: class="left-align crammed" -->

Because SVG is already a thing (it began in 1999!) here are a few more resources for further information and to help get you started—**only if you're interested**

- [Practical SVG, Chris Coyier, 2016](https://alistapart.com/article/practical-svg)
- [JavaScript in SVG](http://apike.ca/prog_svg_js_create.html)
- [SVG on W3Schools](https://www.w3schools.com/html/html5_svg.asp)

===

<!-- SVG ANIMATION -->

<section class="left-align">
<h1>SVG ANIMATION <strong>1</strong></h1>

<svg class="svg-anim" width="300" height="100">
  <circle cx="20" cy="50" r="15" />
</svg>

<p>This SVG is <strong>animated by CSS</strong></p>

---

# SVG ANIMATION **2**
<!-- .slide: class="left-align crammed" -->

The SVG **markup**:

```html
<svg width="300" height="100">
  <circle cx="20" cy="50" r="15" />
</svg>
```

(`cx`, `cy`: centre position of x and y, `r`: radius)

---

# SVG ANIMATION **3**
<!-- .slide: class="left-align crammed" -->

The basic **CSS styles** and **animation**:

```css
.svg-anim {
  width: 600px;
  height: 100px;
  border: 1px solid #ccc;
}
.svg-anim circle {
  fill: #5fabfc;
  stroke: white;
  animation: move 3s infinite linear alternate;
}
```
[Cubic-bezier CSS visual animation resource](http://cubic-bezier.com/) has more `animation-timing-function` examples, for HTML/SVG

---

# SVG ANIMATION **4**
<!-- .slide: class="left-align crammed" -->

The CSS **animation keyframes**

```css
@keyframes move {
  from {
    cx: 26;
    cy: 17;
    fill: #fc5f8e;
    stroke: #9f9;
  }
  to {
    cx:574;
    cy: 84;
    fill: #9f9;
    stroke: #fc5f8e;
  }
}
```

---

# SVG ANIMATION **4**
<!-- .slide: class="left-align crammed" -->

The two "SVG Sarahs"

- [Sarah Drasner](https://sarahdrasnerdesign.com/): book [SVG Animations](http://shop.oreilly.com/product/0636920045335.do)
- [Sarah Soueidan](https://www.sarasoueidan.com/): [SVG articles](https://www.sarasoueidan.com/tags/svg/), [codePen](https://codepen.io/SaraSoueidan/)

These two developers have **worked extensively with SVG graphics**

---

# SVG ANIMATION **5**
<!-- .slide: class="left-align crammed" -->

**Sarah Drasner**:

- [Animated gear wheel](https://codepen.io/sdras/pen/NqYGZv)
- [Global warming solutions](https://codepen.io/sdras/full/JdJgrB)

[Sarah Drasner on CodePen](https://codepen.io/sdras/)

---

# SVG ANIMATION **6**
<!-- .slide: class="left-align crammed" -->

**Sarah Soueidan**:

- [Use SVG! presentation](http://slides.com/sarasoueidan/building-better-interfaces-with-svg#/)
- [Sarah Soueidan: CSS vs SVG](https://theblog.adobe.com/css-vs-svg-the-final-roundup/)

[Sarah Soueidan, Making SVG Responsive using CSS](https://tympanus.net/codrops/2014/08/19/making-svgs-responsive-with-css/) ([Example](https://tympanus.net/Tutorials/ResponsiveSVGs/index6.html))

===

<!-- CODE COMEDY -->

# **THINK**, DON’T **COPY**
<!-- .slide: class="left-align" -->

![](images/google_problems.jpg)

**read** it, **type** it out, **understand** it!


# QUESTIONS?