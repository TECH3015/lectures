# TECH3015 Lecture 13

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

## WHERE WE ARE

- progress with making your site:
  - **validate** your HTML!
  - test your site at **all widths**
  - make sure your **breakpoints are in order**
  - think about **user interaction**
- use the CodeCademy courses to revise…

===

## NEXT LECTURES

The next few lectures will focus on **JavaScript**

This will give you a thorough introduction, some **examples and demos** to help, and hopefully **spark some ideas** about how you can use JavaScript to create some **interactive features** for your project

===

<!-- .slide: class="crammed" -->
## JAVASCRIPT USE: 1

How is JavaScript used?

- form **validation** of user input
- handling **data** (e.g. **JSON**)
- interactive **user interfaces** and feedback
- web-based **apps** (mobile and desktop)
- web and mobile **frameworks**
- **applications** built on web technologies
- **games** with HTML5 canvas ([HTML5 Games website](http://html5games.com/Best/702b9531-c136-437a-ab97-0b209d893b55))
- **[3D animations](https://tutorialzine.com/2013/09/20-impressive-examples-for-learning-webgl-with-three-js)** with canvas and WebGL e.g. [cars](http://carvisualizer.plus360degrees.com/threejs/), [Aquarium](http://webglsamples.org/aquarium/aquarium.html)

---

## JAVASCRIPT USE: 2

There are various ways to use JavaScript:

- use it to access the **Document Object Model** (DOM)
- **make changes** and **get information** from the DOM
- to add **user interaction** and **store preferences**
- to fetch online JSON data (and **style the result**)

===

<!-- JAVASCRIPT: HOW IT WORKS -->

## JS **HOW IT WORKS**: 1
<!-- .slide: class="crammed" -->

- translated into **machine instructions** by the **syntax parser**
- creates a **global execution context** in a browser window…
- …`window` is the global object and `this` is a special variable
- runs in an **event loop** to check if **user events** need **action**

<small>**global**: means available everywhere **in one window**</small>

Try an empty browser tab (`about:blank` in the address bar) and e.g. type `this.innerWidth;` into the browser console

---

## JS **HOW IT WORKS**: 2
<!-- .slide: class="crammed" -->

1. builds an **execution stack** to handle your code
2. executes your code **synchronously** (one thing at a time)
3. the browser adds **user events** (e.g. click) to an **event queue**
4. if the **execution stack** is empty…
5. …JavaScript **checks** the **event queue** for **actionable events**

<small>The browser does things *asynchronously* (**rendering the page**, making **HTTP calls**, storing **user events** in the queue…) while JavaScript handles things *synchronously* (one at a time)…<br><br>
…except for `async` (see [js Goes Async](https://www.sitepoint.com/javascript-goes-asynchronous-awesome/) and [MDN/async](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/async_function))</small>

---

## JS **HOW IT WORKS**: 3

JavaSript accesses the **Document Object Model** (DOM) tree, just like CSS

There are **parent**, **child** and **sibling** nodes

<small>From: [Document Object Model Structure](http://www.corelangs.com/js/dom/domtree.html) (corelangs.com)</small>

---

## JS **HOW IT WORKS**: 4

![Document Object Model diagram with hand-drawn annotations](https://raw.githubusercontent.com/DaveEveritt/TECH3015/master/imgs/javascript/dom.png)

---

## JS **HOW IT WORKS**: 5

## THE BROWSER EVENT LOOP

In a browser, everything runs in an **event loop** so you use **event listeners** to errr… **listen** for **events** triggered by the **user** or **other processes**:

``` javascript
myElement.addEventListener("click", MyFunction);
```

---

## JS **HOW IT WORKS**: 6

While **CSS** can be triggered by focus/hover/etc.  
**JavaScript** can listen for **hundreds** of events.

See: [Web Event reference (MDN)](https://developer.mozilla.org/en-US/docs/Web/Events)

===

<!-- <h2><strong>JS HOW IT WORKS</strong>: 9</h2> -->
## JS **EXAMPLE**: 1

A simple example:

```css
a.highlight {
 background: yellow;
}
```
```js
const myLinks = document.getElementsByTagName('a');

for(i=0; i < myLinks.length; i++){
  myLinks[i].classList.add("highlight");
}
```

<small>MDN: [Introduction to the DOM](https://developer.mozilla.org/en-US/docs/Web/API/Document_Object_Model/Introduction "Mozilla Web Docs")</small>

---

## JS **EXAMPLE**: 2

[`querySelector()`](https://www.w3schools.com/jsref/met_document_queryselector.asp) enables us to be more specific  
and to to use *CSS-style selectors*:

<a href="#" class="showme">

```js
const myLinks = document.querySelector(".showme");

for(i=0; i < myLinks.length; i++){
  myLinks[i].classList.add("highlight");
}
```

See a more detailed [demo that fades link colours in/out](https://front-end-materials.github.io/js-simple-examples/js-change-element/)

<!-- TODO: SHARE WITH MEDS2007 LECTURE 04 -->

===

**JAVASCRIPT IS WEIRD**
<!-- .slide: class="crammed" -->

![Javascript is weird](https://raw.githubusercontent.com/TECH3015/lectures/master/imgs/humour/js-banana.png)
