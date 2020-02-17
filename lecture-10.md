# TECH3015 Lecture 10

2019-2020

===

## MODULE TUTORS

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

- **Term 1, Assignment 1:** IA, design and wireframes, accessibility, interaction design, graphic design, **recap web languages**
- **Term 2, Assignment 2:** HTML5, CSS3, JavaScript ES6, APIs, animation, HTML validation, accessibility testing, Responsive Web Design and code, Progressive Web Apps

---

## ASSIGNMENT DEADLINES

- **Assignment 1 (40%):**  
midday (12pm) on Friday 13 December 2019

- **Assignment 2 (60%):**  
midday (12pm) Friday 3rd April 2020

[Full marking criteria for Coursework 1](https://tech3015.github.io/lectures/coursework-01.html#marking-criteria)  
(Assignment 2 criteria to follow)

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
- **revise** any [lectures you missed](https://vle.dmu.ac.uk/webapps/blackboard/execute/announcement?method=search&context=course_entry&course_id=_550284_1&handle=announcements_entry&mode=view)

---

## ASSIGNMENT 1 **02**

Crucial—**you must hand these in**:

- a brief **outline** explaining what your website is about
- **wireframes** (*mobile*, *tablet*, *desktop*)
- **design** sketches, finished design/mockup
- evidence of **user feedback**
- commentary/annotations for **images**
- critical **analysis**

---

## ASSIGNMENT 1 **03**

Optional—**also good to include**:

- *site map*
- *content* inventory
- *user/task* stories and/or profiles
- *moodboard*, colour theme, font choices, etc.
- consistently-formatted *references*
- other material that shows your *process*

---

## ASSIGNMENT 1 **04**

**5 marking criteria @ 20% each**

- Information Architecture
- Responsiveness
- Design & Interaction
- Accessibility
- Critical Analaysis

See the [full Marking Criteria](https://tech3015.github.io/lectures/coursework-01.html#marking-criteria)

===

## LECTURE 10 CONTENT

- [basic HTML structure](#/4)
- [quick CSS tips](#/5)
- [responsive web design basics](#/6)
- [RWD breakpoint demo](#/7)

===

<!-- HTML5 REVISITED -->
<!-- in: https://github.com/CTEC3905/10-lecture -->

## HTML5 SEMANTIC STRUCTURE **01**

- **header, footer**: optional within a **page or section**
- use footer/header for **complex content** about the containing element e.g. *author*, *copyright*, links to *terms of use*, *contact* info.
- **nav**: only for **major navigation links** - one only
- **article, section** can **contain each other** e.g. newspaper: a *games section* can have *game articles* with *technical sections* in each one

---

## HTML5 SEMANTIC STRUCTURE **02**

Important, because **good semantic structure** addresses:

- **access needs** for disabled users
- is **good UI and IA** practice
- enables **machine processing** of web-based content
- improves **searchability** and [SEO](https://support.google.com/webmasters/answer/40349?hl=en "Search Engine Optimisation")

---

## HTML5 SEMANTIC STRUCTURE **03**

the distinction between `figure` and `aside`

- `aside`: supplementary content **related** to surroundings e.g. boxout
- `aside`: for content simply **related** but **not essential**
- `figure`: for **essential** content where **position** in the flow of related text isn’t important

[The figure & figcaption elements (2010)](http://html5doctor.com/the-figure-figcaption-elements/)  
[Keep up-to-date: what's arrived/changed in HTML5](https://www.w3.org/TR/html/changes.html "W3C Recommendation, 1 November 2016")

---

## HTML5 SEMANTIC STRUCTURE **04**

HTML5 tags for **AUDIO & VIDEO**:

- `video`: [MDN](https://developer.mozilla.org/en/docs/Web/HTML/Element/video) and [W3Schools HTML video tag](http://www.w3schools.com/TAgs/tag_video.asp)
- `audio`: [MDN](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/audio) and [W3Schools HTML audio tag](http://www.w3schools.com/TAgs/tag_audio.asp)

The `src` attribute can read media files  
(e.g. .mpeg, .wav. .mp4…) hosted elsewhere.

Really want to push things? [Learning How to Capture and Record Audio in HTML5](https://medium.com/@yushulx/learning-how-to-capture-and-record-audio-in-html5-6fe68a769bf9) (Patchy browser support)

---

## HTML5 SEMANTIC STRUCTURE **05**

resources

- [HTML5 Element Flowchart](http://html5doctor.com/downloads/h5d-sectioning-flowchart.pdf) 
- [Avoiding common HTML5 mistakes](http://html5doctor.com/avoiding-common-html5-mistakes/)

<!-- END HTML5 REVISITED -->

===

<!-- CSS TIPS/REVISITED -->
<!-- https://ctec3905.github.io/10-lecture/#/6 -->

## QUICK CSS TIPS **01**

- **classes are reusable** in an HTML file, **IDs are unique**!
  
- you can use **more than one class** on one element:  
  `class="mything myclass anotherclass"`

---

## CSS REVISITED **02**

- **don’t duplicate style rules** or whole **style blocks**…
  
- CSS rules in **breakpoints** should override  
  *only* specific **mobile**/**global** styles

---

## CSS REVISITED **02**

**styles/my.css** needs a **path to find** images:

- **NO**: looks for 'images/' in the CSS folder:  
	`background: url('images/pic.jpg');`

- **YES**: goes **up and out** of 'styles/' and **into** 'images/'  
  `background: url('../images/pic.jpg');`

<!-- END CSS TIPS/REVISITED -->

===

## RESPONSIVE WEB DESIGN **01**

<!-- https://ctec3905.github.io/05-lecture/#/2 -->

to get started, here’s **all you need**…

- **mobile first** design using CSS (**top** of the .css file)
- [**natural breakpoints**](https://stackoverflow.com/a/20350990 "Follow the links and go down the rabbit-hole in this StackOverflow answer") (**not** device-specific)
- `min-width` up (**not** max-width) for **increasing widths**
- `<meta name="viewport" content="width=device-width, initial-scale=1.0">` in the HTML `head`

<!-- See the [responsive starter code](https://github.com/CTEC3905/starter-code)! -->
<!-- See the [responsive starter code](https://github.com/DaveEveritt/starter-code)! -->

---

## RESPONSIVE WEB DESIGN **02**

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

### **NATURAL** BREAKPOINTS

Design **mobile-first**,  resize the browser window to **increase the screen width**

Add `min-width` **breakpoints** when the **design becomes “broken”** when the viewport width increases—  
all content should **look good at any width/height**

Use the [Chrome inspector mobile icon](https://developers.google.com/web/tools/chrome-devtools/device-mode/)

---

## RESPONSIVE WEB DESIGN **04**

Now the second demo…

Making the mobile design responsive

if you're **not here now** watch the [Panopto recording](https://dmureplay.cloud.panopto.eu/Panopto/Pages/Viewer.aspx?id=4f7f57a2-8b99-4674-9d95-ab1f00997b76)!

- [demo: responsive layout (code)](https://github.com/front-end-materials/page-layouts/tree/master/responsive-page-outline)
- [demo: in browser (use Chrome mobile view)](https://front-end-materials.github.io/page-layouts/responsive-page-outline/)
- [last week's demo: simple mobile menu (code)](https://github.com/front-end-materials/menus/tree/master/js-mobile-menu)
- [last week's demo: in browser (use Chrome mobile view)](https://front-end-materials.github.io/menus/js-mobile-menu/)
