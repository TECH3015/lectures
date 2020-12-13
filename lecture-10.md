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
- **watch** any [lectures you missed](https://github.com/TECH3015/lectures#welcome-to-tech3015)

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
- is **good UI** and aids **Information Architecture**
- enables **machine processing** of web-based content
- improves **searchability** and [SEO](https://support.google.com/webmasters/answer/40349?hl=en "Search Engine Optimisation")

---

## SEMANTIC STRUCTURE **03**
<!-- .slide: class="crammed" -->

the distinction between `figure` and `aside`

- [`aside`](https://www.w3resource.com/html5/aside-tutorial.php): extra content **related** to main e.g. boxout, quote
- `aside`: **non-essential** content in the flow of text
- [`figure`](https://www.w3resource.com/html5/figure-tutorial.php): **essential** content where **position** in the text is optional
- `figure`: has a **caption** e.g image, graph, diagram…

[The figure & figcaption elements (2010)](http://html5doctor.com/the-figure-figcaption-elements/)  
[Keep up-to-date: what's arrived/changed in HTML5](https://www.w3.org/TR/html/changes.html "W3C Recommendation, 1 November 2016")

---

<!-- .slide: data-background-image="https://raw.githubusercontent.com/TECH3015/lectures/master/imgs/layout/html5-element-flowchart.png" data-background-size="contain" -->

---

## SEMANTIC STRUCTURE **04**
<!-- .slide: class="crammed" -->

resources

- [HTML5 Element Flowchart](http://html5doctor.com/downloads/h5d-sectioning-flowchart.pdf) 
- [Avoiding common HTML5 mistakes](http://html5doctor.com/avoiding-common-html5-mistakes/)

<!-- END HTML5 REVISITED -->

---

## SEMANTIC STRUCTURE **05**
<!-- .slide: class="crammed" -->

HTML5 tags for **AUDIO & VIDEO**:

- `video`: [MDN](https://developer.mozilla.org/en/docs/Web/HTML/Element/video) and [W3Schools HTML video tag](http://www.w3schools.com/TAgs/tag_video.asp)
- `audio`: [MDN](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/audio) and [W3Schools HTML audio tag](http://www.w3schools.com/TAgs/tag_audio.asp)

The `src` attribute can also read media files  
(e.g. .mpeg, .wav, .mp4…) hosted elsewhere.

Really want to push things? [Learning How to Capture and Record Audio in HTML5](https://yushulx.medium.com/learning-how-to-capture-and-record-audio-in-html5-6fe68a769bf9) (Patchy browser support)


===

## JS: TWO TIPS
<!-- .slide: class="crammed" -->

This is **ALL** you need to get **your JavaScript file**:

```html
<script src="myscript.js"></script>
```

…add it **just before** the closing `</body>` tag!

…and here is a JavaScript style guide—some are way too wordy, so use this one…

[W3Schools has a good, brief style guide](https://www.w3schools.com/js/js_conventions.asp)

===

**CSS: chinstache…**
<!-- .slide: class="crammed" -->

```css
.moustache { position: absolute; bottom: 0; }
```

![chin moustache CSS](https://raw.githubusercontent.com/TECH3015/lectures/master/imgs/humour/moustache-css-position.jpg)
