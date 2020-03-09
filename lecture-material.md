===

# Web 3D

[X3D Version 4 Overview](https://www.web3d.org/x3d4)

===

# JS: THE CONSOLE

there are a few functions to help debug your JavaScript problems

you can use most of them in your code to print out results in the console

- […JavaScript debugging tips](https://raygun.com/javascript-debugging-tips 'clickbait title abbreviated!')
- [Console API Reference (Google Developers)](https://developers.google.com/web/tools/chrome-devtools/console/api)

---

# JS: CONSOLE TESTING

Instead of `console.log()` You can use `console.assert()` to test whether something came out as you intended

```js
let value = 10;
console.assert(value <= 7, 'The value is greater than 7.');

value = 6; // passes test, no message

value = 7.01
'Assertion failed: The value is greater than 7.'
```

---

# JS: CONSOLE TABLE

If you find an object hard to read in the console, you can use `console.table();`

```js
var animals = [
  { animal: 'Pangolin', name: 'Julie', age: 43 },
  { animal: 'Armadillo', name: 'Inez', age: 13 },
  { animal: 'Platypus', name: 'Frodo', age: 120 }
];

console.table(animals);
```

!['output from console.table'](javascript/console.table.png)

`console.dir(animals);` is also more readable than `console.log(animals)`

---

# JS: CONSOLE TRACE

trace which thing called what, and in which order

```html
<button onclick="myFunction()">Start Trace</button>
```

```js
function myFunction() {
  myOtherFunction();
}

function myOtherFunction() {
  console.trace();
}
```

---

# JS: CONSOLE TIME

how long does something take?

add `console.time()` before and `console.timeEnd()` after

```js
const items = [1, 2, 3, 4, 5, 6, 7, 8, 9];

console.time()
let count = 0;
let len = items.length;
for(count; count < len; count++) {
  items[count * 10];
}
console.timeEnd() // 55282.25ms

console.time()
items.map(item => item * 10);
console.timeEnd() // 0.030029296875ms
```

<!-- is this in CTEC3905?? -->

---

# JS: CONSOLE VARS

e.g. `console.log($0);`

- `$0` currently selected element
- `$1` previous element
- `$2`, `$3`, `$4` element before previous, etc.
- `$(‘css-selector’)` return the first match for any selector
- `$$(‘css-selector’)` return all matches for any selector

[A Guide To Console Commands](https://css-tricks.com/a-guide-to-console-commands/)

---

# JS: DEBUGGER

enables you to add a **breakpoint**, then **step** through code, **track variable values**, etc.

```js
function potentiallyBuggyCode() {
  debugger;
  // do potentially buggy stuff, examine, step through, etc.
}
```

`debugger;` isn't part of the browser console object, but the **console will respond** to it from within JavaScript code

===

# JS: STYLE GUIDE

some style guides are extremely long and a little bit too wordy, so…

[W3Schools has a good, brief style guide](https://www.w3schools.com/js/js_conventions.asp)

===

## BAD UI

https://www.mockplus.com/blog/post/bad-ui-design-examples

https://www.interaction-design.org/literature/article/bad-design-vs-good-design-5-examples-we-can-learn-frombad-design-vs-good-design-5-examples-we-can-learn-from-130706

===

## DEMOS

- Dense grid https://codepen.io/faniae/pen/QWWoZem
- CSS filter https://codepen.io/fania/pen/xBEZBz

===

## CAROUSELS?

http://shouldiuseacarousel.com/

===

## KINDS OF WEBSITE **01**
<!-- .slide: class="crammed" -->

- dynamic
- static
- responsive (RWD)
- progressive (PWA)

===

## MOBILE APP ICONS
<!-- .slide: class="crammed" -->

- [50 Beautiful Mobile App Icons for Design Inspiration](https://speckyboy.com/mobile-app-design-inspiration/)


