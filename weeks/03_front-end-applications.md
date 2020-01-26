# Week 3: Front-end Applications

## Slides
* ↳ [Link to Week 3 Slides: Front end Applications](#)

## About
This week, we will be learning how to use JavaScript to update the DOM, listen for events, and make API requests to fetch dynamic data. 

Emphasis this week will be on writing clean and organized JavaScript code.

- [Week 3: Front-end Applications](#week-3-front-end-applications)
  - [Slides](#slides)
  - [About](#about)
  - [Outcomes & Goals](#outcomes--goals)
  - [Pacing / Duration](#pacing--duration)
  - [Materials Needed](#materials-needed)
  - [What we are not covering](#what-we-are-not-covering)
  - [Topics](#topics)
    - [JavaScript: Part 2](#javascript-part-2)
    - [DOM Manipulation](#dom-manipulation)
      - [When is a website finished loading?](#when-is-a-website-finished-loading)
      - [Selecting DOM Elements](#selecting-dom-elements)
      - [Creating and Appending DOM Elements](#creating-and-appending-dom-elements)
      - [Removing Elements](#removing-elements)
      - [HTML Element Reference](#html-element-reference)
    - [Event Handlers](#event-handlers)
    - [Using APIs](#using-apis)
      - [What is an API?](#what-is-an-api)
      - [Connecting to RESTful APIs with JavaScript: AJAX and the Fetch API](#connecting-to-restful-apis-with-javascript-ajax-and-the-fetch-api)
      - [Public APIs and Terms](#public-apis-and-terms)
      - [An Example API request from JavaScript](#an-example-api-request-from-javascript)
    - [Reactive UIs](#reactive-uis)

## Outcomes & Goals

You should be able to speak on the following points:

* **DOM Manipulation**
  * What does it mean for a website to be loaded?
  * How do you include JS files in HTML?
  * How do you add new DOM elements?
  * How do you remove DOM elements?
  * How do you change DOM elements?
  * How do you select DOM elements?
* **Event Handling**
  * What is an event handler?
  * What types of events can elements listen for?
  * What the default behavior for certain events on certain elements?
  * How do events propagate to parent elements?
  * How do you create an event listener? How do you remove one?
  * What is the scope within a JS event handler? What is `this`?
* **API Requests**
  * What is an API?
  * How do you find an API?
  * How do you read API documentation?
  * How do you use an API key?
  * How do you make an API request in JS?
  * What is AJAX?
  * What is the fetch API?
  * What is a promise?
* **Reactive UI**
  * What is a UI component?
  * What is functional programming? 
  * What is a template string?
  * How do you separate your data from your "presentation"?
* **Organizing your JavaScript**
  * How do you write clean code?
  * How do you know when you need to refactor?

## Pacing / Duration
TBD

## Materials Needed

* ↳ please see [Developer Setup Guide - Quickstart](../guides/developer-setup-guide.md#quickstart)

## What we are not covering

Topics we are not covering, but are of importance:
* JavaScript Frameworks (React, Vue, Angular, Next)
* Dependency management, transpiling and bundling (Webpack, Parcel, Rollup, Browserify, Babel)

## Topics

### JavaScript: Part 2

> Make your things interactive with JavaScript

* ↳ [JavaScript Frontend Guide](../guides/javascript-frontend-guide.md)
  * Review: JavaScript and the DOM 
  * Asynchronous Javascript: Callbacks, Promises, and Async/Await
  * Networking, AJAX, talking to APIs, and CORs
  * Reactive UIs, Refactoring, and Structuring
  * The Web Platform

### DOM Manipulation

When JavaScript was first created back in the 90's, one of the original uses was to dynamically change a page's HTML after the website had loaded. This is still the most common usage of JS in the browser.

To get started, create a new `index.html`, a new empty JS file `script.js`, and have the HTML link to the script. Then start a simple static server to start building and testing.

**TODO** do I need to include a section about how to include JS files? Or where they are commonly put?

#### When is a website finished loading?
Back in week 1, we talked about all of the steps that happen when you load a website in a browser. Part of that process is when the server sends back an HTML file, and the browser starts rendering the HTML. The browser interprets the HTML and builds the DOM (Document Object Model) of the website. This process isn't instantaneous—it takes some time. If we want to make changes to the DOM, we have to wait until it's finished loading. How do we know (in code) when it's done? The browser fires a `load` event, which we can listen for:
```js
window.onload = function() {
  initialize();
  appendToDOM();
}
```
You'll need to call any code that accesses the DOM, whether you are selecting elements, binding event handlers, or adding or removing elements, after this function had been called. It's common wrap calls to any initialization code in this function.

You can read more here about the details about [Browser Page Lifecycle](/guides/browser-guide.md##the-page-lifecycle)

#### Selecting DOM Elements
See [Selecting DOM Elements](../guides/javascript-frontend-guide.md#selecting-dom-elements) in the JS Front End Guide.


#### Creating and Appending DOM Elements
See [Reference: JavaScript and the DOM](../guides/javascript-frontend-guide.md#references-javascript-and-the-dom) for an in-depth guide. 

*Note*: You cannot create or append DOM elements until the website is loaded. Therefore you'll need to wrap all of the code in this section in a `window.onload` handler.

To create a new element, the code looks like

```js
const newParagraph = document.createElement("p");
newParagraph.textContent = "I'm a new paragraph";
```

If you then reload your webpage, you won't see the new element? Why? Because you didn't saw where you want to put it. You must manually append it to the DOM. You need to include the line
```js
document.body.appendChild(newParagraph);
```

Often, you don't want to append your new element to the end of your DOM, but in a specific location. Rather then specifying an index, it's most common to specify the parent element to add the element to. For example, if your HTML body looked like this
```html
<section id="post">
</section>
<ul id="comments">
</ul>
<footer>
</footer>
```
And you wanted to add a new element to the `#comments` section, you first need to select the element to append to, using `document.getElementById`:
```js
const commentsContainer = document.getElementById("comments");
const newComment = document.createElement("li");
newComment.textContent = "This is an amazing post.";
commentsContainer.appendChild(newComment);
```
Once you selected an element, you can access that elements attributes/properties/methods. This allows you to set, for example, the `textContent` or `innerHTML`, or call methods like `removeChild()`. These depend on the type of HTML element, but you can get the gist from looking at the [HTMLElement](https://developer.mozilla.org/en-US/docs/Web/API/HTMLElement) documentation on MDN (Mozilla Developer Network).

#### Removing Elements

After you've selected an element, you can remove it directly by calling `.remove()`, or remove a child element by calling `.removeChild(childElement)`:
```js
const postElement = document.getElementById("post");
postElement.remove();

const commentContainer = document.getElementById("comments");
commentContainer.removeChild(commentContainer.lastChild);
```

#### HTML Element Reference
The best reference for web development tools is the [Mozilla Developer Network](https://developer.mozilla.org/en-US/docs/Web). It's impossible to memorize all of the different attributes and methods and properties!

Every single HTML element is a subclass of [HTMLElement](https://developer.mozilla.org/en-US/docs/Web/API/HTMLElement). This means that every single element shares some of the same methods and properties, and also have their own (for example, a `<p>` tag can do different stuff from a `<canvas>` element). Also, HTMLElement is a subclass of a few different classes—[Element](https://developer.mozilla.org/en-US/docs/Web/API/Element), [Node](https://developer.mozilla.org/en-US/docs/Web/API/Node), and [EventTarget](https://developer.mozilla.org/en-US/docs/Web/API/EventTarget)—therefore, all elements also include any of the methods/properties from these classes as well.

TODO: include a reference on inheritance and subclasses.

### Event Handlers

Websites and web applications are interactive. When you click on a link, it takes you to a new page, you click a button and it makes a purchase. Every HTML element has **event handlers** so that you can listen for these events, and take actions (i.e. execute code) when these events occur. 

See [Event Handlers and Event Listeners](../guides/javascript-frontend-guide.md#event-handlers-and-event-listeners) for commonly used events.

### Using APIs

#### What is an API?
In ICM, we used p5.js to get data from API's using [loadJSON()](https://p5js.org/reference/#/p5/loadJSON). Our p5.js sketch, the front end JavaScript code, was making an HTTP request, specifically an AJAX request (Asychronous JavaScript Request), and fetching JSON data. This specific type of API is called a REST (Relational State Transfer) API, which specifically defines the interface for computer systems connected to the Internet. I just named a lot of terms, so let's take a step back and talk about all of these different pieces.

What is an API? API stands for "Application Programming Interface," which I don't think does a great job of actually explaining what an API is. The thing is, it's actually a pretty general term—basically, every piece of software has an interface, and therefore an API. You use the API in *code*—for example, you can open the website [Twitter](https://twitter.com) to write a tweet, or you can use the Twitter API to write a tweet from code. Why would you want to do this? For example, you could make a Twitter bot that tweets a programmatically generated [Emoji Aquarium](https://twitter.com/emojiaquarium) every three hours.

What you can do with an API depends on the underlying software. Sometimes an API gives you access to JSON weather data, or sometimes it lets you create a Tweet, or control another application like Ableton Live.

In this class, we will use the term API mostly in the context of RESTful API's and Browser API's. In reality, you're using tons of APIs (VSCode API, Node API, etc.) but we may not talk about them.

* **Reading: ** [Nobody Introduced Me to the API](https://www.robinwieruch.de/what-is-an-api-javascript)

#### Connecting to RESTful APIs with JavaScript: AJAX and the Fetch API
When you load a website or web application, the server is communicating with the browser using HTTP. This is called a **communication protocol**. When you want to load data from an API, you also need to make the request using HTTP. In JavaScript, this is done using AJAX (Asynchronous JavaScript and XML). 

The syntax for making AJAX requests is quite verbose, and while some libraries have been created to make AJAX easier to use (jQuery, Axios), the standard now is to use the Fetch API. To use the Fetch API, you must understand Promises and async/await.

* **Promises and async/await**: [Callbacks, Promises, and async/await](../guides/javascript-frontend-guide.md#callbacks-promises-and-asyncawait)
* **In-depth guide**: [JavaScript Networking, AJAX, talking to APIs, and CORS](../guides/javascript-frontend-guide.md#javascript-networking-ajax-talking-to-apis-and-cors)

#### Public APIs and Terms

Many websites and web applications have created publicly available APIs, to let you access their data or use their services from code. There's tons to choose from!

* **Resource**: [Free, Public APIs](https://github.com/public-apis/public-apis)

If you look through this list, and look through the documentation for each API, you'll notice they look pretty different. Some are minimal, for example, the [Bored API](https://www.boredapi.com/documentation) simply gives you suggestions for activities to do if you are bored. [The New York Times APIs](https://developer.nytimes.com/apis) are much more complicated, and therefore the [documentation](https://developer.nytimes.com/docs/articlesearch-product/1/overview) is more complicated.

There are a few terms to get comfortable with when using APIs:
* **Authentication (or Auth)**: Some APIs require you to authenticate before you can use them. Why? Think of it like logging into a website like Twitter—it gives the API developers and maintainers control over your access to the service, as well as see how you are using it. If they perceive that you are abusing their service, they can turn off your access.
* **AJAX and Fetch**: see [#javascript-networking-ajax-talking-to-apis-and-cors](../guides/javascript-frontend-guide.md)
* **CORS**: Cross-Origin Resource Sharing gives API controls over which websites can access the API. APIs decide which origins can access them, and how. If CORS is enabled, then you should be able to use it. If you are making the requests server-side, this is irrelevant, as CORS is only important for AJAX requests, but that's a topic for next week.
* **origin**: an origin is the protocol (http, https) + hostname (localhost, twitter.com) + port (8000, 80). For example, the full origin running your website locally using the python simple server is `http://localhost:8000`, and the full origin of Wikipedia is https://wikipedia.org:443
* **API Key**: a string of letters/numbers that gives you access to an API, that you can think of like a password.
* **OAuth**: A system for authenticating with an API service in which you can enter a username and password and get back a token. Usually more complicated to use than an API key.
* **Base URL**: Every API has base URL that all of its endpoints are appended to. It usually looks something like `https://www.potterapi.com/v1/`
* **Endpoint**: Also known as a path, an endpoint gives you the slice of data, or service within an API, which is appended to the base url. This also includes the HTTP verb (GET, POST, etc.) ([What is an HTTP verb?](https://developer.mozilla.org/en-US/docs/Web/HTTP/Methods)) This could be something like GET `/characters`, where the full URL would be GET `https://www.potterapi.com/v1/characters`. 
* **URL Query Parameters**: Often endpoints allow you filter and search the data at an endpoint using query string parameters. For example, `https://www.potterapi.com/v1/characters?house=Gryffindor`. `house` is the name of the parameter, and `Gryffindor` is the value. In the documentation, it's usually specified what these parameters can be, just be sure to [URL encode](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/encodeURI) them.
* **Response format**: Usually the response is JSON, very rarely it will not be.


#### An Example API request from JavaScript

Let's practice working with APIs using the [Harry Potter API](https://www.potterapi.com/). To integrate using this API into your application, there's a few steps:

0. Look through the API documentation and figure out if it has the capabilities you are looking for. In this case, I've decided we're using the Harry Potter API so I've done that work for us.
1. Make an account and request an API key. If the API authentication uses API keys, you'll probably have to register with an email/password, and then they will give you an API key.
2. Let's say, for example, we're trying to get all of the characters in Gryffindor house. We need to look at the documentation and construct the full URL:
   1. We need to use the `/characters` endpoint: GET `/characters`
   2. Add a query string parameter, `house=Gryffindor`, bringing the url to GET `/characters?house=Gryffindor`
   3. Add the api key: GET `/characters?house=Gryffindor&key=API_KEY`
   4. Prepend with the base URL: GET `https://www.potterapi.com/v1/characters?house=Gryffindor&key=API_KEY`
3. Test that the URL works. A GET request is the same as entering a URL into your browser window, except that rather than getting a web page back we just get JSON:
  ![Potter API Response JSON](../assets/potter_api_response.png)
  **Note**: I have a Chrome extension that "prettifies" the JSON, for you it may look like a blob of text.
4. Use the Fetch API to make the API request from JS:
  ```js
  const API_KEY = "API_KEY";
  const baseUrl = "https://www.potterapi.com/v1";
  const URL = `${baseUrl}/characters?house=Gryffindor&key=${API_KEY}`;
  fetch(URL).then((response) => {
    return response.json();
  }).then((data) => {
    console.log(data);
  });
  ```
  Notice that this code uses a few newer JavaScript features:
  * [Template Strings](../guides/javascript-frontend-guide.md#template-strings)
  * [Arrow Functions](../guides/javascript-frontend-guide.md#arrow-functions)
  * [Promises](../guides/javascript-frontend-guide.md#callbacks-promises-and-asyncawait)

`data` now holds the JSON from the API we wanted to get. We could do anything we want with it! Create HTML elements, make a data visualization, or even sonify it.

### Reactive UIs

There are many different design patterns to use JSON data to create interfaces. This is the reason for the plethora of front end frameworks—jQuery, Backbone, Angular, React, Vue—they exist to help make this process easier. In this class, we will not be using any front end frameworks, but instead be making our own by using a design pattern called Reactive UI. It's no coincidence that the name is similar to React, and if you can master Reactive UIs, the transition to React will feel right. 



