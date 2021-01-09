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

## LECTURE 11 CONTENT

- [Quick CSS tips](#/3)
- [Responsive Web Design (RWD) basics](#/4)

===

<!-- CSS TIPS/REVISITED -->
<!-- https://ctec3905.github.io/10-lecture/#/6 -->

## CSS TIPS **01**
<!-- .slide: class="crammed" -->

- **classes** are **reusable** in your HTML files

- **ID**s are **unique**! Use them for JavaScript

- you can use **more than one class** on one element:  
  `class="mything myclass anotherclass"`

---

## CSS TIPS **02**
<!-- .slide: class="crammed" -->

**don’t duplicate style rules** or whole **style blocks**…
  
CSS rules in **breakpoints** should override  
*only* specific **mobile**/**global** styles

---

## CSS TIPS **03**
<!-- .slide: class="crammed" -->

**styles/my.css** needs a **path to find** images:

- **NO**: looks for 'images/' in the 'styles' folder:  
	`background: url('images/pic.jpg');`

- **YES**: goes **up and out** of 'styles/' and **into** 'images/'  
  `background: url('../images/pic.jpg');`

---

## CSS TIPS **04**
<!-- .slide: class="crammed" -->

Keep your CSS **in order**:

- `@font-face` at the top for custom fonts
- set **CSS variables** (custom properties) on `html`
- set **general styles** on `body`
- then **utility classes** e.g. links, headings
- set **menu styles** inside your `nav` tag e.g. `nav a`
- add **above-mobile** styles in a `@media` breakpoint  
  around `(min-width: 600px)`-ish

You now have a styled, **responsive page template**. Next…

---

## CSS TIPS **05**
<!-- .slide: class="crammed" -->

create sections in your CSS for the following:

- general styles for your **page content** `main` tag
- image/audio/video **gallery** styles
- **hover** styles in the above-mobile `@media` block
- styles for **forms** e.g. 'contact', 'search'

When **adding new styles**, keep them in the **order** you’ve made

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

**MIS-ALIGN-MENT**
<!-- .slide: class="crammed" -->

**ARRGGH** getting things to **line up**…

![getting things to line up with CSS](https://raw.githubusercontent.com/TECH3015/lectures/master/imgs/humour/humanty-victories-not-css.jpg)
