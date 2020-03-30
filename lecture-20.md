<!-- .slide: class="centre" -->
# TECH3015 Lecture 20

2019-2020

===

# CORONA VIRUS
<!-- .slide: class="left-align smalltext" -->

COVID-19 has meant **all teaching is now online**

- Fania will be present in the BlackBoard **[Online Classroom](https://vle.dmu.ac.uk/webapps/collab-ultra/tool/collabultra?course_id=_550284_1&mode=cpview)**  
  for the **remaining labs on Tuesdays at 4-6pm**
- Please **be patient with emails**, we have **many queries** across modules!
- **Visit** your **public_html folder** in a **browser** to be sure we can **see the web files**

If you **do not attend online** even briefly, **response to desperate late emails will be limited** as we also teach on *many other modules*, which have deadlines too!

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

## LIVE WEBSITES **01**
<!-- .slide: class="left-align" -->

There a few different parts to setting up a live site, and they **don't always play well together**!

- access to a **web server** to host your **website files**
- a good, memorable **domain name**
- [FTP software](https://cyberduck.io/) to **upload your files** to the server
- a modest sum of **money to cover costs**
- an optional **SSL certificate** (for some purposes)

---

## LIVE WEBSITES **02**
<!-- .slide: class="left-align smalltext" -->

### **WEB SERVERS**

are **computers linked to the internet** as part of the **World Wide Web** network, and typically managed by companies that maintain and manage access

**Shared Hosting** is where people have **separate logins** and **user spaces** on **one server**. Costs range from free to above £50 p.a. Some **domain providers** also offer hosting

- Choose a plan with **24/7 support** - you'll need it
- Choose a **Linux**—not a Windows—server (trust us on this!)

You may have some **web space** with your **Internet Service Provider** (ISP) - check if they **allow you** to use **your own domain name**

- [TechRadar review of free and cheap hosting](https://www.techradar.com/uk/web-hosting/best-free-web-hosting)
- [7 “Best” Free Hosting Sites (some on commission)](https://hostingfacts.com/free-web-hosting-sites/)

---

## LIVE WEBSITES **03**
<!-- .slide: class="left-align smalltext" -->

### **DOMAIN NAMES**

a domain name is made up of **your domain** + a **top-level domain** (TLD) like .org, .uk, .com etc. e.g. **myownname.org**

some TLDs like .com and .co.uk are for **companies**, others (.org, .edu .net) for **non-profit**, **information** or **internet-specific** (.net) sites

Domains cost around £5-£20+ per year, **some more expensive** (e.g. .com). Choose a domain name reseller with good management tools and (if you can) an auto-renew option—at some point you will **inevitably forget to renew** in time-expired domains are **grabbed up quickly** by people who **try to re-sell** them to you **at inflated prices**!

There are **newer, less prestigious TLDs** like .tv, .biz (originaly meant for Tuvalu) and even wacky ones like .wtf!!

Here's a [loooong list of TLDs](https://ftp.isc.org/www/survey/reports/current/bynum.txt)

---

## LIVE WEBSITES **04**
<!-- .slide: class="left-align smalltext" -->

### OVERVIEW

- you **purchase a domain name** (make it memorable and snappy)
- **don't expect** to get .com or .org with a **short name**
- you **sign in** to your chosen **web hosting service** and get the **IP address**
- you **'point' your domain name** to the **server** by entering the **IP address** in your domain reseller's **domain admin screens**
- you wait for the **Domain Name Server** (DNS) to update (can take 24 hours)

---

Typical **domain admin screen** (FastHosts)

![](https://raw.githubusercontent.com/front-end-materials/images/master/hosting/domain-admin-01.png "typical domain admin screen")

---

**Domains 'pointing' to servers** (FastHosts)

![](https://raw.githubusercontent.com/front-end-materials/images/master/hosting/domain-admin-02.png "domain names pointing to servers")

---

## LIVE WEBSITES **05**
<!-- .slide: class="left-align smalltext" -->

You can also use **GIT** and **GitHub**

- **[GIT](https://git-scm.com/downloads)** is **verson control software**
- it has a steep but short **learning curve** (e.g. from [another module](https://ctec3905.github.io/presents/?lecture-06#/3/5))
- you create **repositories** ('repos') that **store your files**
- these **track changes** and **save history**
- you can open a **[free student GitHub account](https://help.github.com/en/github/getting-started-with-github/types-of-github-accounts)** without obligation ([guide here](https://www.wikihow.com/Create-an-Account-on-GitHub))
- **[GitHub](https://github.com/)** can **host** your **GIT repositories**
- **[GitHub pages](https://pages.github.com/)** can also host **some kinds of websites**
- You can [point your domain name](https://help.github.com/en/github/working-with-github-pages/managing-a-custom-domain-for-your-github-pages-site) to GitHub pages

GIT and GitHub **require more detail** than we can cover here!

You also can **simply upload your site** to GitHub without GIT

===

# HTML5 MOBILE: **01**
<!-- .slide: class="left-align smalltext" -->

## “WRITE **ONCE** DEPLOY **ANYWHERE**”

Many frameworks *promised* to deliver this idea (e.g. [Meteor](https://www.meteor.com/), [Ionic](http://ionicframework.com), [Appcelerator Titanium](http://www.appcelerator.com/mobile-app-development-products/), [Sencha](https://www.sencha.com/products/extjs/), [React Native](https://facebook.github.io/react-native/) (Adobe [PhoneGap](http://phonegap.com/) is a *distribution* of Apache's [Cordova](https://cordova.apache.org/))

- [Swift](https://developer.apple.com/swift/)/[Java](https://developer.android.com/) **vs** HTML5+native wrapper **vs** PWAs

Increased browser functionality, advances in JavaScript, HTML and CSS drove a *significant shift* towards using **web technologies for mobile development**, so Google introduced a concept…  
**Progressive Web Apps** (PWAs), which took off quickly!

---

# HTML5 MOBILE: **02**
<!-- .slide: class="left-align smalltext" -->

## **native** vs **webapp**

> When dealing with clients… by far the most common thing I’ve noticed is: **they do not care if it’s HTML5 or native**. In fact, despite explanation, they rarely ever understand the difference. **Deliver what they want** and they will be happy no matter what you make it with.

[7 Lessons from 3 Years of HTML5 Mobile App Dev (2017)](https://www.joshmorony.com/7-lessons-from-3-years-of-html5-mobile-application-development/ "this is from a dev who uses a chosen framework")

---

# HTML5 MOBILE: **03**
<!-- .slide: class="left-align smalltext" -->

## ACCESSING DEVICE HARDWARE

HTML5/CSS/JS can access/do many things e.g.  
**location**, **camera**, **push messages**, **file access**…  
see [What Web Can Do Today](https://whatwebcando.today/)

- [“Progressive Web Apps vs. native”… the wrong question…](https://medium.com/dev-channel/why-progressive-web-apps-vs-native-is-the-wrong-question-to-ask-fb8555addcbb)
- [Progressive Web Apps vs Native Apps](https://www.codica.com/blog/progressive-web-apps-vs-native/)
- [Progressive Web Apps: When Short on Resources](https://insanelab.com/blog/web-development/progressive-web-apps-pwa-vs-native/)

===
<!-- PROGRESSIVE WEBAPPS -->

# **PROGRESSIVE** WEBAPPS: **1**
<!-- .slide: class="left-align crammed smalltext" -->

Can give users an **app-like experience** from a **SPA** website

- Save to **home screen** with an icon
- Will now show among **open apps**
- Can increasingly **access device hardware**
- Are based on the **open web**
- **By-pass** the App Store, Google Play
- Are **securely served** ([SSL](https://www.digicert.com/ssl/)—[free SSL with LetsEncrypt](https://letsencrypt.org/))

[**progressive web apps**](https://web.dev/progressive-web-apps/) start **mobile-freindly**, go **much further**

---

# **PROGRESSIVE** WEBAPPS: **2**
<!-- .slide: class="smalltext" -->

![Web App Vs Native App](https://raw.githubusercontent.com/front-end-materials/images/master/pwa/install-a-web-app.gif)

Are **enabled** by—and **compete with**—native Apple and Google apps

---

# **PROGRESSIVE** WEBAPPS: **3**
<!-- .slide: class="smalltext" -->

![Web App Vs Native App](https://raw.githubusercontent.com/front-end-materials/images/master/pwa/webapp-v-app.jpg)

have code telling the device they’re **PROGRESSIVE**, so are “installed” when saved to the home screen. This means they’re **full screen**, and stay in **open apps** separate from the browser.

---

# **PROGRESSIVE** WEBAPPS: **4**
<!-- .slide: class="left-align smalltext" -->

> The fact that web apps are on the **open web** allows developers to **publish anything they want** (and compete with anyone they want) and charge for their own in-app purchases or even “downloads,” **without paying fees** to Apple or Google…
>
> …developers can create an app as a side project **and actually “ship” it**.

[Installable Web Apps May Be the Future of the Open Web](http://brolik.com/blog/installable-web-apps-open-web/)  
—Drew Thomas, 2014.

---

# **PROGRESSIVE** WEBAPPS: **5**
<!-- .slide: class="left-align crammed smalltext" -->

## WHAT YOU **NEED**

- **single-screen** navigation (a SPA or JavaScript navigation)
- fully **responsive design** (see [RWD best practices](https://uxplanet.org/responsive-design-best-practices-c6d3f5fd163b#.o))
- various **icons** and **splash screen** graphics
- wipe **cookies** and **local data** if required
- some understanding of [offline storage](https://medium.com/dev-channel/offline-storage-for-progressive-web-apps-70d52695513c "Addy Osmani")

---

# **PROGRESSIVE** WEBAPPS: **6**
<!-- .slide: class="left-align crammed smalltext" -->

## GOING **FURTHER**

- use **HTTPS** and and **SSL certificate** ([LetsEncrypt](https://letsencrypt.org/) is free)
- a [valid **manifest** file](https://manifest-validator.appspot.com/) (replaces `<meta>` tags) for offline use
- server **config** code for the manifest (e.g. [Apache](https://github.com/h5bp/server-configs-apache/blob/master/src/media_types/media_types.conf))
- [**service workers**](https://developers.google.com/web/fundamentals/getting-started/primers/service-workers): cache assets, **offline data** and **push notifications**
- read up on [IndexedDB](https://developers.google.com/web/fundamentals/instant-and-offline/web-storage/offline-for-pwa) and an [offline data comparison](https://nolanlawson.com/2015/09/29/indexeddb-websql-localstorage-what-blocks-the-dom/)

See [Native Apps are Doomed](https://medium.com/javascript-scene/native-apps-are-doomed-ac397148a2c0)

---

# **PROGRESSIVE** WEBAPPS: **7**
<!-- .slide: class="left-align smalltext" -->

## A **TUTORIAL**

[Your First Progressive Web App](https://codelabs.developers.google.com/codelabs/your-first-pwapp/)

===

## WEB AUDIO **01**
<!-- .slide: class="left-align" -->

Two hand-picked guides/tutorials

- [Getting Started with Web Audio API](https://www.html5rocks.com/en/tutorials/webaudio/intro/)
- [Using the Web Audio API](https://developer.mozilla.org/en-US/docs/Web/API/Web_Audio_API/Using_Web_Audio_API)

===

## INFORMATION ARCHITECTURE
<!-- .slide: class="left-align" -->

A great article and video, so you can **double-check** your site's **Information Architecture** (and look clever by using the information **in your report**!):

[An Excellent Beginner's Guide To Information Architecture](https://careerfoundry.com/en/blog/ux-design/a-beginners-guide-to-information-architecture/)

===

## MOBILE APP ICONS
<!-- .slide: class="left-align" -->

- [50 Beautiful Mobile App Icons for Design Inspiration](https://speckyboy.com/mobile-app-design-inspiration/)

===

# Web 3D
<!-- .slide: class="left-align smalltext" -->

**X3D** is a web standard for **3D in the browser**, with it's **own DOM** (like SVG)

```html
<x3d >
  <scene>
    <shape>
      <appearance>
         <material diffuseColor='0 .4 .8' shininess='0.7' transparency='.1'></material>
      </appearance>
      <box></box>
    </shape>
<!-- etc. … -->?
```

[X3D demo](https://daveeveritt.github.io/x3d-example/) ([code here](https://github.com/DaveEveritt/x3d-example))

===

# STAY SAFE
<!-- .slide: class="left-align" -->

COVID-19 is a **serious threat** to people of **all ages**

Remember to **help and protect your older relatives and friends**, and anyone with a **pre-existing condition**

===

## GOODBYE-**ISH**!
<!-- .slide: class="left-align" -->

If you **attended regularly** you've been **great**!

If not, you're *still great* but we now have  
**less time** to **help you**!

…although we're around for **awhile longer**…