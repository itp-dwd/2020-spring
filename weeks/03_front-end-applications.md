# WEEK 3: FRONT-END APPLICATIONS

## SLIDES
* ↳ [Link to Week 3 Slides: Front end Applications](https://docs.google.com/presentation/d/100WtCNmj6iJA8loNarUAnuLM5LoS09k2WkWhmRGJU_g/edit?usp=sharing)

## ABOUT
This week, we will be exploring JavaScript as it relates to adding interactivity to our web applications. JavaScript can be and is used to, among many things, update the content of DOM elements, to dynamically apply CSS styles that allow for better user experience and interaction design, and to send and retrieve data from external APIs that can affect what information is shown on the page. 

We will take a project based approach to highlight the major features of modern JavaScript (as of 2020) and how you can use JavaScript to do things like update and manipulate the DOM, listen for events (e.g. did the user click? did the user scroll? is the page loaded?), and make API requests to get and send data from remote servers. 

Emphasis this week will be on writing clean and organized JavaScript code.

This introduction to JavaScript foundations assumes basic working knowledge of JavaScript, i.e.:  

* the existence of control structures: 
  * looping (for loops, while loops)
  * conditional statements (e.g. if, else if, else)
* the existence of data structures:
  * JSON
  * arrays
* basic asynchronous JavaScript:
  * callback functions

- [WEEK 3: FRONT-END APPLICATIONS](#week-3-front-end-applications)
  - [SLIDES](#slides)
  - [ABOUT](#about)
  - [OUTCOMES & GOALS](#outcomes--goals)
  - [PACING / DURATION](#pacing--duration)
  - [MATERIALS NEEDED](#materials-needed)
  - [WHAT WE ARE NOT COVERING](#what-we-are-not-covering)
  - [TOPICS](#topics)
    - [JAVASCRIPT: FOUNDATIONS](#javascript-foundations)
    - [JAVASCRIPT: THE DOM & EVENTS](#javascript-the-dom--events)
    - [JAVASCRIPT: GETTING DATA FROM APIS](#javascript-getting-data-from-apis)
    - [JAVASCRIPT: FORM DATA & SENDING DATA TO APIS](#javascript-form-data--sending-data-to-apis)
    - [JAVASCRIPT: FUNCTIONAL PROGRAMMING, UI COMPONENTS, & REACTIVE USER INTERFACES](#javascript-functional-programming-ui-components--reactive-user-interfaces)
    - [JAVASCRIPT: THE BROWSER PLATFORM](#javascript-the-browser-platform)
  - [STUDIO: FRONT-END APPLICATIONS WORKBOOK](#studio-front-end-applications-workbook)
  - [ASSIGNMENT 3: INTERACTIVE FRONT-END APPLICATION](#assignment-3-interactive-front-end-application)
  - [ADDITIONAL NOTES](#additional-notes)
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
      - [Functional programming: An applied approach](#functional-programming-an-applied-approach)
      - [Unidirectional Data Flow](#unidirectional-data-flow)
    - [Organizing your JavaScript](#organizing-your-javascript)

## OUTCOMES & GOALS

You should be able to speak to the ways that JavaScript related to the following topics: 

* **ES2015 Features**
  * Template strings
  * Array functions
  * Promises, async/await
  * Arrow functions
* **DOM Manipulation**
  * What does it mean for a website to be loaded?
  * How do you include JS files in HTML?
  * How do you **add** new DOM elements?
  * How do you **remove** DOM elements?
  * How do you **change** DOM elements?
  * How do you **select** DOM elements?
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

## PACING / DURATION

* :10 Quick, random selection of Assignment highlights
* :10 Review of last week's material on CSS layouts
* : 

## MATERIALS NEEDED

* ↳ please see [Developer Setup Guide - Quickstart](../guides/developer-setup-guide.md#quickstart)

## WHAT WE ARE NOT COVERING

Topics we are not covering, but are of importance:
* JavaScript Frameworks (React, Vue, Angular, Next)
* Dependency management, transpiling and bundling (Webpack, Parcel, Rollup, Browserify, Babel)

## TOPICS

### JAVASCRIPT: FOUNDATIONS
> Essential JavaScript for all occasions

* ↳ [JavaScript Frontend Guide](../guides/javascript-frontend-guide.md)
  * JavaScript Foundations Review
  * ES6 Syntax, arrow functions, Template Strings
  * Array Functions: e.g. `.forEach()`, `.map()`, `.filter()`, `.findIndex()`
  * Object Functions: e.g. `Object.keys()`, `Object.values()` 


### JAVASCRIPT: THE DOM & EVENTS
> "All we do is talk about manipulating the DOM, but what about checking in and caring for the DOM?" - Kara Gates via Twitter

* ↳ [JavaScript Frontend Guide](../guides/javascript-frontend-guide.md)
  * JavaScript and the DOM
  * JavaScript Events and the DOM 

### JAVASCRIPT: GETTING DATA FROM APIS
> API: "It’s like the connectors on the back of your TV. They let you plug in a device from another manufacturer (DVD player, games console, set-top box) and both the TV and the device know what to do next. The connectors are the interface that lets one machine talk to another." - [Sideways Dictionary](https://sidewaysdictionary.com/#/term/api)

* ↳ [JavaScript Frontend Guide](../guides/javascript-frontend-guide.md)
  * Asynchronous Javascript: Callbacks, Promises, and Async/Await
  * Retrieving data from APIs: Networking, AJAX, and CORs

### JAVASCRIPT: FORM DATA & SENDING DATA TO APIS
> "API: It's like a waiter at a restaurant. The waiter takes a guests' food order, then delivers to the food order to the kitchen staff. The kitchen staff then makes the food, hands the food to the waiter, and then the waiter delivers the correct food order back to the guest." - [Sideways Dictionary](https://sidewaysdictionary.com/#/term/api)

* ↳ [JavaScript Frontend Guide](../guides/javascript-frontend-guide.md)
  * Sending data to APIs: POST, PUT, DELETE

### JAVASCRIPT: FUNCTIONAL PROGRAMMING, UI COMPONENTS, & REACTIVE USER INTERFACES
> "No JavaScript frameworks were created during the writing of this article." - Jose Aguinaga in *[How it feels to learn JavaScript in 2016]((https://hackernoon.com/how-it-feels-to-learn-javascript-in-2016-d3a717dd577f))*

* ↳ [JavaScript Frontend Guide](../guides/javascript-frontend-guide.md)
  * Reactive UIs, Refactoring, and Structuring

### JAVASCRIPT: THE BROWSER PLATFORM
> "The Browser is a treasure trove of goodies."

* ↳ [JavaScript Frontend Guide](../guides/javascript-frontend-guide.md)
  * The Web Platform

***
***
***

## STUDIO: FRONT-END APPLICATIONS WORKBOOK

Learn by doing with the [Front-End Applications Workbook](https://github.com/itp-dwd/front-end-applications-workbook). Here you will encounter a set of guided challenges that will introduce you to a specific process of building an interactive front-end web application that interacts with a 3rd party API to generate a dynamic clientside views.

* ↳ [Link to Front-End Applications Workbook](https://github.com/itp-dwd/front-end-applications-workbook)

***
***
***

## ASSIGNMENT 3: INTERACTIVE FRONT-END APPLICATION

* ↳ [Link to Assignment](../assignments/03_assignment.md)

***
***
***

## ADDITIONAL NOTES

### DOM Manipulation

When JavaScript was first created back in the 90's, one of the original uses was to dynamically change a page's HTML after the website had loaded. This is still the most common usage of JS in the browser.

To get started, create a new `index.html`, a new empty JS file `script.js`, and have the HTML link to the script. Then start a simple static server to start building and testing.



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

If you then reload your webpage, you won't see the new element? Why? Because you didn't say where you want to put it. You must manually append it to the DOM. You need to include the line
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

  We could also using async/await to make the code even shorter:
  ```js
  const API_KEY = "API_KEY";
  const baseUrl = "https://www.potterapi.com/v1";
  const URL = `${baseUrl}/characters?house=Gryffindor&key=${API_KEY}`;
  const response = await fetch(URL);
  const data = response.json();
  ```

`data` now holds the JSON from the API we wanted to get. We could do anything we want with it! Create HTML elements, make a data visualization, or even sonify it.

### Reactive UIs

In ICM, we learned **object-oriented programming**—we encapsulated data and actions (functions) into objects, also known as `class`es. They looked something like this:
```js
// assuming this code uses p5.js
class Bubble {
  constructor() {
    this.x = random(0, width);
    this.y = random(0, height);
    this.size = random(5, 20);
  }

  show() {
    fill(0, 255, 255);
    ellipse(this.x, this.y, this.size);
  }

  update() {
    this.y = this.y + 1;
  }
}

let bubble = new Bubble();
```
This code contains:
1. A **data structure**:
   ```js
   const data = {
     x: Number,
     y: Number,
     size: Number
   };
   ```
2. **functions** that initialize and update the data structure:
   ```js
   constructor() {
     this.x = random(0, width);
     this.y = random(0, height);
     this.size = random(5, 20);
   }

   update() {
     this.y = this.y + 1;
   }    
   ```
3. **functions** that translate the data structure into visual elements:
   ```js
   update() {
     this.y = this.y + 1;
   }
   ```

When creating dynamic websites using HTML, CSS, and JS, we also want to do to the same things! Except we're going to use a different design pattern, called **functional programming**. I'm going to show you how it works, and then talk about why we're switching. 

#### Functional programming: An applied approach

If you search "functional programming" on the Internet, you'll see terms like **pure function** or **immutable data** come up. Don't worry about what these mean yet. Using functional programming to create dynamic web interfaces solves problems that you likely haven't encountered, so I don't want to bore you with these details. Let's just look at how it works.

Let's say we were making a website to explore the characters in Harry Potter. We want to have a radio button selector to select the house, so we could see only the characters in "Gryffindor" or "Slytherin". What are all of the steps in putting this together?
1. Construct URL for Harry Potter API, use house as query string parameter
2. Make API request and load data as JSON
3. Translate JSON to HTML
4. Add event handlers to do steps 1-3 when the user selects a different house

Since we've already done (1) and (2) in the previous API section, let's focus on (3) and (4). We know that the data we're getting back is a list of characters, so we want to put them in some `<ul>`'s and `<li>`'s. We want to use JS to generate HTML that looks like this:
```html
<ul>
  <li>
    <p><span>Name: </span> Katie Bell</p>
    <p><span>Species: </span> Human</p>
  </li>
  <li>
    <p><span>Name: </span> Cuthbert Binns</p>
    <p><span>Species: </span> Ghost</p>
  </li>
  <li>
    <p><span>Name: </span> Sirius Black</p>
    <p><span>Species: </span> Human</p>
  </li>
  <!-- ... and so on -->
</ul>
```

When we're using JS to create HTML, we're not going to manually create all of the DOM elements, though technically this would work:
```js
  // "data" contains the array of characters
  let listContainer = document.createElement("ul");
  document.body.appendChild(listContainer);
  for (let i = 0; i < data.length; i += 1) {
    const listItem = document.createElement("li");
    listItem.textContent = data[i].name;
    listContainer.appendChild(listItem);
  }
```
Creating HTML this way is hard to read, and pretty long. It's also unclear what the HTML structure is. There's a better way! What we can do is create an HTML string, as though we were writing the HTML in a text editor, and then set the `innerHTML` of a DOM element to that string. The browser will then render that HTML string to the DOM.

Let's start with just creating one `<li>` string:
```js
function CharacterItem(character) {
  return `<li>
          <p>${character.name}</p>
         </li>`;
}
```
So now, we've written a function that takes a character (as JSON) as an argument and returns HTML. To create the list, we could do the following:
```js
  function CharacterList(characters) {
    let listItems = '';
    characters.forEach(character => {
      const li = CharacterItem(character);
      listItems += li;
    });
    return `<ul>
              ${listItems}
           </ul>`;
  }
```
`forEach` is a JavaScript array function. It's like a `for` loop but better! Spend some time getting comfortable: [JavaScript array functions](../guides/javascript-frontend-guide.md#javascript-array-methods).

If we want, we can make this code a little shorter using `map`:
```js
  function CharacterList(characters) {
    return `<ul>
              ${characters.map(CharacterItem).join('')}
           </ul>`;
  }
```

Then, when we are ready to actually render the HTML, we can write the following code:
```js
  // assuming there's a <div> with the id "list-container"
  const listContainer = document.getElementById("list-container");
  // data is the response from the Potter API
  const list = CharacterList(data);
  listContainer.innerHTML(list);
```

The functions `CharacterList` and `CharacterItem` can be referred to as **components**, which is a term commonly used in front end web development. 

#### Unidirectional Data Flow

We're going to get a little abstract for a moment. When we use functional programming to create interfaces, we're using a concept called unidirectional data flow. 

![Unidirectional data flow diagram, state -> view -> actions](https://flaviocopes.com/react-unidirectional-data-flow/view-actions-state.png)

There are three components here:
* **state**: This is your data, sometimes called the **store**. In our case, this is simply JS Objects, holding API response data, or interface state, i.e. if a dropdown menu is open
* **view**: This is the HTML created as a function of the state. When the state changes, the view changes.
* **actions**: These are functions, triggered by the view, which make changes to the state.

When you construct your application like this, there is one **source of truth**—the state. When a user interacts with your website, and triggers an event, e.g. they press a button and you want something to change, that event should call a **function** that makes an update to the **state**. Then, the change in state will regenerate the HTML strings. 

### Organizing your JavaScript

When using p5.js, we used a file called `sketch.js` to be our "main" file, the first place we'd look to get an overview of how the code works. From there, you might have some separate files that contained different classes or collections of functions, maybe one called `bubble.js`, `level.js`, and so on. 

When using JS without p5.js, we want to add the same kind of organization. Your folder structure should look something like this:

```
index.html
views/
  about.html
  other-page.html
styles/
  main.css
  about.css
js/
  main.js
  navigation.js
```


***
***
***

