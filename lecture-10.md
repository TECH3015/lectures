# TECH3015 Lecture 10

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

## ASSIGNMENT 1 **01**
<!-- .slide: class="crammed" -->

finishing assignment 1:

- 1200 **word limit** (or few hundred over)
- think **bullet points**!
- can be **informal**, write how you like
- **reference** any research/resources used
- complete finished **designs/mockups**
- **user feedback**:
  - state number of users
  - present in a table
- **revise** any [lectures you missed](https://vle.dmu.ac.uk/webapps/blackboard/content/listContent.jsp?course_id=_562055_1&content_id=_4770346_1&mode=reset)

---

## ASSIGNMENT 1 **02**
<!-- .slide: class="crammed" -->

**Due:** 12pm (midday) on Monday 21/12/2020

Crucial—**you must hand these in**:

- a brief **outline** explaining what your website is about
- **wireframes** (*mobile*, *tablet*, *desktop*)
- **design** sketches, finished design/mockup
- evidence of **user feedback**
- commentary/annotations for **images**
- critical **analysis**

---

## ASSIGNMENT 1 **03**
<!-- .slide: class="crammed" -->

Optional—**also good to include**:

- **site map**
- **content** inventory
- **user/task** stories and/or profiles
- **moodboard**, colour theme, font choices, etc.
- consistently-formatted **references**
- other material that shows your **process**

---

## ASSIGNMENT 1 **04**
<!-- .slide: class="crammed" -->

**5 marking criteria @ 20% each**

<!-- flipping direct links NOT WORK!! But I CBA to update them in the handbook now -->
<!-- - [Information Architecture](https://thomcorah.github.io/dmu-multimedia/lab-reader.html?TECH3015-Module-Handbook.md#informationarchitecture)
- [Responsiveness](https://thomcorah.github.io/dmu-multimedia/lab-reader.html?TECH3015-Module-Handbook.md#responsiveness)
- [Design & Interaction](https://thomcorah.github.io/dmu-multimedia/lab-reader.html?TECH3015-Module-Handbook.md#designandinteraction)
- [Accessibility](https://thomcorah.github.io/dmu-multimedia/lab-reader.html?TECH3015-Module-Handbook.md#accessibility)
- [Critical Analaysis](https://thomcorah.github.io/dmu-multimedia/lab-reader.html?TECH3015-Module-Handbook.md#criticalanalysis)
 -->

<!-- BUT these do -->

- [Information Architecture](https://github.com/thomcorah/dmu-multimedia/blob/master/md/TECH3015-Module-Handbook.md#information-architecture)
- [Responsiveness](https://github.com/thomcorah/dmu-multimedia/blob/master/md/TECH3015-Module-Handbook.md#responsiveness)
- [Design & Interaction](https://github.com/thomcorah/dmu-multimedia/blob/master/md/TECH3015-Module-Handbook.md#design-and-interaction)
- [Accessibility](https://github.com/thomcorah/dmu-multimedia/blob/master/md/TECH3015-Module-Handbook.md#accessibility)
- [Critical Analaysis](https://github.com/thomcorah/dmu-multimedia/blob/master/md/TECH3015-Module-Handbook.md#critical-analysis)

See the [module handbook](https://thomcorah.github.io/dmu-multimedia/lab-reader.html?TECH3015-Module-Handbook.md#coursework1) for full details

---

## ASSIGNMENT 1 **05**
<!-- .slide: class="crammed" -->

**Learning outcomes**

- **Understand and evaluate complex issues** related to browser platforms, accessibility, usability and mobile access when developing dynamic and animated content on the web.
- **Collect, evaluate, and analyse feedback** from users at various points in the development cycle of a Multimedia application.
- **Develop strategies** for the effective design and planning of a multimedia production

===

## LECTURE 10 CONTENT

- [basic HTML structure](#/4)
- [quick CSS tips](#/5)
- [responsive web design basics](#/6)
- [RWD breakpoint demo](#/6)

===

<!-- HTML5 REVISITED 05dec2020-->
<!-- also in: https://github.com/CTEC3905/10-lecture -->

## SEMANTIC STRUCTURE **01**
<!-- .slide: class="crammed" -->

- **header, footer**: optional within a **page or section**
- use header/footer for **complex content** about the containing element e.g. *author*, *copyright*, links to *terms of use*, *contact* info.
- **nav**: only for **major navigation links** - one only
- **article, section** can **contain each other** e.g. newspaper: a *games section* can have *game articles* with *technical sections* in each one

---

## SEMANTIC STRUCTURE **02**
<!-- .slide: class="crammed" -->

Important, because **good semantic structure** addresses:

- **access needs** for disabled users
- is **good UI and IA** practice
- enables **machine processing** of web-based content
- improves **searchability** and [SEO](https://support.google.com/webmasters/answer/40349?hl=en "Search Engine Optimisation")

---

## SEMANTIC STRUCTURE **03**
<!-- .slide: class="crammed" -->

the distinction between `figure` and `aside`

- `aside`: supplementary content **related** to surroundings e.g. boxout
- `aside`: for content simply **related** but **not essential**
- `figure`: for **essential** content where **position** in the flow of related text isn’t important

[The figure & figcaption elements (2010)](http://html5doctor.com/the-figure-figcaption-elements/)  
[Keep up-to-date: what's arrived/changed in HTML5](https://www.w3.org/TR/html/changes.html "W3C Recommendation, 1 November 2016")

---

## SEMANTIC STRUCTURE **04**
<!-- .slide: class="crammed" -->

HTML5 tags for **AUDIO & VIDEO**:

- `video`: [MDN](https://developer.mozilla.org/en/docs/Web/HTML/Element/video) and [W3Schools HTML video tag](http://www.w3schools.com/TAgs/tag_video.asp)
- `audio`: [MDN](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/audio) and [W3Schools HTML audio tag](http://www.w3schools.com/TAgs/tag_audio.asp)

The `src` attribute can read media files  
(e.g. .mpeg, .wav. .mp4…) hosted elsewhere.

Really want to push things? [Learning How to Capture and Record Audio in HTML5](https://medium.com/@yushulx/learning-how-to-capture-and-record-audio-in-html5-6fe68a769bf9) (Patchy browser support)

---

## SEMANTIC STRUCTURE **05**
<!-- .slide: class="crammed" -->

resources

- [HTML5 Element Flowchart](http://html5doctor.com/downloads/h5d-sectioning-flowchart.pdf) 
- [Avoiding common HTML5 mistakes](http://html5doctor.com/avoiding-common-html5-mistakes/)

<!-- END HTML5 REVISITED -->

===

<!-- CSS TIPS/REVISITED -->
<!-- https://ctec3905.github.io/10-lecture/#/6 -->

## CSS REVISITED **01**
<!-- .slide: class="crammed" -->

- **classes are reusable** in an HTML file, **IDs are unique**!
  
- you can use **more than one class** on one element:  
  `class="mything myclass anotherclass"`

---

## CSS REVISITED **02**
<!-- .slide: class="crammed" -->

- **don’t duplicate style rules** or whole **style blocks**…
  
- CSS rules in **breakpoints** should override  
  *only* specific **mobile**/**global** styles

---

## CSS REVISITED **02**
<!-- .slide: class="crammed" -->

**styles/my.css** needs a **path to find** images:

- **NO**: looks for 'images/' in the CSS folder:  
	`background: url('images/pic.jpg');`

- **YES**: goes **up and out** of 'styles/' and **into** 'images/'  
  `background: url('../images/pic.jpg');`

<!-- END CSS TIPS/REVISITED -->

===

## RESPONSIVE WEB DESIGN **01**
<!-- .slide: class="crammed" -->

<!-- RWD updated 05dec2020 -->
<!-- also in https://ctec3905.github.io/05-lecture/#/2 -->

to get started, here’s **all you need**…

- **mobile first** design using CSS (**top** of the .css file)
- [**natural breakpoints**](https://stackoverflow.com/a/20350990 "Follow the links and go down the rabbit-hole in this StackOverflow answer") (**not** device-specific)
- `min-width` up (**not** max-width) for **increasing widths**
- `<meta name="viewport" content="width=device-width, initial-scale=1.0">` in the HTML `head`

See the [responsive example](https://front-end-materials.github.io/page-layouts/responsive-page-outline/)
See the [responsive example code](https://github.com/front-end-materials/page-layouts/tree/master/responsive-page-outline)

---

## RESPONSIVE WEB DESIGN **02**
<!-- .slide: class="crammed" -->

A **mobile-first** CSS example:

```css
nav { display: flex; flex-direction: column; }
main { padding: .75em 10px; }
/* more mobile/global styles here < 599px */

@media screen and (min-width: 600px) {
  /* override mobile styles screens > 599px */
  nav { display: flex; flex-direction: row; }
}

@media screen and (min-width: 1200px) {
  /* override previous styles for screens > 1199px */
  main { padding: 1em 16px; max-width: 960px; }
}
```

---

## RESPONSIVE WEB DESIGN **03**
<!-- .slide: class="crammed" -->

### **NATURAL** BREAKPOINTS

Design **mobile-first**,  resize the browser window to **increase the screen width**

Add `min-width` **breakpoints** when the **design becomes “broken”** when the viewport width increases—  
all content should **look good at any width/height**

Use the [Chrome inspector mobile icon](https://developers.google.com/web/tools/chrome-devtools/device-mode/)

---

## RESPONSIVE WEB DESIGN **04**
<!-- .slide: class="crammed" -->

**Mobile menus**: reminders from the [Lecture 09 demo](https://tech3015.github.io/presents/?lecture-09#/4)

- [Last week's demo: mobile menu, animated slide-in (code)](https://github.com/front-end-materials/menus/tree/master/js-mobile-menu-anim-side), [(browser demo)](https://front-end-materials.github.io/menus/js-mobile-menu-anim-side/)
- [Extra demo: mobile menu, accessible, bottom-up (code)](https://github.com/front-end-materials/menus/tree/master/js-mobile-menu-anim-bottom), [(browser demo)](https://front-end-materials.github.io/menus/js-mobile-menu-anim-bottom/)

===

**CSS: errr**
<!-- .slide: class="crammed" -->

CSS chin moustache…

![chin moustache CSS](https://raw.githubusercontent.com/TECH3015/lectures/master/imgs/humour/moustache-css-position.jpg)
