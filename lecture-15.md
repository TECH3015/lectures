<!-- .slide: class="centre" -->
# TECH3015 Lecture 15

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

## WE ARE STILL HERE

- progress with making your site:
  - **validate** your HTML!
  - test your site at **all widths**
  - make sure your **breakpoints are in order**
  - think about **user interaction**
- use the CodeCademy courses to revise…

===

# LOCAL STORAGE: **1**
<!-- .slide: class="crammed" -->

Browsers have **their own storage**, similar to cookies.

The easiest of these is called: `localStorage`

- it’s for **small amounts** of data (5Mb)
- it stores data in **key: value** pairs

<small>
`localStorage` is **insecure** (so not good for ~~sensitive data~~ - see [Please Stop Using Local Storage](https://dev.to/rdegges/please-stop-using-local-storage-1i04)).  
However, it’s **fine for non-critical data** like user preferences.
</small>

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
We don’t know what most of those are for!

---

# LOCAL STORAGE: **4**
<!-- .slide: class="crammed" -->

Example: set a localStorage item from a **field value**:

```javascript
const theName = document.getElementById("name-field");

localStorage.setItem("name", theName.value);

myElementId.innerText = localStorage.getItem("name");
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

where `myFunction` handles **actions** on `localStorage` data.

---

# LOCAL STORAGE: **6**
<!-- .slide: class="crammed" -->

Putting data **in** and getting it **out** of `localStorage` needs two **built-in JSON functions**:

- **JSON.stringify** takes a JavaScript data *object* and turns it into a *string* (see [stringify](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/JSON/stringify))
- **JSON.parse** gets a *string* from localStorage and turns it into an *object* (see [parse](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/JSON/parse))

===

# **DEMOS**

- [Store a name with local storage from an input form](https://front-end-materials.github.io/local-storage/local-storage-form/)  
[view code](https://github.com/front-end-materials/local-storage/tree/master/local-storage-form)

- [store multiple names in localStorage](https://front-end-materials.github.io/local-storage/local-storage-object/)  
[view code](https://github.com/front-end-materials/local-storage/tree/master/local-storage-object)

- [Checking Local Storage capacity with `StorageManager`](https://front-end-materials.github.io/local-storage/browser-storage-check/)
[view code](https://github.com/front-end-materials/local-storage/tree/master/browser-storage-check/)

===

**WISDOM**
<!-- .slide: class="crammed" -->

This.

![Things aren't always black & white](https://raw.githubusercontent.com/TECH3015/lectures/master/imgs/humour/not-black-and-white.jpg)
