===

[Multi-touch Web Development](https://www.html5rocks.com/en/mobile/touch/)

===

## KINDS OF WEBSITE **01**
<!-- .slide: class="crammed" -->

- dynamic
- static
- single page (SPA)
- responsive (RWD)
- progressive (PWA)

===
<!-- JavaScript debugging 13oct2020:  -->

## JS DEBUG 1:

### THE CONSOLE

there are a few functions to help **debug** your **JavaScript problems**

you can use some in your code to print out results in the console

- […JavaScript debugging tips](https://raygun.com/javascript-debugging-tips 'clickbait title abbreviated!')
- [Console API Reference (Google Developers)](https://developers.google.com/web/tools/chrome-devtools/console/api)

---

## JS DEBUG 2:

### CONSOLE TESTING

Instead of `console.log()` You can use `console.assert()` to test whether something came out as you intended

```js
let value = 10;
console.assert(value <= 7, 'The value is greater than 7.');

value = 6; // passes test, no message

value = 7.01
'Assertion failed: The value is greater than 7.'
```

---

## JS DEBUG 3:

### CONSOLE TABLE

To show an object neatly in the console, use `console.table();`

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

## JS DEBUG 4:

### CONSOLE TRACE

trace **which thing called what**, and in **which order**

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

## JS DEBUG 5:

### CONSOLE TIME

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

## JS DEBUG 6:

### CONSOLE VARS

e.g. `console.log($0);`

- `$0` currently selected element
- `$1` previous element
- `$2`, `$3`, `$4` element before previous, etc.
- `$(‘css-selector’)` return the first match for any selector
- `$$(‘css-selector’)` return all matches for any selector

[A Guide To Console Commands](https://css-tricks.com/a-guide-to-console-commands/)

---

## JS DEBUG 7:

### DEBUGGER

Add a **breakpoint**, then **step** through code, **track variable values**, etc.

```js
function potentiallyBuggyCode() {
  debugger;
  // potentially buggy code: examine, step through, etc.
}
```

`debugger;` isn't part of the browser console object, but the **console will respond** to it from within JavaScript code

<!-- END JavaScript debugging  -->

===

## DEMO

- [Dense grid](https://codepen.io/faniae/pen/QWWoZem)

===

## DEMO

- [CSS filter](https://codepen.io/fania/pen/xBEZBz)

===

## CAROUSELS?

http://shouldiuseacarousel.com/

===

