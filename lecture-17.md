<!-- .slide: class="centre" -->
# TECH3015 Lecture 17

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

## WE ARE STILL HERE
<!-- .slide: class="left-align" -->

- progress with making your site:
  - [**validate** your HTML](https://validator.w3.org/#validate_by_input)!
  - test your site at **all widths**
  - make sure your **breakpoints are in order**
  - think about **user interaction**
- use the CodeCademy courses to revise…

===

## ONLINE RESOURCES
<!-- .slide: class="left-align" -->

**Codecademy** free courses:

- [Learn HTML](https://www.codecademy.com/learn/learn-html)
- [Learn CSS](https://www.codecademy.com/learn/learn-css)
- [Learn how to build websites](https://www.codecademy.com/learn/paths/learn-how-to-build-websites)
- [Introduction to JavaScript](https://www.codecademy.com/learn/introduction-to-javascript)

===

## TYPOGRAPHY **01**
<!-- .slide: class="left-align" -->

> **95%** of the information on the web is **written language**. It is only logical to say that a web designer should get good training in the main discipline of **shaping written information**, in other words: **Typography**.
> 
> —Oliver Reichenstein, "[Web Design is 95% Typography](https://ia.net/topics/the-web-is-all-about-typography-period)”, 2006

---

## TYPOGRAPHY **02**
<!-- .slide: class="left-align" -->

> our harassed contemporaries simply **cannot take everything** that is printed today.
> 
> It is the typographer’s task to **divide up, organize** and **interpret this mass** of printed matter in such a way that **the reader** will have a **good chance of finding what is of interest**
>
> —Emil Ruder, famous Swiss typographer, 1969

---

## TYPOGRAPHY **03**
<!-- .slide: class="left-align crammed" -->

recommended **web typography primary sources**:

- [The Elements of Typographic Style Applied to the Web](http://webtypography.net/toc/)
- [Typography chapter, Web Style Guide](https://webstyleguide.com/9-typography.html)  
—Patrick J. Lynch and Sarah Horton, 2016

---

## TYPOGRAPHY **04**
<!-- .slide: class="left-align" -->

> Choosing a Typeface Is **Not Typography**

but here's a little inspiration: [Beautiful Web Type](http://hellohappy.org/beautiful-web-type/)

---

## TYPOGRAPHY **05**
<!-- .slide: class="left-align crammed" -->

optimum **line length for readablity** was supposed to be 50-75 characters…

…but [The Line Length Misconception](https://www.viget.com/articles/the-line-length-misconception/) draws on more recent research, although `line-spacing`, `letter-spacing` and `font-family` helps—see [Optimal Text Layout Line Length](https://www.paulolyslager.com/optimal-text-layout-line-length/)

…and the advice continues **in more detail** for **mobile devices** in [How To Set Perfect Line Lengths For The Web](http://www.simon-li.com/design-and-code/how-to-set-perfect-line-lengths-for-your-webpages/)

…and finally [Letterspacing Makes ALL CAPS Easier to Read](https://uxmovement.com/content/how-letterspacing-can-make-all-caps-easier-to-read/)

---

## TYPOGRAPHY **06**
<!-- .slide: class="left-align" -->

Use the following CSS properties to aid legibility:

- [line-height](https://www.w3schools.com/cssref/pr_dim_line-height.asp)
- [word-spacing](https://www.w3schools.com/cssref/pr_text_word-spacing.asp)
- [letter-spacing](https://www.w3schools.com/cssref/pr_text_letter-spacing.asp)

---

## TYPOGRAPHY **07**
<!-- .slide: class="left-align crammed smalltext" -->

how how many `h1` tags can you have?

- one set of `h1` tags per **sectioning root** or content section  
- these are "sectioning root elements":

```html
<article> <section> <aside> <nav>
```

- `h1` labels the **whole document** between opening `body` and first **sectioning root**
- an `h1` heading in a **content section** should be the **first heading** in that section
- with `h1` top of a content section, **other headings** in that section should **descend in order**, starting with `h2` to create a **structured document outline**

condensed from [The Truth About Multiple H1 Tags in the HTML5 Era](https://webdesign.tutsplus.com/articles/the-truth-about-multiple-h1-tags-in-the-html5-era--webdesign-16824)

---

## TYPOGRAPHY **08**
<!-- .slide: class="left-align crammed smalltext" -->

| Semantic Meaning | HTML Tag |
| --: | :-- | 
| [Headings](https://www.w3schools.com/tags/tag_hn.asp) |	`<h1>`, `<h2>` … `<h6>` |
| [Block quotation](https://www.w3schools.com/TAGS/tag_blockquote.asp) | `<blockquote>` |
| [Address](https://www.w3schools.com/tags/tag_address.asp) | `<address>` |
| [Abbreviation](https://www.w3schools.com/TAGS/tag_abbr.asp) (with `title` attribute) | `<abbr>` |
| [Defined term](https://www.w3schools.com/tags/tag_dfn.asp) | `<dfn>` |
| [Title of a work](https://www.w3schools.com/tags/tag_cite.asp) | `<cite>` |
| [Computer code](https://www.w3schools.com/TAGs/tag_code.asp) | `<code>` |
| [Emphasis](https://www.w3schools.com/tags/tag_em.asp) | `<em>` not ~`<i>`~ |
| [Strong emphasis](https://www.w3schools.com/tags/tag_strong.asp) | `<strong>` not ~`<b>`~ |

~`<acronym>`~, ~`<menu>` and ~`<dir>`~ are *not* supported in HTML5

---

## TYPOGRAPHY **09**
<!-- .slide: class="left-align crammed smalltext" -->

HTML **lists**:

| Semantic meaning | tag |
| --: | :-- | 
| [Unordered (bullet point) Lists](https://www.html-5-tutorial.com/ul-ol-tags.htm) |	`<ul>` |
| [Ordered (numbered) Lists](https://www.html-5-tutorial.com/ul-ol-tags.htm) |	`<ol>` |
| [Definition lists (title, description)](https://www.w3schools.com/TAGS/tag_dl.asp) | `<dl>` `<dt>` `<dd>` |

Definition lists are great for **title/description content**:

```html
<dl>
  <dt>Cat</dt>
    <dd>fluff, claws, whiskers, meowing…</dd>
  <dt>Caterpillar</dt>
    <dd>
      Middle English catirpel, catirpeller, probably  
      an alteration of Old North French catepelose
    </dd>
<dl>  
```
---

## TYPOGRAPHY **10**
<!-- .slide: class="left-align smalltext" -->

**only a few fonts** are on every computer (see [Typetester](http://classic.typetester.org/)).

A font on your computer may look fine in your browser **but** your website users **may not have that font**.

> It **looks fine** on **my computer**
>
> —*well-known moan* of novice web designers!

[Google fonts](https://fonts.google.com/) (and other services) allow you to **expand the range** of available **web typefaces** with the CSS property `@font-face`, but **only use them for headings**, NOT body text as they can be slow to load

---

## TYPOGRAPHY **11**
<!-- .slide: class="left-align crammed smalltext" -->

To use a specific font **local to your website** (and not depend on a Google fonts download), you also use `@font-face`

```css
@font-face {
  font-family: Chunkfive;
  src: url('Chunkfive.otf');
}
/* a font stack: */
font-family: Chunkfive, Georgia, Palatino, Times, serif;
```

This gives the custom font an **identifier** for the **rest of your CSS** and points to the **original font file** when this identifier is used in **other CSS style rules**

**Best format**: WOFF (OpenType or TrueType with compression and additional metadata) is the [most widely supported](https://www.w3schools.com/css/css3_fonts.asp) but OTF/TTF are also good.

- [Web Font Generator](https://www.web-font-generator.com/)
- [css @font-face generator (carful: more options!)](https://transfonter.org/)

---

## TYPOGRAPHY **12**
<!-- .slide: class="left-align" -->

type in CSS can be **sized** using several **different measures**, most commonly:

`em`, `%`, and `px` (ems, percentage and pixels).

```css
font-size: 1.5em;
font-size: 150%;
font-size: 12px;
```

`em`s are adjusted according to their **parent element** which makes for confusing **size variations**, so…

---

## TYPOGRAPHY **13**
<!-- .slide: class="left-align" -->

…the `rem` or "root em"—typically set on the `body`—allows for 'absolute' size adjustments with the **root** `font-size` **as a base** regardless of any other containing element's `font-size` style:

```css
body { font-size: 1em; } /* set the root (em or px) */
h1 { font-size: 2rem; } /* twice as big */
small { font-size: .75rem; } /* 3/4 size */
```

[Rems, ems, and pixels. What’s the difference? (Abbey Fitzgerald 2015)](https://getflywheel.com/layout/rems-ems-and-pixels-whats-the-difference/)

---

## TYPOGRAPHY **14**
<!-- .slide: class="left-align" -->

the default font for **form fields** as displayed by browsers is usually **smaller** and in a **different font** than the body text,  but you can make them the same using

```css
input, textarea {
  font-size: inherit;
  font-family: inherit;
}
```

or **manually set** the **font** and **font-size**

---

## TYPOGRAPHY **15**
<!-- .slide: class="left-align crammed" -->

You can divide text [into columns](https://developer.mozilla.org/en-US/docs/Web/CSS/columns) using CSS:

```css
.my-columns {
  column-count: 3;
}
```

there are a few settings: `column-gap`, `column-rule-style`, `column-rule-width`, `column-rule-color` or shorthand:

```css
column-rule: 1px solid lightblue;
```

[CSS Multiple Columns (W3Schools)](https://www.w3schools.com/Css/css3_multiple_columns.asp)

---

## TYPOGRAPHY **16**
<!-- .slide: class="left-align crammed" -->

you can highlight the entire [::first-line](https://www.w3schools.com/cssref/sel_firstline.asp) of a block of text:

```css
blockquote::first-line,
p::first-line {
  font-size: 1.25rem;
}
```

---

## TYPOGRAPHY **17**
<!-- .slide: class="left-align crammed" -->

… and use [::first-letter](https://www.w3schools.com/cssref/sel_firstletter.asp) to make a CSS `class` you can **apply** to **paragraphs** and **other elements** with **multiple lines of text**:

```css
.drop-cap::first-letter {
  font-size: 4.5rem;
  float: left;
  margin-top: .15em;
}
```

[DEMO: drop capital letter](https://front-end-materials.github.io/typography/drop-cap/) ([code here](https://github.com/front-end-materials/typography/tree/master/drop-cap))

See [CSS Drop Caps](https://www.abeautifulsite.net/css-drop-caps)

---

## TYPOGRAPHY **18**
<!-- .slide: class="left-align" -->

indent the **first line** of a text block with [text-indent](https://www.w3schools.com/cssref/pr_text_text-indent.asp)

```css
.indentme {
  text-indent: -2em;
}
```

---

## TYPOGRAPHY **19**
<!-- .slide: class="left-align" -->

**hyphenate** large chunks of text with [hyphens: auto;](https://www.w3schools.com/cssref/css3_pr_hyphens.asp) (default is `manual`, which only breaks on the minus `-` character)

```css
.hyphenated {
  hyphens: auto;
}
```

---

## TYPOGRAPHY **20**
<!-- .slide: class="left-align" -->

it's even possible to have vertical text: [writing-mode](https://www.w3schools.com/cssref/tryit.asp?filename=trycss3_writing-mode)

 although it may be better to **rotate** the **containing element**:

```css
.rotate90 {
  transform: rotate(90deg); /* note the `deg`! */
}
/* or -90deg */
```

---

## TYPOGRAPHY **21**

Two resources:

- [Tips For Setting Up A Baseline Grid (CSS, article)](https://vanseodesign.com/web-design/baseline-grid/)
- [Typesetting Body Text (loooong video lecture)](https://vimeo.com/156203722)

---

## TYPOGRAPHY **22**
<!-- .slide: class="left-align" -->

[BONUS DEMO: show an image inside text](https://front-end-materials.github.io/typography/image-as-text/) ([code here](https://github.com/front-end-materials/typography/tree/master/image-as-text))

===

**COOKIES**
<!-- .slide: class="crammed" -->

![No problem, you can track my data](https://raw.githubusercontent.com/TECH3015/lectures/master/imgs/humour/cookies-whatever.jpg)
