<!-- .slide: class="centre" -->
# TECH3015 Lecture 19

2019-2020

===

# CORONA VIRUS
<!-- .slide: class="left-align smalltext" -->

COVID-19 has meant **all teaching is now online**

- Fania will be present in the BlackBoard **[Online Classroom](https://vle.dmu.ac.uk/webapps/collab-ultra/tool/collabultra?course_id=_550284_1&mode=cpview)**  
  during the **usual lab time on Tuesdays at 4-6pm**
- Please **be patient with emails**, we have **many queries** across modules!
- **Visit** your **public_html folder** in a **browser** to be sure we can **see the web files**

Please **attend online**, even briefly, if only to email later with **anything specific**  
if you **really need to**—target only **one or two issues** at a time

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

- **Term 1, Assignment 1 (40%):** DONE!
- **Term 2, Assignment 2 (60%):** your website here!

For Assignment 2:

- **Website = 60%**
- **Documentation = 40%**

A **new deadline** allows for two extra weeks…

---

## NEW ASSIGNMENT DEADLINE
<!-- .slide: class="left-align" -->

**Assignment 2 was**  
~midday (12pm) Friday 3rd April 2020~  

**Assignment 2 NOW**  
midday (12pm) Friday **17th April** 2020

---

## ASSIGNMENT 2
<!-- .slide: class="left-align" -->

You need to hand in:

- **the website**, in your public_html folder
- **the critical report**, as a PDF on Turnitin

It helps us locate your site if it's in **public_html/TECH3015/coursework2/website**

**IMPORTANT!** Use **home.html** rather than the standard **index.html** so we can see the full file listing

===

## MARKING CRITERIA
<!-- .slide: class="left-align" -->

Let's go through a detailed checklist of the  
[full marking criteria for Coursework 2](https://tech3015.github.io/lectures/coursework-02.md#marking-criteria)  
with some linked resources to help you

Points mentioned in the handbook are **abbreviated here** because some appear in **multiple criteria**

===

## MARKING CRITERIA: **CONTENT 01**
<!-- .slide: class="left-align smalltext" -->

From the [handbook marking criteria](https://tech3015.github.io/lectures/coursework-02.md#marking-criteria):

- HTML5 markup uses **semantic tags** appropriately
- Text content has **semantic structure** e.g. headings, lists etc.
- Careful selection, preparation and editing of **video and/or audio**
- Awareness of **loading speed** and disk space e.g. no huge images
- Your **own original content** is briefly credited and any **third-party content** referenced (media from a single source can have just a **single general credit/reference**) - so we know the difference

---

## MARKING CRITERIA: **CONTENT 02**
<!-- .slide: class="left-align smalltext" -->

[Content](https://tech3015.github.io/lectures/coursework-02.html#content) **checklist**:

**Document** briefly that you've addressed these points (a **table in an appendix** will do)

- **valid HTML** (a few warnings are okay, explain that you understand them)
- no **missing images** check every page from the server, not just locally
- no **broken links** click every link
- no **JavaScript errors** - don't include JavaScript on pages where it isn't used
- web-**prepared files** (image, audio, video file sizes - okay if hosted elsewhere)

here are some free online file **compressors** and **converters**…

---

## MARKING CRITERIA: **CONTENT 03**
<!-- .slide: class="left-align smalltext" -->

[youcompress](https://www.youcompress.com/) handles images, audio and video, or…

- **Images:** [shortpixel.com](https://shortpixel.com/), [tinyjpg.com](https://tinyjpg.com/), takes multiple images: [imagecompressor.com](https://imagecompressor.com/), more detailed options: [kraken.io](https://kraken.io/web-interface)

- **Video:** [clipchamp.com](https://clipchamp.com/) has several tools, including a [video compressor](https://clipchamp.com/en/video-compressor/) and [video converter](https://clipchamp.com/en/video-converter/). Two more simpler ones: [apowersoft](https://www.apowersoft.com/compress-video-online), [mp4compress.com](https://www.mp4compress.com/)

- **Audio:** [mp3smaller](https://www.mp3smaller.com/) and [compress MP3](https://www.onlineconverter.com/compress-mp3), for mobile: [onlineconverter](https://www.onlineconverter.com/mobile-audio)

===

## MARKING CRITERIA: **STYLE 01**
<!-- .slide: class="left-align smalltext" -->

[Style](https://tech3015.github.io/lectures/coursework-02.html#style) **checklist**:

Your website should appeal to your **intended audience** and follow on from your **mockups/designs** (or, if not, explain in your documentation **what changed and why**). **CSS** is the **crucial technology** here.

- Style and layout reflect/have **evolved from the designs**
- **Coherent overall design** (see [PARC slides](https://tech3015.github.io/presents/?lecture-04#/6)), colour and font choices
- Design and content matches the **target audience**
- Skilful use of CSS to style and **arrange site elements**
- **No duplicate CSS**, prefer **classes** over IDs for selectors
- **Well-ordered CSS**: **mobile-first** followed by `min-width` breakpoints to be  
  fully responsive at **any screen width**

---

## MARKING CRITERIA: **STYLE 02**
<!-- .slide: class="left-align smalltext" -->

**Simplify your CSS 01**

- **do not** apply CSS styles globally to **all elements of a kind**  
  e.g. `img { width: 100%; }`, instead, **target only the elelments required**
- **do not repeat any mobile/global CSS styles** that are at the top of your CSS file in the breakpoints—**they 'cascade' to the larger sizes**
- avoid adding the same class to (e.g.) every image inside a container. Instead, add a **class to the container** and apply the style to **images inside the container**

for example…

---

## MARKING CRITERIA: **STYLE 03**
<!-- .slide: class="left-align smalltext smallcode" -->

**Simplify your CSS 02**

Apply styles to the **images inside the container** by using a class on the **container**

**Before:** ~same class on every image~

```css
/* DON'T DO THIS! */
<section>
  <img class="gallery" alt="brief text" src="images/image1.png">
  <img class="gallery" alt="brief text" src="images/image2.png">
  <img class="gallery" alt="brief text" src="images/image3.png">
</section>
```

**After:** **one** class **on the container**

```css
/* DO THIS! */
<section class="gallery">
  <img alt="brief text" src="images/image1.png">
  <img alt="brief text" src="images/image2.png">
  <img alt="brief text" src="images/image3.png">
</section>
```

(your **container** can be any block-level element: `div`, `ul`, `ol` `section` etc.) …

---

## MARKING CRITERIA: **STYLE 04**
<!-- .slide: class="left-align smalltext smallcode" -->

**Simplify your CSS 03**

Now apply CSS styles to **images inside the container**:

**Before:** ~same class on every image or **BAD!** on `img`~

```css
/* DON'T DO THIS! */
.gallery { /* or img */
  width: 100%;
  object-fit: cover;
}
/* do not duplicate .gallery on every image
```
**After:** **one** `.gallery` class **on the container**

```css
/* DO THIS! */
.gallery img {
  width: 100%;
  object-fit: cover;
}
/* add .gallery to the container for the images
```

You can also use `figure` and `figcaption` tags for **good semantic markup**

---

## MARKING CRITERIA: **STYLE 05**
<!-- .slide: class="left-align smalltext" -->

**Design** and **Information Architecture 1**

Use **navigation feedback** e.g. highlight the **current page** menu item with a class to styles it differently, and add an **ARIA role** (your CSS use `a[role="page"]` as a selector)

```html
<nav>
  <a href="index.html" class="currentPage" aria-current="page">Home</a>
  <a href="about.html">About</a>
  <a href="contact.html">Contact</a>
</nav>
<!-- no real need for ul and li inside the nav tag -->
```

You can keep things simple—[a `ul` inside `nav` is optional](https://stackoverflow.com/a/49090010/123033),  
but see [Using the aria-current attribute](https://tink.uk/using-the-aria-current-attribute/)

Read [WebAIM: The Cause of, and Solution to, All Our Accessibility Problems](https://webaim.org/blog/aria-cause-solution/)

---

## MARKING CRITERIA: **STYLE 06**
<!-- .slide: class="left-align smalltext" -->

**Design** and **Information Architecture 2**

**Nested pages** [can use breadcrumbs](https://www.smashingmagazine.com/2009/03/breadcrumbs-in-web-design-examples-and-best-practices/) beneath the menubar  
e.g. for breadcrumbs on: **travels > locations > crete**:

```html
<p aria-label="Breadcrumb">
  <a href="travels/index.html">Travels</a> >
  <a href="travels/locations/index.html">Locations</a> >
  <span>Crete</span>
</p>
<!-- mind the default margin/padding on the p tag -->
```

Use t `p` tag `Breadcrumb` attribute. If the last item is a link (but a `span` is fine) use `aria-current="page"` but **move aria-current** from the **main menu to the currentsub-page**. You can **still have a visual style** on the **Travels** main menu item.

You could also use `nav` instead of `p`—this is [one case](https://stackoverflow.com/a/58305075/123033) for [more than one `nav` element](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/Heading_Elements#Labeling_section_content), as it is part of the **site-wide navigation** and not a *minor local sub-menu*

[Accessible Breadcrumb Navigation Pattern](https://scottaohara.github.io/a11y_breadcrumbs/)

---

## MARKING CRITERIA: **STYLE 07**
<!-- .slide: class="left-align smalltext" -->

**Design** and **Information Architecture 3**

links to previous lectures on **IA** and **design** and:

- [Lecture 3: Information Architecture](https://tech3015.github.io/presents/?lecture-03#/10)
- [lecture 4: the PARC design principles](https://tech3015.github.io/presents/?lecture-04#/6)
- [Lecture 7: Information Design](https://tech3015.github.io/presents/?lecture-07#/5)

===

## MARKING CRITERIA: **TECH 01**
<!-- .slide: class="left-align smalltext" -->

[Technical Skills](https://tech3015.github.io/lectures/coursework-02.html#technical-skills) **checklist**:

You need to demonstrate your ability to **apply the concepts learnt** in this module:

- Ability in current web code: **markup (HTML5)**, **style (CSS)**, **programming (JS)**
- Awareness of **usability/accessibility** (more in a moment)
- Use of **CSS animations** and/or **transitions** (subtle or otherwise!)
- Site works across **screen sizes**, including **mobile**
- Use of **at least two** of:
  - Local database **data storage**
  - Third-party data **APIs**
  - CSS **animation** (the `@keyframes` timeline)
  - **JavaScript** user **interaction** and/or **functionality**

look through the [slide index](https://github.com/tech3015/lectures/#lecture-slides-term-1) to **find the presentations** covering these, but here are some further hints on **technical skills** …

---

## MARKING CRITERIA: **TECH 02**
<!-- .slide: class="left-align smalltext" -->

**Technical Skills 01**

Some basics:

- keep **file** and **folder** names **lower-case**—servers are *case-sensitive*!
- **organise your media** (images, video and audio) in sub-folders
- make **filenames consistent** and **descriptive** e.g.  
  `crete-01.png` instead of `image1.png`
- styles in **breakpoints** will **override earlier styles**
- generally, use **one CSS file for your whole site** but if you *really* need more…
  - note that **CSS ordering** is from **top->bottom** i.e. **first->last**
  - last to load **overrides what came before** …

---

## MARKING CRITERIA: **TECH 03**
<!-- .slide: class="left-align smalltext" -->

**Technical Skills 02**

try to avoid it, but if you have **more than one stylesheet**,  
the CSS cascade and order works like this:

```html
<link rel="stylesheet" href="css/styles.css">
<link rel="stylesheet" href="css/styles2.css">
```

```css
/* in styles.css */
body { background: rgb(255, 200, 200); }

/* in styles2.css
   this overrides the above 
   because it loads afterwards */
body { background: rgb(200, 100, 100); }
```

---

## MARKING CRITERIA: **TECH 04**
<!-- .slide: class="left-align smalltext" -->

**Technical Skills 03**

styles in breakpoints **override only at the specified width**:

```css
/* at the top of styles.css */
body { background: rgb(255, 200, 200); }

@media (min-width: 600px) {
  body { background: rgb(200, 100, 100); }
  /* this overrides the global/mobile body style
   only above 600 pixels screen width */
}
```

---

## MARKING CRITERIA: **TECH 05**
<!-- .slide: class="left-align smalltext" -->

**Technical Skills 03**

More **usability/accessibility**:

- Use good image `alt` attributes see [What is Alt Text?](https://moz.com/learn/seo/alt-text)
- [Keyboard Accessibility](https://webaim.org/techniques/keyboard/)—[tab order](https://webaim.org/techniques/keyboard/tabindex) is ONLY needed if the **default order is confusing** (try tabbing around your links). 
- **IGNORE** *tab Keyboard Shortcuts* in that article—they can clash with *system* shortcuts
- **Consistent navigation** throughout i.e. easy to **get anywhere from any page**
- Consistently-placed **menu and home link** throughout the site
- **Good link text**—never ~click here~! Use brief text about the link destination e.g. "more" is okay **once in a section**, but better to use “**more about (whatever)**”

[see Lecture 3: accessibility](https://tech3015.github.io/presents/?lecture-03#/5) and [slide in lecture 7 on colour and accessibility](https://tech3015.github.io/presents/?lecture-07#/3/1)

To **learn more about web accessibility** see the excellent [WebAIM](https://webaim.org/)

===

## DOCUMENTATION **01**
<!-- .slide: class="left-align" -->

40% of the coursework mark

1500-2000 words, references and appendices not included in word count

- [Design Process](https://tech3015.github.io/lectures/coursework-02.html#design-process)
- [Production](https://tech3015.github.io/lectures/coursework-02.html#production)
- [Evaluation](https://tech3015.github.io/lectures/coursework-02.html#evaluation)

---

## DOCUMENTATION **02**
<!-- .slide: class="left-align smalltext" -->

**Design Process**: refer back to mock-up designs and discuss:

- what has **changed** and why, or why your design **didn't need changes**!
- what you think your **main challenge(s)** were
- what you consider to be the **most important feature(s)** of your design
- Recall your own **design evaluation from CW1**, plus peer and tutor feedback

---

## DOCUMENTATION **03**
<!-- .slide: class="left-align smalltext" -->

**Production**: summarise the development of your website by (say) choosing three components, explaining:

- What you were **trying to achieve**
- How you **achieved it** in the end
- Why you **chose a certain approach**
- **How successful** the end result is, and/or what you might **do better** given more time (which you umm… *now have*)

An individual component of your website could be a **slideshow**, **dropdown menu**, a **social media feed**, **locaStorage data**, **animations**, etc.

---

## DOCUMENTATION **04**
<!-- .slide: class="left-align smalltext" -->

**Evaluation**: needs to cover:

- Evidence of **code testing** and **HTML validation**
- Evidence and a table (can be in the appendix) of **user testing** and **use of feedback**
- Evaluate your work, with reference to testing where appropriate, and user feedback, describing:
  - **limitations** of your website
  - **improvements** you would make to the site and why
  - **problems** you encountered and **solutions** you found (references) or devised

===

## **BAD** VS **GOOD** UI
<!-- .slide: class="left-align" -->

finally, a couple of links with some **useful examples**:

- [6 Bad UI Design Examples & Common Errors of UI Designers](https://www.mockplus.com/blog/post/bad-ui-design-examples)
- [Bad Design vs. Good Design: 5 Examples We can Learn From](https://www.interaction-design.org/literature/article/bad-design-vs-good-design-5-examples-we-can-learn-frombad-design-vs-good-design-5-examples-we-can-learn-from-130706)
