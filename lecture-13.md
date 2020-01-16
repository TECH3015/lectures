# TECH3015 Lecture 13

2019-2020

---

## MODULE TUTORS

- **Thom Corah** (Module Leader)  
Location: GH6.62  
Email: tcorah@dmu.ac.uk  
Tel: 0116 207 8088

- **Fania Raczinski** (labs)  
Email: fania.raczinski@dmu.ac.uk

- **Dave Everitt** (lectures)  
Email: deveritt@dmu.ac.uk


## MODULE STRUCTURE

- **Term 1, Assignment 1:** DONE!
- **Term 2, Assignment 2:** HTML5, CSS3, JavaScript ES6, APIs, animation, HTML validation, accessibility testing, Responsive Web Design and code, Progressive Web Apps


## ASSIGNMENT DEADLINES

- **Assignment 2 (60%):**  
midday (12pm) Friday 3rd April 2020

[Full marking criteria for Coursework 2](https://daveeveritt.github.io/TECH3015/coursework-02.md#marking-criteria)

---

## WHERE WE ARE

- progress with making your site:
  - test the basic structure at all widths
  - make sure your CSS styles are mobile-first
  - use only `min-width` breakpoints below mobile styles
  - think about interaction
- use the CodeCademy courses to revise…


## ONLINE RESOURCES

**Codecademy** has the following free courses:

- [Learn HTML](https://www.codecademy.com/learn/learn-html)
- [Learn CSS](https://www.codecademy.com/learn/learn-css)
- [Learn how to build websites](https://www.codecademy.com/learn/paths/learn-how-to-build-websites)
- [Introduction to JavaScript](https://www.codecademy.com/learn/introduction-to-javascript)

---

# JS **HOW IT WORKS**: 1
<!-- JAVASCRIPT: HOW IT WORKS -->

- translated into **machine instructions** by the **syntax parser**
- creates a **global execution context** in the browser window…
- …with `window` as the global object and `this` as a special variable
- runs in an **[event loop](#/4/5)** to check if **user events** need **action**

**global**: means available everywhere **in one window**

Try an empty browser tab (or blank .js file) e.g. type `this.innerWidth;` into an empty browser console


# JS **HOW IT WORKS**: 2

1. builds an **execution stack** to handle your code
2. executes your code **synchronously** (one thing at a time)
3. the browser adds user events (e.g. click) to an **event queue**
4. if the **execution stack** is empty…
5. …JavaScript **checks** the event queue for **actionable events**

The browser does things *asynchronously* (**rendering the page**, making **HTTP calls**, storing **user events** in the queue…) while JavaScript handles things *synchronously*…

…except for `async` (see [js Goes Async](https://www.sitepoint.com/javascript-goes-asynchronous-awesome/) and [MDN/async](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/async_function))


# JS **HOW IT WORKS**: 3

- use it to access the **Document Object Model** (DOM)
- **make changes** and **get information** from the DOM
- get data from JSON online and **style the result** 


Example:

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

See [Introduction to the DOM](https://developer.mozilla.org/en-US/docs/Web/API/Document_Object_Model/Introduction "Mozilla Web Docs")

---

# JS **HOW IT WORKS**: 4

![](images/dom-model.svg)

The first few branches on a **Document Object Model** (DOM) tree

There are **parent**, **child** and **sibling** nodes

From: [Document Object Model Structure](http://www.corelangs.com/js/dom/domtree.html) (corelangs.com)

---

## JS **HOW IT WORKS**: 5

![Document Object Model diagram with hand-drawn annotations](images/dom.png "From a JQuery course http://cs.wellesley.edu/~cs110/reading/DOM-JQ.html")

<!-- SHARED WITH MEDS2007 LECTURE 04 -->


# JS **HOW IT WORKS**: 6

## THE BROWSER EVENT LOOP

In a browser, everything runs in an **event loop** so you use **event listeners** to errr… **listen** for **events** triggered by the **user** or **other processes**:

``` javascript
myElement.addEventListener("click", MyFunction);
```


While **CSS** can be triggered by focus/hover/etc.  
**JavaScript** can listen for **hundreds** of events.

See: [Web Event reference (MDN)](https://developer.mozilla.org/en-US/docs/Web/Events)


<!-- .slide: class="crammed" -->
# JS **HOW IT WORKS**: 7

## How is JavaScript used?

- form **validation** of user input
- handling **data** (e.g. **JSON**)
- interactive **user interfaces** and feedback
- web-based **apps** (mobile and desktop)
- web and mobile **frameworks**
- **applications** built on web technologies
- **games** with HTML5 canvas ([HTML5 Games website](http://html5games.com/Best/702b9531-c136-437a-ab97-0b209d893b55))
- **3D animation** with canvas and WebGL ([F1 car](http://helloracer.com/webgl/), [Aquarium](http://webglsamples.org/aquarium/aquarium.html))

<!-- END SHARED WITH MEDS2007 LECTURE 04 -->

<!-- JAVASCRIPT SYNTAX -->
---

# JAVASCRIPT SYNTAX: **1**

## Blank console in Chrome:

- type `about:blank` in the address bar
- type in JavaScript and **try things** out
- **shift-return**: new line without executing

---

A demo, if there's time…

![console log for experimenting with JavaScript](images/chrome-about-blank.png)

---

# JAVASCRIPT SYNTAX: **2**

## **C-FAMILY** STYLE SYNTAX

familiar if you've used C-family languages:

``` javascript
const myArray = ["C", "C++", "Ruby", "R", "Go", "Rust"];

// These are not all C-family languages!
```
[Array methods (W3Schools)](http://www.w3schools.com/js/js_array_methods.asp)

---

# JAVASCRIPT SYNTAX: **3**

## DYNAMIC TYPING

- 6 **primitive types** (not objects):  
`undefined`, `null`, `boolean`, `number` (always a float), `string`, [`symbol` (ES6)](https://docs.microsoft.com/en-us/scripting/javascript/reference/symbol-object-javascript "For creating a unique identifier for object properties")
- JavaScript **works out the type** for a variable value
- you can change a `let` value from **one type to another**

---

# JAVASCRIPT SYNTAX: **4**

### VARIABLES (`var`), `let`, `const`

```javascript
let greet, helloUser; // initialise two variables
greet = "hello";  // assign a value
let userInput = // get user input from the DOM  
helloUser = `Oh, ${greet} ${userInput}`;

let myVar = // can be: string, number, boolean
const myVar = // can be: array, object, function…

myVar === myVar01; // true if the same
myVar !== myVar01; // true if different
```

`const` can store an **immutable type** (e.g. array, function), the **elements** or **properties** of which can change.

We will see that `let` has **tighter scope** than `var`…

---

# JAVASCRIPT SYNTAX: **5**

## VARIABLE scope: **var** and **let**

```javascript
function demoLet() {
  //tuce is *not* visible out here
  for( let tuce = 0; tuce < 5; tuce+=1 ) {
    //tuce is only visible in here (in the for())
  }
  //tuce is *not* visible out here
}
function demoFor() {
  //nish *is* visible out here
  for( var nish = 0; nish < 5; nish++ ) {
    //nish is visible to the whole function
  }
  //nish *is* visible out here
}
```
[…difference between using “let” and “var” to declare a variable?](http://stackoverflow.com/a/11444416/123033)

---

# JAVASCRIPT SYNTAX: **6**

## FUNCTIONS

function **declaration** || **expression** (as a `const` variable):

```javascript
function multiplyNums(x, y) {
  return x * y;
} // function declaration

// function expression (as an arrow function)
const multiplyNums = (x, y) => x * y;
```

Nearly everything in JavaScript is an **object**, including functions which can be used _as variables_ **including function call parameters**. ([MDN functions](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Functions))

---

# JAVASCRIPT SYNTAX: **7**

## **ARROW** FUNCTIONS: **COMPACT**

```javascript
const multiplyNums = (x, y) => x * y;

const square = x => multiplyNums (x, x);
square(8);

const squares = [1,2,3,4,5];
squares.map(num => square(num));
// [1, 4, 9, 16, 25] much better than a for loop!
```

…so you can use **function composition**, with **pure functions** (same input \> same output, self-contained).

[MDN arrow functions](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Functions/Arrow_functions)

---

# JAVASCRIPT SYNTAX: **8**

## **PURE** FUNCTIONS: **COMPACT** AND **SAFE**

```javascript
const hexagrams = square(8); // hexagrams is 64

console.log(`I Ching: always ${hexagrams} hexagrams!`);
// I Ching: always 64 hexagrams!
```

A pure function with **parameters** in a template literal:

```javascript
console.log(`This is not a ${square(4)}-bit laptop!`);
// This is not a 16-bit laptop!
```

---

# JAVASCRIPT SYNTAX: **9**

## **GENERATOR** FUNCTIONS\*

Example: a simple counter limiter:

```javascript
function* count () {
  let index = 1;
  while (index < 4) {
    yield index++;
  }
}
const upTo3 = count();

upTo3.next(); // value: 1, done: false
upTo3.next(); // value: 2, done: false
upTo3.next(); // value: 3, done: false
upTo3.next(); // value: undefined, done: true
```

---

# JAVASCRIPT SYNTAX: **10**

## JavaScript [Math](https://developer.mozilla.org/en/docs/Web/JavaScript/Reference/Global_Objects/Math "Moxilla Developer Netwrork detailed JS Math Reference") Object e.g.

```javascript
Math.round(4.5); // 5
Math.pow(8,2); Math.sqrt(64); // 64, 8
Math.abs(-4.7); // 4.7
Math.ceil(4.4); Math.floor(4.7); // 5, 4
Math.max(0, 150, 30, 20, -8, -200); // 150 (and min)
Math.random(); // a float from 0 to (almost) 1
Math.floor(Math.random() * 10); // number between 0 and 9
```

if you get `NaN` and you (know/want/think it is) a number:  
```javascript
parseFloat(aFloatYouThink); parseInt(AnIntegerYouThink);
```

Read W3Schools: [JavaScript Math Reference](http://www.w3schools.com/jsref/jsref_obj_math.asp),  
[JavaScript Number Methods](http://www.w3schools.com/js/js_number_methods.asp), 
[JavaScript Type Conversion Table](http://www.w3schools.com/jsref/jsref_type_conversion.asp)

---

# JAVASCRIPT SYNTAX: **11**

### Array **[…]**

'array literal' - create and populate:

```javascript
const myArray = [1, 2, "free",  multiplyNums(8, 8)];
myArray[3]; // 64
```

**No comma** after the **last element**!

```javascript
myArray[3] = multiplyNums; // no parameters
myArray[3](2, 2); // 4
```

**omit trailing brackets()** in functions with **no parameters** when inside an array - you can pass them later

---

# JAVASCRIPT SYNTAX: **12**

### OBJECT **{…}** (ASSOCIATIVE ARRAY)

Contains **key value** pairs. This is declared as an 'object literal':  

```javascript
const myObject = {key1: 64, key2: "text"};
```

Access/change: **square brackets** or **dot** (property) syntax:
```javascript
alert(myObject['key2']); // [] syntax… but dot is best:
alert(myObject.key2); // key2 is a property of myObject
myObject.key2 = 'More text'; // change the value of key2
```

add a new key/value pair:  
```javascript
myObject.key3 = Math.PI;
```

---

# JAVASCRIPT SYNTAX: **13**

**Object keys** _look_ like names (as in variables), but *keys are strings*, which allow expressions such as:

```javascript
let myKey = 2;

console.log(myObject["key"+myKey]);
console.log(myObject["key"+2]);
console.log(myObject["key2"]); // same as both above
```

Key strings (as in **JSON**) mean JavaScript loose typing turns `"key"+2` to `"key"+"2"`, evaluating to the string `"key2"`

```javascript
var myObject = {
  "key1": 64,
  "key2": "text"
};
```

---

# JAVASCRIPT SYNTAX: **14**

## conditionals

```javascript
if (condition is true) {
  // do stuff once here
}
```

```javascript
if (condition is true) {
  // do stuff
} else {
  // condition is false, do other stuff
}
```

---

# JAVASCRIPT SYNTAX: **15**

## LOOPS **1** (FOR)
```javascript
for (counter; condition; increment/decrement) {
  // do stuff using the counter
}
```

```javascript
for (let i = 0; i < myArray.length; i += 1) {
  console.log(myArray[i]);
}
```

…but `map` with an **anonymous function** is cleaner:

```javascript
myArray.map(i => console.log(i));
```

---

# JAVASCRIPT SYNTAX: **16**

## LOOPS **2** (WHILE)

```javascript
while (condition is true) {
  // do stuff until it's false
}
```

or

```javascript
do {
  // some stuff at least once, then…
}
while (condition); // …do it again IF condition is true
```

---

# JAVASCRIPT SYNTAX: **17**

## SWITCH/CASE

```javascript
switch (new Date().getDay()) {
  case 6:
    text = "Today is Saturday";
  break; 
  case 0:
    text = "Today is Sunday";
  break; 
  default: 
    text = "Looking forward to the Weekend";
}
```

[W3Schools switch statment](http://www.w3schools.com/js/js_switch.asp)

---

# JAVASCRIPT SYNTAX: **18**

## **OBJECT**===ES6 **CLASS** (+SYNTACTIC SUGAR)

> JavaScript uses a **prototypal inheritance model** with **object prototypes** as "classes". New objects inherit methods and attributes of their parent object through the prototype chain. It’s possible to modify an object’s prototype at any time, making JavaScript very flexible and dynamic.

[ES6 classes and JavaScript prototypes (Sebastian Porto)](https://reinteractive.com/posts/235-es6-classes-and-javascript-prototypes)  
**But** [Think twice about ES6 classes (Christian Alfoni)](http://christianalfoni.github.io/javascript/2015/01/01/think-twice-about-classes.html)

