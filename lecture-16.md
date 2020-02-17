<!-- .slide: class="centre" -->
# TECH3015 Lecture 16

2019-2020

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

- **Term 1, Assignment 1:** DONE!
- **Term 2, Assignment 2:** HTML5, CSS3, JavaScript ES6, APIs, animation, [HTML validation](https://validator.w3.org/), accessibility testing, [Responsive Web Design](https://developers.google.com/web/fundamentals/design-and-ux/responsive/) and code, Progressive Web Apps

---

## ASSIGNMENT DEADLINES
<!-- .slide: class="left-align" -->

- **Assignment 2 (60%):**  
midday (12pm) Friday 3rd April 2020

[Full marking criteria for Coursework 2](https://tech3015.github.io/lectures/coursework-02.md#marking-criteria)

===

## WE ARE STILL HERE
<!-- .slide: class="left-align" -->

- progress with making your site:
  - **validate** your HTML!
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

<!-- JSON -->

# JSON: **01**
<!-- .slide: class="left-align smalltext" -->


a **JavaScript object** can contain any of these: `string`, `number`, `array`, `object`, `boolean` (true|false), `null` plus (unike JSON) **functions** and **comments**…

**JavaScript objects** are the basis of the **JSON data format**:

> JavaScript’s object-literal syntax is so simple, fexible, and concise, it was adapted to become the **dominant standard for client/server communication in the form of JSON**, which is more compact and flexible than the **XML** that it replaced.

— [Programming JavaScript Applications, Eric Elliott](https://www.ebooks.com/1719226/programming-javascript-applications/elliott-eric/)

---

# JSON: **02**
<!-- .slide: class="left-align smalltext" -->

JSON is a **compact plain-text portable data format**, read/writable (**parsed**) in many languages. It can be generated by **databases** as a data API, **translated** into/from (say) XML…

You can **use JSON data from many APIs** that offer **data** from **remote servers**: [news](https://open-platform.theguardian.com/access/), [weather](https://www.metoffice.gov.uk/datapoint), [Wikipeda](https://www.mediawiki.org/wiki/API:Main_page), [game statistics](https://www.programmableweb.com/category/games/apis?category=20098)…

[JSON Placeholder](https://jsonplaceholder.typicode.com/) has some good examples and can be used for development or learning. An **array of objects** is a common format.

For a more in-depth introduction to APIs in general, see [**"What Are APIs and How Do They Work?"** (ProgrammableWeb.com)](https://www.programmableweb.com/api-university/what-are-apis-and-how-do-they-work)

---

# JSON: **03**
<!-- .slide: class="left-align smalltext" -->

The [Discourse forum software](https://www.discourse.org/) generates a JSON API, viewable by **simply adding ".json"** to the end of a URL. Here’s a list of [discussions on the Three.js forum](https://discourse.threejs.org/c/discussion)…

![Discourse Three.js forum](https://raw.githubusercontent.com/TECH3015/lectures/master/imgs/json-api/discourse-three-js-forum.png)

---

# JSON: **04**
<!-- .slide: class="left-align smalltext" -->

…here’s the **JSON data** for a [Discourse forum](https://discourse.threejs.org/c/discussion.json)—for readability use a [JSON beautifier](https://beautifier.io/)

![Discourse Three.js forum JSON](https://raw.githubusercontent.com/TECH3015/lectures/master/imgs/json-api/discourse-raw-json.png)

---

# JSON: **05**
<!-- .slide: class="left-align smalltext" -->

…or a browser plug-in like the [Chrome extension JSONview](https://chrome.google.com/webstore/detail/jsonview/chklaanhfefbnpoihckbnefhakgolnmc)):


![Discourse Three.js forum JSON](https://raw.githubusercontent.com/TECH3015/lectures/master/imgs/json-api/discourse-three-js-forum-json.png)

---

# JSON: **06**
<!-- .slide: class="left-align smalltext" -->

in the JSON data for this forum, "users" is an **array** of **objects**, so if we fetch this data:

```js
{
  users: [
  {  
    id: 2,  
    username: "fraguada",  
    name: "Luis E. Fraguada",  
    avatar_template: "/user_avatar/discourse.[…].png"
  },
  {
    id: 1956,  
    username: "andreasplesch",  
//... MUCH MORE DATA!
```

…and assign it to a variable `test`,  
we can get user names from this Discourse forum with [map](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/map):

```javascript
test.users.map(u => u.username)
// ["fraguada", "andreasplesch", etc...]
```

---

# JSON **07**
<!-- .slide: class="left-align smalltext" -->

Rather than the older AJAX method, this code extract for The Guardian API uses `fetch`, with **promises** that **wait for a result** and only `.then` **do something**:

```js
//...
let theData;

fetch(data-to-fetch)
  .then(function (response) {
    // checks the if the response was okay
    console.log(`response: ${response.status}`);
    return response.json();
  })
  .then(function(data) {
    // check the raw JSON data in the console
    console.log(data);
    // assign it to a variable
    theData = data;
    // and do stuff with the data here
  })
```

- [JavaScript Promises: an Introduction (developers.google.com)](https://developers.google.com/web/fundamentals/primers/promises)
- [Promises, async/await (javascript.info)](https://javascript.info/async)

---

# JSON: **08**
<!-- .slide: class="left-align smalltext" -->

**JSON has no "parent" or variable assignment**—it starts with an opening `{` or `[`.  
This example of local JSON data (stored within a website in a file called, say, "menu.json") could build a special kind of menu:

```js
{
  "id": "file",
  "value": "File",
  "popup": {
    "menuitem": [
      {"label": "New", "url": "/new", "action": "createNewDoc()"},
      {"label": "Open", "url": "/open", "action": "openDoc()"},
      {"label": "Close", "url": "/close", "action": "closeDoc()"}
    ]
  }
}
```

however, JSON is **just data**! It *cannot* contain **functions** or **comments** like a JavaScript object…

---

# JSON: **09**
<!-- .slide: class="left-align smalltext" -->

…but JSON data *can* be assigned to a variable as a **JavaScript object** (e.g. a `const` if you know the type—object or array) to **store the JSON** for use on your website  
—you’d write code to *remove quotes* from the *function names* in the `action` values:

```js
const menu = getData() // get the menu.json here using fetch
removeQuotes(menu.popup.menuitem); // pass menuitem array to removeQuotes()
console.log(menu); // will then show:
{
  "id": "file",
  "value": "File",
  "popup": {
    "menuitem": [
      {"label": "New", "url": "/new", "action": createNewDoc()},
      {"label": "Open", "url": "/open", "action": openDoc()},
      {"label": "Close", "url": "/close", "action": closeDoc()}
    ]
  }
}
```

See: [Introducing JSON](http://www.json.org/ "ECMA-404 The JSON Data Interchange Standard") and
[JSON Basics: What You Need to Know](https://www.elated.com/articles/json-basics/)

---

# JSON: **10**
<!-- .slide: class="left-align smalltext" -->

for a real-world example, here’s the raw **JSON data** for the [current solar weather](https://services.swpc.noaa.gov/products/geospace/planetary-k-index-dst.json)  
This is often used to **predict aurora displays** in the Arctic Circle

![Solar data raw JSON](https://raw.githubusercontent.com/TECH3015/lectures/master/imgs/json-api/solar-raw-json.png)

---

# JSON: **11**
<!-- .slide: class="left-align crammed smalltext" -->

this solar weather data is in a **nested array**, with the first array as a **header row**:

```json
[
  ["time_tag", "planetary_k_index", "dst"],
  [
    "2018-11-13 00:00:00",
    "2.67",
    "-10.2685003"
  ],
  [ // much, much more data...
]
```

So you access the first `"time_tag"` date by starting at `[1][0]`,  
the `"planetary_k_index"` ([K-index](https://en.wikipedia.org/wiki/K-index)) data (`"2.67`) with `[1][1]`  
and the "dst" ([disturbance storm time](https://en.wikipedia.org/wiki/Disturbance_storm_time_index)) at `[1][2]`

Various other [space weather readings are freely available](https://services.swpc.noaa.gov/) from [noaa.gov](https://www.noaa.gov/)

---

# JSON **12**
<!-- .slide: class="left-align smalltext" -->

if the **data is stored** in a variable called `jsonData`, this `processData` function will get, format and display it  
`showData` is the ID of the element that will show… the data!

```js
const processData = () => {
  showData.innerHTML =
    <strong>Time:</strong> ${ jsonData[1][0] }
    <br><strong>K index:</strong> ${ jsonData[1][1] }
    <br><strong>distance of solar wind:
    </strong> ${ jsonData[1][2] }`;
}

getData.addEventListener("click", processData);
```

abbreviated for clarity. 

---

# JSON **13**
<!-- .slide: class="left-align" -->

- [Get and display live solar data from an API](https://front-end-materials.github.io/json-api/api-solar-data/)
- [download code](https://github.com/front-end-materials/json-api/tree/master/api-solar-data)
- [See the raw data here](https://services.swpc.noaa.gov/products/geospace/planetary-k-index-dst.json)

===

<!-- APIs -->

# API: **01**
<!-- .slide: class="left-align smalltext" -->

**Using APIs in your project**

- **show initiative** by presenting data in an interesting way
- you may need to **run your code** on a **server**
- you often need to apply for an **API key**
- there are good [social media APIs](https://www.programmableweb.com/news/top-10-social-apis-facebook-twitter-and-google-plus/analysis/2015/02/17)
- [Google Maps API](https://developers.google.com/maps/documentation/javascript/) now wants your credit card :-(

[What Is an API… Why Does It Matter? (M. Patterson 2015)](https://sproutsocial.com/insights/what-is-an-api/)  
[Search the Largest API Directory on the Web](https://www.programmableweb.com/category/Social/apis)

---

# API: **02**
<!-- .slide: class="left-align crammed smalltext" -->
				
**API Security**

- all **JavaScript is insecure** as it can be read from the browser
- if you store your API key in JavaScript, **anyone can read it**
- **not to worry**—this is **not a problem for your assignment**!

Extra info: **Just getting data** is fine, but if you're **sending new data** *to* an API, *anyone* could use your key, so it has to be secure. Most options store the key on the server or use [OAuth](https://oauth.net/ "An authorization framework enabling a third-party applications to obtain limited access to an HTTP service").

See: [how can you secure a JavaScript application's API calls](https://stackoverflow.com/a/18516778/123033)  
and [Securing API Keys in a Client Side JavaScript App](http://billpatrianakos.me/blog/2013/09/12/securing-api-keys-in-a-client-side-javascript-app/ "Bill Patrianakos, 2013")

---

# API: **02**
<!-- .slide: class="left-align crammed smalltext" -->
		
**Accessing APIs**

- browsers only allow access to files from the **same domain**
- you need a **local server** to access JSON files on your computer
- one way to allow access from **other domains** is [CORS](https://www.telerik.com/blogs/using-cors-with-all-modern-browsers "Cross-Origin Resource Sharing")

Cross-origin resource sharing (CORS) allows restricted resources (e.g. fonts) to be requested from other domains via secure cross-domain requests and data transfers between browsers and web servers. Modern browsers use CORS in an API container such as `XMLHttpRequest` or `Fetch` to reduce cross-origin HTTP request risks.

See: [Using CORS](https://www.html5rocks.com/en/tutorials/cors/), 
[CORS (MDN)](https://developer.mozilla.org/en-US/docs/Web/HTTP/CORS), [CORS in detail (Stack Overflow)](https://stackoverflow.com/a/43881141/123033)  

---

<!-- .slide: data-background-image="https://raw.githubusercontent.com/TECH3015/lectures/master/imgs/json-api/CORS_principle.png" data-background-size="contain" -->

===

## POSSIBLE NEXT TOPICS
<!-- .slide: class="left-align" -->

- **bad UI** design examples
- **typography** for the Web
- getting your **site live**
- **CSS grid** layout (possibly)

Anything else you want?