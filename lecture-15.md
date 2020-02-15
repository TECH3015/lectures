<!-- .slide: class="centre" -->
# TECH3015 Lecture 15

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

- **Term 1, Assignment 1:** DONE!
- **Term 2, Assignment 2:** HTML5, CSS3, JavaScript ES6, APIs, animation, [HTML validation](https://validator.w3.org/), accessibility testing, [Responsive Web Design](https://developers.google.com/web/fundamentals/design-and-ux/responsive/) and code, Progressive Web Apps

---

## ASSIGNMENT DEADLINES

- **Assignment 2 (60%):**  
midday (12pm) Friday 3rd April 2020

[Full marking criteria for Coursework 2](https://daveeveritt.github.io/TECH3015/coursework-02.md#marking-criteria)

===

## WE ARE STILL HERE

- progress with making your site:
  - **validate** your HTML!
  - test your site at **all widths**
  - make sure your **breakpoints are in order**
  - think about **user interaction**
- use the CodeCademy courses to revise…

===

## ONLINE RESOURCES

**Codecademy** free courses:

- [Learn HTML](https://www.codecademy.com/learn/learn-html)
- [Learn CSS](https://www.codecademy.com/learn/learn-css)
- [Learn how to build websites](https://www.codecademy.com/learn/paths/learn-how-to-build-websites)
- [Introduction to JavaScript](https://www.codecademy.com/learn/introduction-to-javascript)

===

# LOCAL STORAGE: **1**
<!-- .slide: class="crammed" -->

Browsers have **their own storage**, similar to cookies.

In this module, we're using one of the storage functions: `localStorage`

- it’s for **small amounts** of data (5Mb)
- it stores data in **key value** pairs

`localStorage` is **insecure** (so not good for ~~sensitive data~~ - see [Please Stop Using Local Storage](https://dev.to/rdegges/please-stop-using-local-storage-1i04)).  
However, it’s still **good for non-critical data**.

---

# LOCAL STORAGE: **2**
<!-- .slide: class="crammed" -->

**Setting** and **getting** data:

```javascript
localStorage.setItem("name", "Dave");
localStorage.getItem("name"); // Dave
```

**Changing** data: **basic syntax**:

```javascript
localStorage["name"] = "Fania";
console.log(localStorage["name"]); // Fania
```

---

# LOCAL STORAGE: **3**
<!-- .slide: class="crammed" -->

Instead of using *cookies*, many websites now use **local storage** to keep small amounts of **data between visits**. It can:

- **store user preferences** 
- **personalise each visit**

You can **see what a website stores** in your own browser:

- open the **web inspector**
- select the **"Application" tab**…

---

![local storage in the browser Application tab](https://raw.githubusercontent.com/DaveEveritt/TECH3015/master/imgs/localstorage//local-storage-application-tab.png)

---

**Facebook** uses `localStorage` for several settings:

![Facebook local storage](https://raw.githubusercontent.com/DaveEveritt/TECH3015/master/imgs/localstorage/local-storage-facebook.png)

You can see stored **objects** (`{…}`) and **arrays** (`[…]`)  
We don’t know what most of those are!

---

# LOCAL STORAGE: **4**
<!-- .slide: class="crammed" -->

Example: set a localStorage item from a **field value**:

```javascript
const theName = document.getElementById("name-field");

localStorage.setItem("name", theName.value);

myElement.innerText = localStorage.getItem("name");
```

---

# LOCAL STORAGE: **5**
<!-- .slide: class="crammed" -->

You can **remove** an item from `localStorage` or **clear all**:

```javascript
localStorage.removeItem("name");
localStorage.clear();
```

Attach an `eventListener` to use the data on **another page**:

```javascript
localStorage.addEventListener("change", myFunction);
```

`myFunction` handles **actions** on the `localStorage` data.

**NOTE** [browser support is still patchy for LocalStorage events](https://stackoverflow.com/a/6846158/123033)

===

# DEMOS

- [Store a name with local storage from an input form](https://front-end-materials.github.io/local-storage/js-local-storage-form/)  
[view code](https://github.com/front-end-materials/local-storage/tree/master/js-local-storage-form)

- [store multiple names in localStorage](https://front-end-materials.github.io/local-storage/local-storage-object/)  
[view code](https://github.com/front-end-materials/local-storage/tree/master/local-storage-object)
