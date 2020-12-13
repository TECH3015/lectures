# TECH3015 Lecture 11

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

- [Information Architecture](https://github.com/thomcorah/dmu-multimedia/blob/master/md/TECH3015-Module-Handbook.md#information-architecture)
- [Responsiveness](https://github.com/thomcorah/dmu-multimedia/blob/master/md/TECH3015-Module-Handbook.md#responsiveness)
- [Design & Interaction](https://github.com/thomcorah/dmu-multimedia/blob/master/md/TECH3015-Module-Handbook.md#design-and-interaction)
- [Accessibility](https://github.com/thomcorah/dmu-multimedia/blob/master/md/TECH3015-Module-Handbook.md#accessibility)
- [Critical Analaysis](https://github.com/thomcorah/dmu-multimedia/blob/master/md/TECH3015-Module-Handbook.md#critical-analysis)

See the [module handbook](https://thomcorah.github.io/dmu-multimedia/lab-reader.html?TECH3015-Module-Handbook.md#coursework1) for full details

===

## LECTURE 10 CONTENT

- [Quick CSS tips](#/5)
- [Responsive Web Design (RWD) basics](#/6)
- [RWD breakpoint demo](#/6)


===

<!-- CSS TIPS/REVISITED -->
<!-- https://ctec3905.github.io/10-lecture/#/6 -->

## CSS TIPS **01**
<!-- .slide: class="crammed" -->

- **classes are reusable** in an HTML file, **IDs are unique**!
  
- you can use **more than one class** on one element:  
  `class="mything myclass anotherclass"`

---

## CSS TIPS **02**
<!-- .slide: class="crammed" -->

- **don’t duplicate style rules** or whole **style blocks**…
  
- CSS rules in **breakpoints** should override  
  *only* specific **mobile**/**global** styles

---

## CSS TIPS **03**
<!-- .slide: class="crammed" -->

**styles/my.css** needs a **path to find** images:

- **NO**: looks for 'images/' in the 'styles' folder:  
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

### Mobile **menus**

Reminders from the [Lecture 09 demo](https://tech3015.github.io/presents/?lecture-09#/4)

- [Lecture 09 demo: mobile menu, animated slide-in (code)](https://github.com/front-end-materials/menus/tree/master/js-mobile-menu-anim-side), [(browser demo)](https://front-end-materials.github.io/menus/js-mobile-menu-anim-side/)
- [Extra demo: mobile menu, accessible, bottom-up (code)](https://github.com/front-end-materials/menus/tree/master/js-mobile-menu-anim-bottom), [(browser demo)](https://front-end-materials.github.io/menus/js-mobile-menu-anim-bottom/)

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

### Mobile **menus**

Reminders from the [Lecture 09 demo](https://tech3015.github.io/presents/?lecture-09#/4)

- [Lecture 09 demo: mobile menu, animated slide-in (code)](https://github.com/front-end-materials/menus/tree/master/js-mobile-menu-anim-side), [(browser demo)](https://front-end-materials.github.io/menus/js-mobile-menu-anim-side/)
- [Extra demo: mobile menu, accessible, bottom-up (code)](https://github.com/front-end-materials/menus/tree/master/js-mobile-menu-anim-bottom), [(browser demo)](https://front-end-materials.github.io/menus/js-mobile-menu-anim-bottom/)

===

**COMEDY SLIDE**
<!-- .slide: class="crammed" -->

![eyebrow z-index](https://raw.githubusercontent.com/TECH3015/lectures/master/imgs/humour/eyebrow-z-index.jpg)
