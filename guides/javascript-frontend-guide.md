# Frontend Javascript Guide

## Table of Contents
- [Frontend Javascript Guide](#frontend-javascript-guide)
  - [Table of Contents](#table-of-contents)
  - [About](#about)
- [JavaScript Foundations](#javascript-foundations)
  - [Introduction: The Basics](#introduction-the-basics)
  - [Javascript Array Methods:](#javascript-array-methods)
  - [Javascript Object Methods:](#javascript-object-methods)
  - [Callbacks, Promises and Async/Await](#callbacks-promises-and-asyncawait)
  - [References: JavaScript Foundations](#references-javascript-foundations)
- [JavaScript and the DOM](#javascript-and-the-dom)
  - [References: JavaScript and the DOM](#references-javascript-and-the-dom)
- [JavaScript Networking, AJAX, talking to APIs, and CORs](#javascript-networking-ajax-talking-to-apis-and-cors)
  - [Background: XHR: XMLHttpRequest](#background-xhr-xmlhttprequest)
  - [Fetch API](#fetch-api)
    - [Fetch: default](#fetch-default)
    - [Fetch with options: GET, POST, PUT, DELETE](#fetch-with-options-get-post-put-delete)
  - [A quick note on Axios](#a-quick-note-on-axios)
  - [CORs: Cross origin Resource Sharing](#cors-cross-origin-resource-sharing)
  - [References: JavaScript and APIs](#references-javascript-and-apis)
- [The Web Platform](#the-web-platform)
  - [Browser Platform: `localStorage`](#browser-platform-localstorage)
  - [Browser Platform: Geolocation API](#browser-platform-geolocation-api)
  - [References: The Web Platform](#references-the-web-platform)
- [Conclusion & Recap](#conclusion--recap)
- [Advanced: JavaScript Patterns](#advanced-javascript-patterns)
- [Advanced: JavaScript Frameworks](#advanced-javascript-frameworks)
  - [Essential Questions](#essential-questions)

## About

This frontend JavaScript guide is a roadmap to having a solid JavaScript foundation. Like any language, learning JavaScript for the frontend not only means having a strong grasp of the syntax of JavaScript, but also how it works with and applies to other contexts (e.g. interacting with the DOM, communicating with APIs, etc).

***
***
***

# JavaScript Foundations

In this section we cover foundational JavaScript knowledge. Note that we assume some prior exposure to JavaScript in this section.

## Introduction: The Basics

You can skip this section if the following topics are familiar or you have a grasp of these concepts:
1. ✅ [JavaScript Comments, Variables, Data Types, and Hello, World!](https://www.taniarascia.com/javascript-day-one/)
2. ✅ [Understanding Variables, Scope and Hoisting in JavaScript](https://www.taniarascia.com/understanding-variables-scope-hoisting-in-javascript/)
   - Differentiating between: `var`, `const`, and `let`.
3. ✅ [Doing Math with JavaScript](https://www.digitalocean.com/community/tutorials/how-to-do-math-in-javascript-with-operators)
4. ✅ [For loops and looping in JavaScript](https://www.digitalocean.com/community/tutorials/how-to-construct-for-loops-in-javascript) and [While loops in JavaScript](https://www.digitalocean.com/community/tutorials/using-while-and-do-while-loops-in-javascript)
5. ✅ [Writing Conditionals in JavaScript](https://www.taniarascia.com/how-to-write-conditional-statements-in-javascript/) and the super cool [Switch statement in JavaScript](https://www.digitalocean.com/community/tutorials/how-to-use-the-switch-statement-in-javascript)
6. ✅ [JavaScript Objects](https://www.digitalocean.com/community/tutorials/understanding-objects-in-javascript) and [Working with JSON objects in JavaScript](https://www.digitalocean.com/community/tutorials/how-to-work-with-json-in-javascript) and [Using JavaScript Object Methods](https://www.digitalocean.com/community/tutorials/how-to-use-object-methods-in-javascript)
7. ✅ [JavaScript Arrays](https://www.digitalocean.com/community/tutorials/understanding-arrays-in-javascript) and [Accessing data from JavaScript Arrays](https://www.digitalocean.com/community/tutorials/how-to-use-array-methods-in-javascript-accessor-methods) and [Mutating JavaScript Arrays](https://www.digitalocean.com/community/tutorials/how-to-use-array-methods-in-javascript-mutator-methods)
8. ✅ [Defining Functions in JavaScript](https://www.digitalocean.com/community/tutorials/how-to-define-functions-in-javascript)
9. ✅ [JavaScript Classes](https://www.digitalocean.com/community/tutorials/understanding-classes-in-javascript) and encapsulating functionality and data.

And a nice-to-know: [Date and Time in JavaScript](https://www.taniarascia.com/understanding-date-and-time-in-javascript/)

## Javascript Array Methods:

TBD

* [JavaScript Iteration Methods](https://www.digitalocean.com/community/tutorials/how-to-use-array-methods-in-javascript-iteration-methods)

## Javascript Object Methods:

TBD

* [Using JavaScript Object Methods](https://www.digitalocean.com/community/tutorials/how-to-use-object-methods-in-javascript)
* [This, bind, call, and apply in JS](https://www.digitalocean.com/community/conceptual_articles/understanding-this-bind-call-and-apply-in-javascript)

## Callbacks, Promises and Async/Await

TBD

* [Coding Train: Async/Await -- Part 1](https://www.youtube.com/watch?v=XO77Fib9tSI)
* [Coding Train: Async/Await -- Part 2](https://www.youtube.com/watch?v=chavThlNz3s)
* [Coding Train: Async/Await -- Part 3](https://www.youtube.com/watch?v=01RTj1MWec0)
* [Async/Await](https://javascript.info/async-await)
* [Modern Async JS](https://flaviocopes.com/javascript-async-await/)
* [Promise.all and handling multiple async functions](https://www.taniarascia.com/promise-all-with-async-await/)


## References: JavaScript Foundations
* [How to Code in JavaScript](https://www.digitalocean.com/community/tutorial_series/how-to-code-in-javascript)
* [JavaScript Comments, Variables, Data Types, and Hello, World!](https://www.taniarascia.com/javascript-day-one/)
* [How To Write Conditional Statements in JavaScript](https://www.taniarascia.com/how-to-write-conditional-statements-in-javascript/)
* [Understanding Date and Time in JavaScript](https://www.taniarascia.com/understanding-date-and-time-in-javascript/)
* [How To Use the Switch Statement in JavaScript](https://www.taniarascia.com/how-to-use-the-switch-statement-in-javascript/)
* [https://www.taniarascia.com/understanding-classes-in-javascript/](https://www.taniarascia.com/understanding-classes-in-javascript/)
* [Understanding Variables, Scope and Hoisting in JavaScript](https://www.taniarascia.com/understanding-variables-scope-hoisting-in-javascript/)
* [Real World Examples of Map, Filter and Reduce in JavaScript](https://www.taniarascia.com/real-world-examples-of-map-filter-and-reduce-in-javascript/)


***
***
***

# JavaScript and the DOM

In this section we discuss the wonderful role of JavaScript and its ability to interact with the DOM. This is where we really dive into what it means for JavaScript to not only create the ability for pages to be *interactive*, but also *reactive*. So far, we've been talking mostly about JavaScript as a language, but now it is time to explore the ways in which JavaScript completes the HTML5 trifecta of HTML/CSS/JavaScript.

By mastering JavaScript as a language, understanding how to work with JavaScript in relation to CSS and HTML, and building up your sensibilities for software architectures and JavaScript patterns, you'll be well equipped to approach the development client side applications with confidence and across many contexts.

Let's begin applying our JavaScript knowledge in relation to interacting to DOM.


TBD

## References: JavaScript and the DOM 
* understanding events: https://www.digitalocean.com/community/tutorials/understanding-events-in-javascript
* https://www.taniarascia.com/how-to-access-elements-in-the-dom/
* https://www.taniarascia.com/how-to-traverse-the-dom/
* https://www.taniarascia.com/how-to-make-changes-to-the-dom/

***
***
***

# JavaScript Networking, AJAX, talking to APIs, and CORs

This section is about using client side JavaScript to communicate (aka network) with the outside world. There are a number of ways we can make network connections to servers from our web browser -- e.g. web sockets, webRTC, and HTTP -- but we will focus our attention specifically on communicating over HTTP using **XHR** and its more friendlier API, the **Fetch API**.

In this section you will learn about how you can use JavaScript to communicate with outside servers and APIs from the browser.

## Background: XHR: XMLHttpRequest

> "XMLHttpRequest (XHR) is an API in the form of an object whose methods transfer data between a web browser and a web server." -- [From Wikipedia, the free encyclopedia](https://en.wikipedia.org/wiki/XMLHttpRequest)

While most of the time you will not be using the raw XHR or XMLHttpRequest request object and its functions to make network requests, it is important to know that the integration of this feature into web browsers back in the 2000s was a major innovation and game changer for our web experiences using browsers and the ability to network with the outside world.

It is also important to know that the syntax for using the raw XHR request in JavaScript is not as friendly as using the **fetch API** or better yet, the [Axios](https://github.com/axios/axios) library for making HTTP requests.


```js
// Create a new XHR request object
const xhr = new XMLHttpRequest();
// Set the options of the request including the METHOD, URL, and if the operation should be Asynchronous or not.
xhr.open("GET", "https://api.chucknorris.io/jokes/random", true);
// Here we handle the results of the request.
// Each XHR request goes through 4 stages,
// Stage 4 of the .readyState is DONE
xhr.onload = function (e) {
  if (xhr.readyState === 4) {
    // if our request status is 200 - it is a great success!
    if (xhr.status === 200) {
      console.log(xhr.responseText);
    } else {
      console.error(xhr.statusText);
    }
  }
};
// Here we do our error handling
xhr.onerror = function (e) {
  console.error(xhr.statusText);
};
// and FINAlly can SEND the request
xhr.send(null); 
```
* you can see that the `xhr.readyState` has a few specific numbers, lets take a look at what they mean here in the reference on [MDN's guide to the XMLHttpRequest.readyState](https://developer.mozilla.org/en-US/docs/Web/API/XMLHttpRequest/readyState). As written in the post the `.readyState` value of `4` means that the operation is complete! 

If you copy and paste the above code to your javascript console, you should see:

```json
{"categories":[],"created_at":"2020-01-05 13:42:22.701402","icon_url":"https://assets.chucknorris.host/img/avatar/chuck-norris.png","id":"InbZFgfnQJa_vXsmIS6CeQ","updated_at":"2020-01-05 13:42:22.701402","url":"https://api.chucknorris.io/jokes/InbZFgfnQJa_vXsmIS6CeQ","value":"Particle physicists have finally developed a new atom smasher. It is called Chuck Norris's fist."}
```

![](../assets/js__xhr-01.png)

Notice, it took us several dozens of lines of code to make a simple GET request. Lucky for us the **fetch API** provides and easier way to network with the outside world.

For more information, see [Flavio Copes's post on XHR](https://flaviocopes.com/xhr/)

## Fetch API

### Fetch: default

TBD

### Fetch with options: GET, POST, PUT, DELETE

TBD

## A quick note on Axios

TBD

## CORs: Cross origin Resource Sharing

TBD

## References: JavaScript and APIs 
* https://www.taniarascia.com/how-to-use-the-javascript-fetch-api-to-get-json-data/

***
***
***
# The Web Platform

The Browser is a treasure trove of goodies. It is comprised of many exciting APIs that can be accessed through JavaScript. This section is about the **web platform** that will enable and enhance your users' frontend experiences. 

Below is a (non-exhaustive) list, that you can explore deeper on your frontend development journey:

* [The DOM](https://developer.mozilla.org/en-US/docs/Web/API/Document_Object_Model)
* [DevTools](https://flaviocopes.com/browser-dev-tools/)
* [Web API](https://developer.mozilla.org/en-US/docs/Web/API)
  * Events:
    * [Scroll events](https://developer.mozilla.org/en-US/docs/Web/API/Document/scroll_event)
    * [Drag and Drop](https://developer.mozilla.org/en-US/docs/Web/API/HTML_Drag_and_Drop_API)
    * [Mouse Events](https://developer.mozilla.org/en-US/docs/Web/API/MouseEvent)
    * [Touch Events](https://developer.mozilla.org/en-US/docs/Web/API/Touch_events)
    * [Keyboard Events](https://developer.mozilla.org/en-US/docs/Web/API/KeyboardEvent)
  * [History API](https://developer.mozilla.org/en-US/docs/Web/API/History_API)
  * [Web Speech Synthesis API](https://developer.mozilla.org/en-US/docs/Web/API/Web_Speech_API)
  * [Geolocation API](https://developer.mozilla.org/en-US/docs/Web/API/Geolocation_API)
  * [Canvas API](https://developer.mozilla.org/en-US/docs/Web/API/Canvas_API)
  * [Web workers](https://developer.mozilla.org/en-US/docs/Web/API/Web_Workers_API/Using_web_workers)
* [Web storage API](https://developer.mozilla.org/en-US/docs/Web/API/Web_Storage_API)
  * [cookies](https://developer.mozilla.org/en-US/docs/Web/HTTP/Cookies)
  * [indexedDB](https://developer.mozilla.org/en-US/docs/Web/API/IndexedDB_API)
  * [localStorage](https://developer.mozilla.org/en-US/docs/Web/API/Window/localStorage)
* Networking:
  * [XHR](https://developer.mozilla.org/en-US/docs/Web/API/XMLHttpRequest)
  * [Fetch API](https://developer.mozilla.org/en-US/docs/Web/API/Fetch_API)
  * [CORS](https://developer.mozilla.org/en-US/docs/Web/HTTP/CORS)
  * [web sockets](https://developer.mozilla.org/en-US/docs/Web/API/WebSockets_API)
  * [Stream API](https://developer.mozilla.org/en-US/docs/Web/API/Streams_API)
  * [webRTC](https://developer.mozilla.org/en-US/docs/Web/API/WebRTC_API)

  
In addition adding plugins for the browser in the form of  Bookmarklets and Browser Extensions (commonly referred to as Chrome Extensions) is a very exciting aspect of web development.

From the exciting list of features above, this section will highlight just a few features. The idea is that you should work through these functionalities as they become relevant for your projects. 

## Browser Platform: `localStorage`

TBD

## Browser Platform: Geolocation API

TBD

## References: The Web Platform

* https://www.taniarascia.com/how-to-use-local-storage-with-javascript/


***
***
***

# Conclusion & Recap


***
***
***

# Advanced: JavaScript Patterns

For continued learning, you will start to get into a place where you'll want to develop and eye for and an ability to implement different JavaScript patterns. These software development patterns allow you to handle increasing complexity in your applications such as handling state, managing data, variable and function scoping, and general modularity, scalability, and maintenance of frontend applications. 

There are many JavaScript Patterns that exist and many which are reliant on a firm grasp of [JavaScript Classes]. I can recommend the following references for beginning to understand how JavaScript Patterns can be used in practice to build increasingly complex software:

* [MVC Pattern: Model-view-controller](https://www.taniarascia.com/javascript-mvc-todo-app/)
* [PubSub Pattern: The Publish-Subscribe Pattern]()
  * Examples of the PubSub pattern
    * [a-simple-pubsub-module-in-javascript](https://bdadam.com/blog/a-simple-pubsub-module-in-javascript.html)
    * [pub-sub boilerplate](https://github.com/joeyklee/pubsub-boilerplate)
* [Observer Pattern](https://pawelgrzybek.com/the-observer-pattern-in-javascript-explained/)
* Writing on JS Patterns:
  * Additional patterns are discussed here in [Josh Bedo's JS Design Pattern's Blogpost](https://joshbedo.github.io/JS-Design-Patterns/) 
  * [Observer vs PubSub Pattern](https://hackernoon.com/observer-vs-pub-sub-pattern-50d3b27f838c)

# Advanced: JavaScript Frameworks

At the heart and soul of many JavaScript frameworks is the implementation and application of JavaScript Patterns into a system that allows software to be maintainable and scalable. Many frontend frameworks these days implement some kind of JavaScript pattern like a [MVVM or Model-View-ViewModel](https://en.wikipedia.org/wiki/Model%E2%80%93view%E2%80%93viewmodel) and [Flux pattern](https://facebook.github.io/flux/).

These days, there are A LOT of front end frameworks out there. 

Below are the cool kids in town these days:

* (My personal recommendation) [Vue.js](https://vuejs.org/) with [Vuex](https://vuex.vuejs.org/) ==> [Nuxt.js](https://nuxtjs.org/) which is a framework built in Vue.js
* [React.js](https://reactjs.org/) with React Hooks or [Redux](https://redux.js.org/) & [Next.js](https://nextjs.org/) which is a framework built on React.js

Still relevant and widely used:
 
 * [Backbone.js](https://backbonejs.org/)
 * [Angular.js](https://angularjs.org/)

And recent and somehow seems too good to be true:

* [Svelte](https://svelte.dev/)







<!-- 

Structure

* JS foundations
* JS Array Methods
* JS and the DOM
* Async Foundations
* The Browser API


 -->

<!-- 
## Essential Questions

- How does the web browser work?
- What is the DOM? 
  - Why is it important to use semantically relevant tags instead of just "divs"?
- What are events? What are event listeners?
- How do we handle user inputs using HTML Forms? 
- What are the unique roles of HTML, CSS, and JavaScript?
- What does it mean to be "asynchronous" in development? How and why is this relevant for web development?
- What are JavaScript Array functions and how can they be used to achieve different tasks?

- "Vanilla JavaScript"
- Selecting DOM Elements by DOM type or CSS class or ID
  - Accessing Elements in the DOM: https://www.taniarascia.com/how-to-access-elements-in-the-dom/
  - Traversing the DOM: https://www.taniarascia.com/how-to-traverse-the-dom/
  - Making Changes to the DOM: https://www.taniarascia.com/how-to-make-changes-to-the-dom/
- Event binding / Event firing / listening
- Handling forms (only in the browser)
- `fetch`, AJAX requests


 -->

