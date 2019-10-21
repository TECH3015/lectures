# TECH3015 Lecture 4

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

## Where we are

- web programming refreshers
- progress with planning your site:
  - gather your site **content**
  - arrange your content into *logical groups*
  - use help from feedback ([online card sorting](https://www.optimalworkshop.com/optimalsort))

---

## Assignment 1: 01
<!-- .slide: class="crammed" -->

What you need to hand in:

- a brief for your website
- complete set of wireframes
- mood board and/or rough designs
- evidence of initial user feedback
- your own supporting research
- references to relevant learning materials

---

## Assignment 1: 02

Marking criteria:

- criterion 1
- criterion 2
- criterion …

---

<!-- NEW -->
<!-- DESIGN PRINCIPLES: SHARED MEDS2007.02/CTEC3905.04-->

## DESIGN: **01**

Four basic principles:

- **P**roximity
- **A**lignment
- **R**epetition
- **C**ontrast

(The reverse of ‘**CRAP**’)

---

## DESIGN: **02**
<!-- .slide: class="crammed" -->

**PROXIMITY** sets up *visual cues* that group similar items, suggesting how to ‘read’ content.

- **Group complex content** for legibility
- Display **related items** together
- Use **common styles** to connect similar items

[Guardian website](https://www.theguardian.com/uk): “most viewed” news **grouped** together, **common menu style** has **section colours**

[BBC iPlayer website](http://www.bbc.co.uk/iplayer): **proximity** and **style** group related items


<!-- .slide: data-background-image="https://raw.githubusercontent.com/DaveEveritt/TECH3015/master/imgs/design/guardian-230oct2018.png" data-background-size="contain" -->


<!-- .slide: data-background-image="https://raw.githubusercontent.com/DaveEveritt/TECH3015/master/imgs/design/bbc-iplayer-23oct2018.png" data-background-size="contain" -->			

---

## DESIGN: **03**
<!-- .slide: class="crammed" -->

**ALIGNMENT** makes page elements seem **part of a whole**, creating a **holistic feel** to the various pieces of information.

- Everything should be **placed thoughtfully** in the layout
- Every item is **connected visually** with other page elements

A strict use of **alignment** on a former version of the Oslo-based design agency Heydays website gives a pleasing sense of **coherence and simplicity**.


<!-- .slide: data-background-image="https://raw.githubusercontent.com/DaveEveritt/TECH3015/master/imgs/design/heydays.jpg" data-background-size="contain" -->		

---

## DESIGN: **03a**

**ALIGNMENT**: **grids** are the **primary method** for achieving **alignment**.

- **The core text** on the history and use of grids in design is: Khoi Vinh and Mark Boulton (2007) [Grids Are Good](http://www.slideshare.net/huer1278ft/grids-are-good-right)
- Also see Vitaly Friedman (2007) [Designing With Grid-Based Approach](https://www.smashingmagazine.com/2007/04/designing-with-grid-based-approach/), Smashing Magazine


<!-- .slide: data-background-image="https://raw.githubusercontent.com/DaveEveritt/TECH3015/master/imgs/design/grids/wireframe-01.png" data-background-size="contain" -->	


<!-- .slide: data-background-image="https://raw.githubusercontent.com/DaveEveritt/TECH3015/master/imgs/design/grids/wireframe-02.png" data-background-size="contain" -->	


<!-- .slide: data-background-image="https://raw.githubusercontent.com/DaveEveritt/TECH3015/master/imgs/design/grids/wireframe-03.png" data-background-size="contain" -->	


<!-- .slide: data-background-image="https://raw.githubusercontent.com/DaveEveritt/TECH3015/master/imgs/design/grids/wireframe-04.png" data-background-size="contain" -->	


<!-- .slide: data-background-image="https://raw.githubusercontent.com/DaveEveritt/TECH3015/master/imgs/design/grids/wireframe-finished.png" data-background-size="contain" -->	

---

## DESIGN: **04**

**REPETITION** provides visual and cognitive **consistency** across common design elements

- Repeat **design themes** throughout the interface
- Consistent sizing and proportions strengthen **style**

Use: global **style rules** at the **top** of your CSS **before `@media` query breakpoints** to *style elements consistently* e.g. **colours**, image **widths** (not height), matching **heading** styles…


<!-- .slide: data-background-image="https://raw.githubusercontent.com/DaveEveritt/TECH3015/master/imgs/design/karl-anders.png" data-background-size="contain" -->	


<!-- .slide: data-background-image="https://raw.githubusercontent.com/DaveEveritt/TECH3015/master/imgs/design/creative-depart.jpg" data-background-size="contain" -->	

---

## DESIGN: **05**
<!-- .slide: class="crammed" -->

**CONTRAST**

- Make **distinctly different** items *look* different
- Contrast makes content appear **visually inviting**

There are many ways to create contrast. For example:  
**colour, fonts, rules, column widths**, etc.

- Javascript plugin site [unheap.com](http://www.unheap.com/) uses **bold colours**
- A previous design for agency [Touch](http://www.thetouchagency.co.uk/) used nice **hover transitions** (the current site is slow and annoying!)


<!-- .slide: data-background-image="https://raw.githubusercontent.com/DaveEveritt/TECH3015/master/imgs/design/unheap.png" data-background-size="contain" -->	


<!-- .slide: data-background-image="https://raw.githubusercontent.com/DaveEveritt/TECH3015/master/imgs/design/touch-website.png" data-background-size="contain" -->	

---

<!-- SIMPLICITY QUOTES -->

### SIMPLICITY
<!-- .slide: class="crammed smalltext" -->

**“Simplicity is the ultimate form of sophistication.”** —Leonardo da Vinci

**“Don’t make me think.”** —Steve Krug

### COMMUNICATION

**“People react positively when things are clear and understandable.”**  
—Dieter Rams

**“The main goal is not to complicate the already difficult life of the consumer.”** —Raymond Loewy

### DESIGN

**“White space is to be regarded as an active element, not a passive background.”** —Jan Tschichold

**“A lot of what we are doing is getting design out of the way.”** —Jonathan Ive

<!-- /NEW -->

---

<!-- COLOUR SCHEME LINK -->

Online **colour scheme** chooser: [Paletton](http://paletton.com/)

![Paletton.com colour scheme designer](https://raw.githubusercontent.com/DaveEveritt/TECH3015/master/imgs/design/paletton.png)


<!-- .slide: data-background-iframe="http://paletton.com" data-background-interactive data-background-size="contain" -->

---

<!-- WIREFRAME DESIGNER LINK -->

Online **wireframe** creator: [Figma.com](https://www.figma.com/)

![Paletton.com colour scheme designer](https://raw.githubusercontent.com/DaveEveritt/TECH3015/master/imgs/design/figma-wireframe-design.png)

---

## Design

Any questions about design?

---

## What you want next

What do you want to cover next week? E.g.

- assignment 1 marking criteria
- CSS flexbox
- CSS grid layout
- more on media queries/Responsive Web Design
- CSS animation
- JavaScript ES6 syntax
- Progressive Web Apps (PWAs)
- SVGs

---

## Final Questions?

No crowding around the  
podium after, please!

<!--

<h2>Title</h2>

<img style="float:left;" src="https://raw.githubusercontent.com/DaveEveritt/TECH3015/master/imgs/wireframes/img_name.jpg" alt="text">

.slide data-background-image="https://raw.githubusercontent.com/DaveEveritt/TECH3015/master/imgs/wireframes/rosenfeld-users-content-context.png" data-background-size="contain"

-->

