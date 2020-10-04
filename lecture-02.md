# TECH3015 Lecture 2

2020/21

===

## Module Tutors

- **Thom Corah** (Module Leader)  
Location: GH6.62  
Email: tcorah@dmu.ac.uk  
Tel: 0116 207 8088

- **Dave Everitt** (lectures)  
Email: deveritt@dmu.ac.uk

- [Module handbook](https://tech3015.github.io/lectures/module-handbook.html)

===

## Where we are

- **planning** your site
- **refreshers** for web code 

The **links** within the lecture slides are **important**!

===

## HTML5 structure

**Every site** on the web has this **basic structure**!

```html
<!doctype>
<html>
  <head>
    <title>page name here</title>
    <!-- link to CSS in head section before page load: -->
    <link rel="stylesheet" href="mystyles.css">
  </head>
  <body>
    <!-- everything you see is inside the body tag -->
    <!-- add link to JavaScript after page load: -->
    <script src="js/myscripts.js"></script>
  </body>
</html>
```

===

## Planning your site 01

gather all the **content** for your site:

- images
- movies
- text (see [Writing for the Web](https://www.usability.gov/how-to-and-tools/methods/writing-for-the-web.html))
- audio
- possible data from APIs

===

## Planning your site 02

Arrange your content into *logical groups*

**THINK:** will a section be **limited** or **grow in content**?

Resources from [usability.gov](https://www.usability.gov/):

- [Content Strategy Basics](https://www.usability.gov/what-and-why/content-strategy.html)
- [Content Inventory](https://www.usability.gov/how-to-and-tools/methods/content-inventory.html)
- [Information Architecture](https://www.usability.gov/what-and-why/information-architecture.html)

===

## Planning your site 03

Collecting and sorting your content will provide the **outline** for your site structure and **navigation**

[Card Sorting](https://www.usability.gov/how-to-and-tools/methods/card-sorting.html "a good article introducing card sorting from usability.gov") is a method devised to help you arrange your website content

It works best when **other people** are invited—you can use [online card sorting software](https://www.optimalworkshop.com/optimalsort) ([free plan here](https://www.optimalworkshop.com/register))

===

## Planning your site 04

At the next stage, you will use **[HTML5 semantic tags](https://www.w3schools.com/html/html5_semantic_elements.asp)** to **mark up** the basic areas for:

- each of your site pages **main areas**
- each **kind** of page you have or...
- for one long **scrolling** page

===

## Planning your site 05

First, **HTML5 semantic tags** give **structure**:

- `header` (optional but advised)
- `nav`
- `main`
- `footer` (optional)

**Avoid div tags** and **don't** invent tags e.g. &lt;~~heading~~&gt;!

HTML5 semantic tags for **content** come later

===

## CSS: breakpoints 01

CSS **media queries** can *respond* to many factors:

- print
- width/height
- orientation
- speech
- light-level
- many more...

Full list: [Using media queries (MDN)](https://developer.mozilla.org/en-US/docs/Web/CSS/Media_Queries/Using_media_queries)

===

## CSS: breakpoints 02

**However** we only need `screen` and `min-width` e.g.

```css
@media only screen and (min-width: 600px) {
  body {
    background-color: lightblue;
  }
}
```

This is the basis of **Responsive Web Design**

See some [examples of RWD (mediaqueri.es)](https://mediaqueri.es/)

===

## CSS: breakpoints 03

Use **one** CSS style sheet for your **whole site**!

Put **general** and **mobile** styles first, at the top,  
**above** and **before** any **media queries**

===

## RWD: breakpoints 04

**Arrange your CSS file** like this example:

```css
/* mobile and general styles come first: */
main { background: rgb(200,200,160); }
p { color: #226; }
/* more styles... */

/* above mobile styles go inside 'breakpoints': */
@media only screen and (min-width: 600px) {
  /* override mobile styles and set
  styles for wider screens e.g. */
  main { background: rgb(240,240,200); }
  p { color: #003; }
} /* DO NOT forget the closing bracket!! */
```

===

## SUMMARY

- some code **refreshers**
- choosing your website **subject**
- some tools to help **plan your site**

If you **change the idea for your website** later, it's okay although you will need to justify this with your tutor.

===

## Questions

Please contact **Thom Corah, module leader**

If there's anything I can answer too, he'll contact me!
