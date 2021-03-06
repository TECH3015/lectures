<!-- .slide: class="centre" -->
# TECH3015 Lecture 18

2020/21

===

## MODULE TUTORS
<!-- .slide: class="left-align" -->

- **Thom Corah** (Module Leader)  
Location: GH6.62  
Email: tcorah@dmu.ac.uk  
Tel: 0116 207 8088

- **Dave Everitt** (lectures)  
Email: deveritt@dmu.ac.uk

===

# WEB ANIMATION
<!-- .slide: class="left-align" -->

there are **three approaches** (besides HTML5 Canvas):

- **transition** (CSS)
- **animation** (CSS)
- **SVG manipulation** (CSS/JavaScript)

You can also use JavaScript to **add a class** with a transition or animation to an element according to a user action (eventListener). See [what is animatable](https://www.w3schools.com/CSSref/css_animatable.asp).

===

<!-- BROWSER RENDERING -->

# BROWSER RENDERING **1**
<!-- .slide: class="left-align smalltext" -->

To **update the screen** a **web browser** goes through the following processes:

1. **(Re)Calculate**: determine which CSS rules apply to which elements
2. **Layout**: generate the dimensions and position for each element on the page
3. **Paint**: fill in the pixels for each element into layers (ready to draw to screen)
4. **Composite Layers**: In this final step, the browser draws the pre-painted layers to the screen.

---

# BROWSER RENDERING **2**
<!-- .slide: class="left-align crammed" -->

Changing a **colour** - e.g. transitioning a `background-color` on **hover** triggers the browser ‘**paint**’ process.

Changing an element’s `height` triggers **layout** (step 2) of all elements that follow it on the page, then **repaint** (step 3) and **redraw** (step 4) all of the affected content.

This is known as **reflow**, and it creates **a lot of work for the browser**. While it’s *difficult to avoid reflows entirely*, keeping them to a minimum is *good practice*.

---

# BROWSER RENDERING **3**
<!-- .slide: class="left-align smalltext" -->

For **optimisation**, especially for less powerful **mobile**CPUs, try to **avoid layout** or **paint** animations.

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

# CSS **TRANSITION** **1**
<!-- .slide: class="left-align" -->

- `transition` goes into the **actual element's styles**
- It does **nothing** but **marks the element** for transition
- the styles to **transition _to_** go into the element's   
 `:hover`, `:checked`, `:focus`, (etc.) state
- The **transition to these styles** is only triggered on  
 `:hover`, `:checked`, `:focus`, (etc.)

---

# CSS **TRANSITION** **2**
<!-- .slide: class="left-align" -->

- A transition can be **delayed** e.g.  
 `transition-delay: 2s;`
- A `transition` style can be **triggered by JavaScript**…
- …say by **adding a class** with a `transition`

**CSS `transition` !== CSS `@keyframes` animation**  
they work differently

---

# CSS **TRANSITION** **3**
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

there's **NO need** for vendor prefixes  
(e.g. `-webkit-transition`)

---

# CSS **TRANSITION** **4**
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

# CSS **TRANSITION** **5**
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
</style>

<h1>CSS <strong>TRANSITION</strong> <strong>6</strong></h1>

<div class="mymenu">menu item</div>

<div class="myclass"> </div>
<div class="myclasswait"> </div>

===

<!-- CSS ANIMATION -->

# CSS **ANIMATION** **1**
<!-- .slide: class="left-align crammed" -->

- Create and **name** a `@keyframes` block for the animations
- Add an `animation` rule with the **name** of your `@keyframes` to the element
- `@keyframes` can run `from` and `to` two styles,  
  or be **timed** (e.g. 0%, 25%, 50%, 75%, 100%)
- You can also trigger the animation on e.g.
 `:hover`, `:checked`, `:focus`, etc.

See [Animation](https://css-tricks.com/almanac/properties/a/animation/) (Chris Coyier, 2017)

---

# CSS **ANIMATION** **2**
<!-- .slide: class="left-align smalltext" -->

## THE **ELEMENT**

```css
.heart {
  width: 100%;
  height: 90px;
  margin: 30px;
  transform: scale(1.25);
  animation: pulsate 1.8s alternate infinite ease-in-out;
}
.heart:before,
.heart:after { 
  /* create heart shape here (see CodePen, next slide) */
}
```

animation: **name**, **duration**, **direction**, **count**, **timing function**

---

# CSS **ANIMATION** **3**
<!-- .slide: class="left-align" -->

## THE NAMED **KEYFRAMES**

```css
@keyframes pulsate {
	0% { transform: scale(1); }
	40% { transform: scale(1.3); }
	100% { transform: scale(1); }
}
```

See [CodePen](https://codepen.io/daveeveritt/pen/JjbapGb)

---

<style>
.reveal .heart-container {
  display: flex;
  justify-content: center;
}
.reveal .heart {
  width: 100px;
  height: 90px;
  margin: 30px;
  transform: scale(1);
  animation: 1600ms pulsate infinite alternate ease-in-out;
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
  40% { transform: scale(1.3); }
  100% { transform: scale(1); }
}
</style>

<h1>CSS <strong>ANIMATION</strong> <strong>4</strong><h1>

<div class="heart-container">
  <div class='heart'></div>
</div>

===

<!-- SVG GRAPHICS -->

# **SVG** GRAPHICS **1**
<!-- .slide: class="left-align crammed smalltext" -->

**SVG (Scalable Vector Graphics)** is an XML-based format for **drawing in the browser**

- SVG **version 1** has had support for ages, **version 2** is coming…
- SVG code is **visible** in the **web inspector** and **view source**
- SVG **has a DOM** of nested elements that can be **styled** with CSS and **manipulated** with JavaScript
- **Tiny** file sizes, **massive** functionality, **programmable**
- full **browser support** (see [caniuse SVG](https://caniuse.com/#search=svg))

Instead of ~~pixels~~, SVGs are a **set of instructions** that **create a vector image** from **co-ordinates** and take far **less memory**

SVG is ideal for **complex graphics** that **load quickly** (e.g. [maps](https://simplemaps.com/resources/svg-maps))

---

# **SVG** GRAPHICS **2**
<!-- .slide: class="left-align smalltext" -->

The [W3C Recommendation, 2011](https://www.w3.org/TR/SVG11/)

Some of the drawing applications that can generate SVG:

- [Boxy SVG](https://boxy-svg.com/) (very cheap/online)
- [Inkscape](https://inkscape.org/) (free)
- [Affinity Designer](https://affinity.serif.com/en-gb/designer/) (inexpensive)
- [Sketch](https://www.sketchapp.com/) (OS X-only, inexpensive)
- Adobe Illustrator (expensive)

See: [SVG getting started (MDN)](https://developer.mozilla.org/en-US/docs/Web/SVG/Tutorial/Getting_Started)  

Applications produce bloated/messy code! [Cleaning up SVG files manually](https://commons.wikimedia.org/wiki/User:Quibik/Cleaning_up_SVG_files_manually) or online: [SVGito online cleaner](https://sketchmaster.com/svg-optimizer)

---

# **SVG** GRAPHICS **3**
<!-- .slide: class="left-align crammed" -->

**SVG** VS HTML **Canvas**:

- **SVG** graphics are **retained mode** and do not need to be re-generated on re-sizing
- **canvas** graphics are **immediate mode**, re-generated each time the element is loaded

[Apple introduced the **canvas** element](https://en.wikipedia.org/wiki/Canvas_element#Intellectual_property_over_canvas),  
**SVG** has been a [standard since around 2002](https://www.w3.org/TR/?title=svg)

See [Canvas vs SVG](https://en.wikipedia.org/wiki/Canvas_element#Canvas_versus_Scalable_Vector_Graphics_(SVG))

---

# **SVG** GRAPHICS **4**
<!-- .slide: class="left-align crammed" -->

[SVG 1 and SVG 2](https://en.wikipedia.org/wiki/Scalable_Vector_Graphics#Version_1.x)… SVG is a **huge specification** with a **small working group** and—although widely-supported—has had patchy input from browsers. This is changing, with Microsoft helping to push SVG 2.

- **Developers**: use features, say what’s wanted, determine what’s actually used
- **Browsers**: implement features, are corporate gatekeepers with their own ideas
- **Specifications**: document how features should work and show browsers how to implement them, they also have their own ideas

---

# **SVG** GRAPHICS **5**
<!-- .slide: class="left-align" -->

SVG graphics also need to take care of accessibility requirements, so the next (slighly cheesy cat) example is from an [SVG article on accessibility](https://css-tricks.com/accessible-svgs/)

Now, we'll inspect a **cat SVG** to examine how the **SVG DOM** (which is XML) works

---
<style>
svg {
  max-height: 100vh;
}
.cls-1 { fill: #e4e3e5; }
.cls-2 { fill: #ada6ad; }
.cls-3 { fill: #d2d0d3; }
.cls-4 { fill: #79bf84; }
.cls-10, .cls-11, .cls-13, .cls-5, .cls-8, .cls-9 {
  fill: none;
  stroke-miterlimit: 10;
}
.cls-5 { stroke: #e4e3e5; }
.cls-6 { fill: #ff88b3; }
.cls-7 { fill: #d86694; }
.cls-8 { stroke: #ff88b3; stroke-width: 2px;}
.cls-9 { stroke: #d86694; }
.cls-10 { stroke: #6c6d6c; }
.cls-11 { stroke: #222322; }
.cls-12 { fill: #2f302f; }
.cls-13 { stroke: #2f302f; }
.cls-14 { fill: #fafcfa; }
/* DOES THIS WORK? */
.eye:hover {scaleY:.01; repeat:3; repeatDelay:.4; yoyo:true; transformOrigin: "50% 70%"; ease:Power2.easeInOut;}
</style>

<svg version="1" id="cat" viewBox="0 0 720 800" aria-labelledby="catTitle catDesc" role="img">
  <title id="catTitle">Pixels, My Super-friendly Cat</title>
  <desc id="catDesc">An illustrated gray cat with bright green blinking eyes.</desc>
  <path id="tail" data-name="tail" class="cls-1" d="M545.9,695.9c8,28.2,23.2,42.3,27.2,46.9,21.4,24.1,41.5,40.2,81.1,42.9s65.4-14.2,60.8-26.8-23.1-9.1-51.3-8.3c-35.2.9-66.6-31.3-74.8-63.9s-7.9-63.8-36.8-85.5c-44.1-33-135.6-7.1-159.8-3.4s-48.4,52.5-9.6,45.1,91.4-23.1,123.2-12.7C537.8,640.4,537.9,667.7,545.9,695.9Z" transform="translate(-9.7 -9.3)"/>
  <g id="body">
    <path id="bg" class="cls-2" d="M447.9,502.1c2.1,151.7-108.3,167-216.5,167S9.7,663.8,9.7,510.9,85,242.9,231.3,241,445.8,350.4,447.9,502.1h0Z" transform="translate(-9.7 -9.3)"/>
    <g id="leftleg">
      <path id="leg" class="cls-1" d="M195.6,671.5c-34.2-7.7-40.6-95.6-53.3-191-12-90-90.1-177.2-55.1-177.2s145.7,12,151.4,87.7S261.5,686.5,195.6,671.5Z" transform="translate(-9.7 -9.3)"/>
      <path id="foot" class="cls-3" d="M172.2,688.1c31.6,2.1,56.6-8.7,59.8-32.4s-22.1-49.5-27.3-24.3c25-16.4-39.1-29.4-27.6-3.9,14-24.9-49.6-19.2-31.9-.1-6.5-27.2-35.6,8.2-30.1,29.3C121.5,681.8,140.5,686,172.2,688.1Z" transform="translate(-9.7 -9.3)"/>
    </g>
    <g id="rightleg">
      <path id="leg-2" data-name="leg" class="cls-1" d="M260.4,670.4c42.4-9.2,48.7-87.7,53.9-185.2,5.1-96,98.2-176.1,63.1-176.1s-164,15.7-164,111.8C213.4,420.9,199.1,683.7,260.4,670.4Z" transform="translate(-9.7 -9.3)"/>
      <path id="foot-2" data-name="foot" class="cls-3" d="M279.4,689.8c-31.7,2-56.6-9-59.6-32.6s22.3-49.4,27.4-24.1c-24.9-16.5,39.2-29.2,27.6-3.8-13.9-25,49.7-18.9,31.9,0,6.6-27.1,35.6,8.4,30,29.4-6.7,25-25.7,29.1-57.3,31.1h0Z" transform="translate(-9.7 -9.3)"/>
    </g>
    <path id="tuft" class="cls-3" d="M80,331.2c3.5,9.5,1.2,28.9,4.3,32.7s31.5-30,43-20.6c10.7,8.7,1.7,55.9,12.9,64.5,10.1,7.7,32.1-50.6,52.5-38.7,24.9,14.6,34.1,49.9,49,49.9,18.3,0,7.5-49.5,24.1-53.3s46.1,52.6,60.2,45.6c4.8-2.4,3-50.4,12-57.6,8.7-6.9,30.5,22.4,33.5,18.9,3.7-4.1.1-23.1,8.6-36.1,3.4-5.2,18.9-2.6,28.8-.4a3.46,3.46,0,0,0,3.7-5.2c-19.6-30.8-100-147.4-184.2-147.4-93.3,0-150.9,86.8-178.1,141.6a3.43,3.43,0,0,0,3.6,4.9C63,328.4,78.4,326.6,80,331.2Z" transform="translate(-9.7 -9.3)"/>
  </g>
  <g id="head">
    <path id="collar" class="cls-4" d="M367,231.1c5.7,36.1-4.7,71-97.8,85.6s-184-18.5-189.7-54.5,16.7-17.3,109.8-31.9,172-35.3,177.7.8" transform="translate(-9.7 -9.3)"/>
    <g id="bg-2" data-name="bg">
      <path class="cls-1" d="M362.5,229.5C339.7,279,273.1,299.4,225,300c-60.6.7-134.7-29.5-153.5-86.4C45.6,135.4,132.2,32.6,225,35.8c96.1,3.4,171.7,119.4,137.5,193.7" transform="translate(-9.7 -9.3)"/>
      <path class="cls-5" d="M362.5,229.5C339.7,279,273.1,299.4,225,300c-60.6.7-134.7-29.5-153.5-86.4C45.6,135.4,132.2,32.6,225,35.8,321.1,39.2,396.7,155.2,362.5,229.5Z" transform="translate(-9.7 -9.3)"/>
    </g>
    <g id="leftear">
      <path id="outer" class="cls-1" d="M92.7,117c-2.6,4.7-14.7-16.1-16.5-45-3.3-27.7,3.7-63.4,5.4-62C80.7,8,117,10,143,20c27.5,8.9,44.7,25.7,39.5,27.1-30,23.4-59.9,46.6-89.8,69.9" transform="translate(-9.7 -9.3)"/>
      <path id="inner" class="cls-6" d="M105.8,106.9C103.9,110.3,95.3,95.5,94,75c-2.3-19.6,2.6-44.9,3.8-44-0.6-1.4,25.1,0,43.6,7.1,19.5,6.3,31.7,18.2,28,19.2q-31.8,24.9-63.6,49.6" transform="translate(-9.7 -9.3)"/>
    </g>
    <path id="mask" class="cls-2" d="M338.4,142.5c-2.2,3.3,19.4,19.6,17.2,23.2s-24.3-7.8-25.8-5.2c-1.9,3.3,33.4,24.1,31,29.2-2.3,4.9-34-14.4-84.3-18.1a141.76,141.76,0,0,1-16.4-2.1,91.21,91.21,0,0,1-13.7-3.9c-19.8-6.9-27.7-10.6-32.7-12-19.3-5.7-26.8,11.3-68.1,22.4-18.8,5-37.9,9.7-54.4,0-2.1-1.3-13.6-8.3-16.7-21.1-0.9-3.6-2.8-15.2,10.5-34C146.3,34.3,216.5,34,217.3,34a131.52,131.52,0,0,1,58.4,14.3c-7.6,4.9-11.2,9.5-9,10.1,21.5,16.5,43.1,33,64.6,49.5,0.9,1.7,3.6-1.3,6.3-7.3,19.3,30.5,22.1,41.5,18.9,44.3-3.8,3.6-16.4-4.8-18.1-2.4" transform="translate(-9.7 -9.3)"/>
    <g id="rightear">
      <path id="outer-2" data-name="outer" class="cls-2" d="M344.9,119.9c2.6,4.7,14.7-16.1,16.5-45,3.3-27.7-3.7-63.4-5.4-62,0.9-2-35.4,0-61.4,10-27.5,8.9-44.7,25.7-39.5,27.1q44.85,35,89.8,69.9" transform="translate(-9.7 -9.3)"/>
      <path id="inner-2" data-name="inner" class="cls-6" d="M343.5,76.2a77.83,77.83,0,0,1-5.6,24.6c-15.1-20.3-36-39.8-61-52.4a82,82,0,0,1,19.2-9.1c18.5-7.1,44.2-8.5,43.6-7.1,1.2-.9,6.1,24.4,3.8,44" transform="translate(-9.7 -9.3)"/>
    </g>
    <g id="nose">
      <path class="cls-7" d="M205.1,201.8l-10.6-18.3a9,9,0,0,1,7.7-13.4h21.2a8.9,8.9,0,0,1,7.7,13.4l-10.6,18.3a8.91,8.91,0,0,1-15.4,0" transform="translate(-9.7 -9.3)"/>
      <path class="cls-6" d="M194.2,175.1a9,9,0,0,0,.3,8.4l10.6,18.3a8.92,8.92,0,0,0,15.5,0l8.7-15c-5.8-6.2-19.3-10.1-35.1-11.7" transform="translate(-9.7 -9.3)"/>
    </g>
    <g id="mouth">
      <path class="cls-8" d="M166.7,260.4c-24.4,0-44.1-25-44.1-55.9m88.2,0c0,30.9-19.7,55.9-44.1,55.9m89.9,0c24.4,0,44.1-25,44.1-55.9m-88.2,0c0,30.9,19.7,55.9,44.1,55.9" transform="translate(-9.7 -9.3)"/>
      <path class="cls-9" d="M300.7,204.5a65.16,65.16,0,0,1-8,32" transform="translate(-9.7 -9.3)"/>
    </g>
    <path id="wiskers" class="cls-10" d="M188.7,198.4c0-12.9-72.7-23.3-162.6-23.3m162.6,36.2c0-7.1-65.8-12.9-147.1-12.9m196,1.3c1.4-12.8,74.8-15.6,164.1-6.2m-165.4,19c0.7-7.1,66.8-5.9,147.6,2.6" transform="translate(-9.7 -9.3)"/>
    <g id="lefteye" class="eye">
      <path id="iris" class="cls-4" d="M188.6,141.5s-18.3,12.3-35.8,7.9-30-15.2-27.7-24c1.5-6,9.6-9.6,20.2-9.8a59.5,59.5,0,0,1,15.7,1.9,35.75,35.75,0,0,1,12.5,6.2,60,60,0,0,1,15.1,17.8" transform="translate(-9.7 -9.3)"/>
      <path class="cls-11" d="M125.1,123.6c1.5-6,9.6-9.6,20.1-9.8a59.5,59.5,0,0,1,15.7,1.9,35.75,35.75,0,0,1,12.5,6.2,59.47,59.47,0,0,1,15.2,17.8" transform="translate(-9.7 -9.3)"/>
      <path id="pupil" class="cls-12" d="M172.9,124.3c-2.3,9.2-10.7,15-18.7,13s-12.5-11.1-10.2-20.4a22.39,22.39,0,0,1,1.1-3.1,59.5,59.5,0,0,1,15.7,1.9,35.75,35.75,0,0,1,12.5,6.2,8.6,8.6,0,0,1-.4,2.4" transform="translate(-9.7 -9.3)"/>
      <path id="eyelash" class="cls-13" d="M124.9,121.5c-7.6,2.6-17.1-4.7-21.1-16.3m33.6,9.5c-7.5,2.9-17.3-4-21.7-15.5m36.7,14.6c-8.1-.1-14.5-10.2-14.3-22.6" transform="translate(-9.7 -9.3)"/>
      <path id="reflection" class="cls-14" d="M156.8,122c0,3.6-2.6,6.4-5.8,6.4s-5.8-2.9-5.8-6.4,2.6-6.4,5.8-6.4,5.8,2.9,5.8,6.4" transform="translate(-9.7 -9.3)"/>
    </g>
    <g id="righteye" class="eye">
      <path id="iris-2" data-name="iris" class="cls-4" d="M241.4,143.6s18.5,11.9,36,7.1,29.6-15.8,27.2-24.6c-1.7-6-9.8-9.4-20.3-9.4a59.21,59.21,0,0,0-15.6,2.2,37.44,37.44,0,0,0-12.4,6.4,60.14,60.14,0,0,0-14.9,18.3" transform="translate(-9.7 -9.3)"/>
      <path id="lid" class="cls-11" d="M304.5,124.4c-1.7-6-9.8-9.4-20.3-9.4a59.21,59.21,0,0,0-15.6,2.2,37.44,37.44,0,0,0-12.4,6.4,61.21,61.21,0,0,0-14.9,18.1" transform="translate(-9.7 -9.3)"/>
      <path id="pupil-2" data-name="pupil" class="cls-12" d="M256.7,126.1c2.5,9.2,11,14.8,18.9,12.6s12.3-11.4,9.8-20.6a16.59,16.59,0,0,0-1.2-3.1,59.21,59.21,0,0,0-15.6,2.2,37.44,37.44,0,0,0-12.4,6.4,9.23,9.23,0,0,0,.5,2.5" transform="translate(-9.7 -9.3)"/>
      <path id="eyelash-2" data-name="eyelash" class="cls-13" d="M302.9,122.3c7.7,2.5,17-5,20.8-16.8M292,115.7c7.6,2.8,17.2-4.4,21.4-16M277,115.1c8.1-.3,14.3-10.5,13.9-22.8" transform="translate(-9.7 -9.3)"/>
      <path id="reflection-2" data-name="reflection" class="cls-14" d="M271.1,127.1c0,3.6-2.6,6.5-5.8,6.5s-5.8-2.9-5.8-6.5,2.6-6.4,5.8-6.4,5.8,2.9,5.8,6.4" transform="translate(-9.7 -9.3)"/>
    </g>
  </g>
</svg>

---

# **SVG** GRAPHICS **6**
<!-- .slide: class="left-align crammed" -->

SVG is already a thing (it began in 1999!) so here are a few more resources for further information and to **help get you started with SVGs**:

- [SVG on the web: A Practical Guide](https://svgontheweb.com/)
- [SVG Tutorial (W3Schools)](https://www.w3schools.com/graphics/svg_intro.asp)
- [SVG examples (W3Schools)](https://www.w3schools.com/graphics/svg_examples.asp)

---

# **SVG** GRAPHICS **7**
<!-- .slide: class="left-align crammed" -->

…and a few more tutorials and examples:

- [Practical SVG (book, Chris Coyier, 2016)](https://alistapart.com/article/practical-svg)
- [JavaScript in SVG](http://apike.ca/prog_svg_js_create.html)

===

<!-- SVG ANIMATION -->

<section class="left-align">
<h1><strong>SVG</strong> ANIMATION <strong>1</strong></h1>

<svg class="svg-anim" width="300" height="100">
  <circle cx="20" cy="50" r="15" />
</svg>

<p>This SVG is <strong>animated by CSS</strong></p>

---

# **SVG** ANIMATION **2**
<!-- .slide: class="left-align crammed" -->

The SVG **markup**:

```html
<svg width="300" height="100">
  <circle cx="20" cy="50" r="15" />
</svg>
```

(`cx`, `cy`: centre position of x and y, `r`: radius)

---

# **SVG** ANIMATION **3**
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
  animation: move 3s infinite ease-in-out alternate;
}
```
[Cubic-bezier CSS visual animation resource](http://cubic-bezier.com/) has more `animation-timing-function` examples, for HTML/SVG

---

# **SVG** ANIMATION **4**
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
    cx: 574;
    cy: 84;
    fill: #9f9;
    stroke: #fc5f8e;
  }
}
```

---

# **SVG** ANIMATION **4**
<!-- .slide: class="left-align crammed" -->

The two "SVG Sarahs"

- [Sarah Drasner](https://sarahdrasnerdesign.com/): book [SVG Animations](http://shop.oreilly.com/product/0636920045335.do)
- [Sarah Soueidan](https://www.sarasoueidan.com/tags/svg/), talk: [The \<SVG\> of .SVG](https://www.youtube.com/embed/hhISb-cpFgM)

See [SVG can do that?! (talk, Sarah Drasner)](https://www.youtube.com/watch?v=4laPOtTRteI) ([Slides](https://slides.com/sdrasner/svg-can-do-that#/)) and [USe SVG! (presentation, Sarah Soueidan)](http://slides.com/sarasoueidan/building-better-interfaces-with-svg#/)

These two developers have **worked extensively with SVG graphics**

---

# **SVG** ANIMATION **5**
<!-- .slide: class="left-align crammed" -->

**Sarah Drasner**:

- [Animated gear wheel](https://codepen.io/sdras/pen/NqYGZv)
- [Global warming solutions](https://codepen.io/sdras/full/JdJgrB)

<!-- - [Sarah Soueidan: CSS vs SVG](https://theblog.adobe.com/css-vs-svg-the-final-roundup/) -->

===

# **SVG** RESPONSIVE
<!-- .slide: class="left-align" -->

Sarah Soueidan also has a nice article on  
[Making SVGs Responsive using CSS](https://tympanus.net/codrops/2014/08/19/making-svgs-responsive-with-css/)…

…so finally, let's examine how her logo example becomes **responsive** with media queries:

[Responsive logo example](https://front-end-materials.github.io/svg/responsive-svg-logo/)

===

<!-- CODE COMEDY -->

# **THINK**, DON’T **COPY**
<!-- .slide: class="crammed" -->

![](https://raw.githubusercontent.com/front-end-materials/images/master/comedy/google-problems.jpg)

**read** it, **type** it out, **understand** it!
