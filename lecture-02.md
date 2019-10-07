# TECH3015 Lecture 2

2019-2020

---

## Module Tutors

- **Thom Corah** (Module Leader)  
Location: GH6.62  
Email: tcorah@dmu.ac.uk  
Tel: 0116 207 8088

- **Fania Raczinski** (labs)  
Email: fania.raczinski@dmu.ac.uk

- **Dave Everitt** (lectures)  
Email: deveritt@dmu.ac.uk

---

## Module structure

- **Term 1, Assignment 1:** IA, design and wireframes, accessibility, interaction design, graphic design, mention reading list and resources, **recap web languages**
- **Term 2, Assignment 2:** HTML5, CSS3, JavaScript ES6, APIs, animation, HTML validation, accessibility testing, Responsive Web Design and code, Progressive Web Apps

---

## Assignment deadlines:

- **Assignment 1 (40%):**  
midday (12pm) on Friday 13 December 2019

- **Assignment 2 (60%):**  
midday (12pm) Friday 3rd April 2020

Full assignment criteria covered in later lectures

---

## Handbook: update coming!

- [link on BlackBoard](https://thomcorah.github.io/dmu-multimedia/tech3015/module-handbook.html)
- see reading/resources list

---

## Where we are

- planning your site
- web programming refreshers

---

## HTML5 structure

```html
<!doctype>
<html>
  <head>
    <!-- stuff for the browser -->
    <title>my page name</title>
    <!-- get CSS in head section before page load: -->
    <link rel="stylesheet" href="mystyles.css">
  </head>
  <body>
    <!-- everything you see in in the body tag -->
    <!-- get JavaScript here after page load: -->
    <script src="js/myscripts.js"></script>
  </body>
</html>
```

---

## Planning your site 01

gather all the **content** for your site:

- images
- movies
- text
- audio
- choosing data from APIs

---

## Planning your site 02

arrange your content into *logical groups*

**THINK:** will a group be **limited** or get **more content**?

this is the basis for your site structure, **navigation** and **menu**

Resources from [usability.gov](https://www.usability.gov/):

- [Content Strategy Basics](https://www.usability.gov/what-and-why/content-strategy.html)
- [Content Inventory](https://www.usability.gov/how-to-and-tools/methods/content-inventory.html)
- [Information Architecture](https://www.usability.gov/what-and-why/information-architecture.html)

---

## Planning your site 03

you can get input from others with an online tool:

[Online card sorting software](https://www.optimalworkshop.com/optimalsort)

sign up to the [free plan](https://www.optimalworkshop.com/register)

---

## Planning your site 04

at the next stage, you will use **HTML5 tags** to **mark up** the basic areas for:

- each **kind** of page you have or…
- for one long **scrolling** page

---

## Planning your site 05

inside the `body` tag, use **HTML5 semantic tags** ([read more at W3Schools](https://www.w3schools.com/html/html5_semantic_elements.asp)) for **overall structure**

- `header` (optional but advised)
- `nav`
- `main`
- `footer` (optional)

*avoid div tags* and don’t make up tags!

HTML5 semantic tags for **content** come later

---

## HTML5 semantic tags

questions?

---

## RWD: breakpoints 01

CSS **media queries** can respond to many factors:

- print
- width/height
- orientation
- speech
- hover
- light-level
- many more…

Full list: [Using media queries (MDN)](https://developer.mozilla.org/en-US/docs/Web/CSS/Media_Queries/Using_media_queries)

---

## RWD: breakpoints 02

**However** we only need `screen` and `min-width` e.g.

```css
@media only screen and (min-width: 600px) {
  body {
    background-color: lightblue;
  }
}
```

Some [examples of RWD (mediaqueri.es)](https://mediaqueri.es/)

---

## RWD: breakpoints 03

use **one** CSS style sheet for your whole site!

do **general** and **mobile** styles first, at the top

**above/before any media queries**

---

## RWD: breakpoints 04

your CSS file should be arranged like this e.g.:

```css
/* all general/mobile styles first… */

body { background: rgb(220,230,210); }
a:link, a:visisted { color: #003; }
/* etc… */

/* first breakpoint above mobile */

@media only screen and (min-width: 600px) {
  a:hover { color: #225; }
  /* override mobile styles here…
  and set styles for larger widths */
}
```

---

## Media queries and breakpoints

questions?

---

## What you want next

What do you want to cover next week? E.g.

- design sketches and wireframes
- CSS flexbox and grid
- more o media queries Repsonsive Web Design (RWD)
- CSS animation
- JavaScript ES6 syntax
- Progressive Web Apps (PWAs)
- SVGs

---

## Questions?

Ask now, no crowding around  
the podium after, please!