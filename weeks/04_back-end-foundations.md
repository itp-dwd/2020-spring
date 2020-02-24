# WEEK 03: BACK-END FOUNDATIONS

* 🌟 Guest Speaker, [Yuraima Estevez](https://www.yuraima.com/)

## SLIDES
* ↳ [Link to Week 4 Slides: Back end Foundations](#)

## ABOUT

This week we will be focusing our attention on server-side programming, otherwise known as the "back-end" of web applications.

We will be learning about server-side programming using JavaScript running in Node.js. We we learn how to run Node scripts and make our own API.

Emphasis this week will be on understanding when it is necessary to use server-side programming, and differentiating between server-side and client-side code.


### OUTCOMES & GOALS

In this class we will be:
* Learning to program a server with Node.js
* Writing server-side JavaScript to create our own REST APIs that allow us to communicate between our client and server to perform CRUD operations.

Students will walk away with a deeper understanding of:
* The terminal / command-line
* NPM, Node.js and Express.js
* REST API structure


* **Node.js**
  * What is back end/server side programming?
  * What is Node.js? What's the motivation behind its creation?
  * How do you install Node.js?
  * What are the Node.js core libraries? How do you use them?
  * What capabilities does Node have that browser JS does not? What about vice versa?
  * What is Node.js? How does it relate to Express.js?
* **npm**
  * What is `npm`? What is the difference between `npm`, the command line tool, and "npmjs.com"?
  * How do you create an npm project? How do you install and keep track of dependencies?
  * How do you use "npmjs.org"?
  * How do you use `npm` with `git`?
  * What is **npm**, what is a `package.json`, how they are related, and why they are important?
  * How to install node.js dependencies using npm.
* **APIs**
  * What is an API?
  * What is REST?
  * What is CORS?
* **Express**
  * What is a static web server? How do you create one with Express?
  * How do you Express to return JSON?
  * Why would you use Express to make API requests, rather than making the requests client-side?
* **Data Persistence**
  * What are ways that you can persist data?
  * Can you persist data without a database? When do you need to use a database?
* **Platform as a service**:
  * What is the difference between server-side code and the server machine? How is this related to a platform-as-a-service (PaaS)?
  * Can you explain the difference between a server (code), server (machine), and server (the service)? 
* **Client vs Server**:
  * Can you clearly delineate between your server-side code and your client-side code? Explain how they are different.
  * What is the "back-end" / server-side programming?
  * What is a server side programming language? How does it differ from client-side programming in the browser?
  * What does it mean to serve *static* files using a web server? 
  * How do you use dynamic data in your website?


## WHAT WE ARE NOT COVERING

Topics we are not covering, but are of importance:
* TypeScript
* Dependency management, transpiling and bundling (Webpack, Parcel, Rollup, Browserify, Babel)

## PACING / DURATION

* :30 - Guest Speaker, [Yuraima Estevez](https://www.yuraima.com/)
* :30 - Overview of Backend Foundations with Node.js and Express.js
* :60 - Studio / Live coding express API.

## MATERIALS NEEDED

* ↳ please see [Developer Setup Guide - Quickstart](../guides/developer-setup-guide.md#quickstart)
### Outcomes & Goals

  
## TOPICS

### The client vs. the Server

* [Backend Foundations Guide - Client vs Server](../guides/backend-foundations-guide.md#client-side-javascript-vs-server-side-javascript)

### Server-side JavaScript with Node.js

* [Backend Foundations Guide - Server-side JavaScript with Node.js - The Basics](../guides/backend-foundations-guide.md#server-side-javascript-with-nodejs-the-basics)

### NPM, the Node Package Manager
* [Backend Foundations Guide - NPM](../guides/backend-foundations-guide.md#nodejs--the-node-package-manager-npm)

### Friendly web servers with Express.js

* [Backend Foundations Guide - Node with Express](../guides/backend-foundations-guide.md#simple-expressjs-web-server)

### Building APIs with Express.js & the basics of CRUD

* [Backend Foundations Guide - Basics of CRUD in RESTful APIs](../guides/backend-foundations-guide.md#introduction-to-crud-with-persistence-pizza-topping-api)

### Tools for Interfacing with APIs

* [Backend Foundations Guide - cURL](../guides/backend-foundations-guide.md#curl)
* [Backend Foundations Guide - Postman](../guides/backend-foundations-guide.md#postman)

### Interfacing with APIs from the client

* [Backend Foundations Guide](../guides/backend-foundations-guide.md#client-side-interfacing)

<!-- ### JavaScript in the Browser vs Node
- Node
  - **In a nutshell**:
    - same language, different capabilities 
    - you *could* use any language (Python, Ruby, C++) on your computer, but it's nice using the same language for a whole project
  - **Doesn't have**:
    - `window`, no `document`, no `DOM`, no `canvas` (therefore no p5.js!)
  - **Does have**:
    - Access to the computer's file system
    - (Potentially) faster computation
    - Can be used in non-web contexts, for example, to crunch data
- Browser
  - **In a nutshell**:
    - Only JavaScript runs in a browser, so you don't have other options
    - Always used in conjunction with an HTML document
  - **Doesn't have**:
    -  file system (your computer's files) access
    -  `import` or `require`
 -  **Does have**
    -  access to `window`, `document`
    -  access to browser API's, like Web Audio and Canvas

### Diving in to Node.js
- Starting the Node REPL (Read-eval-print loop). This is the same as opening the Developer Console in a browser.
  - ```sh
    $ node 
    ```
- Running a script - code runs from top to bottom.
  - ```sh
    $ node script.js
    ```
- how to debug? ==> lots of console.log() :) 
- `require()` vs. `import` 
  - there are 2 ways to import packages but depends on the version of Node.js you're using. For usage of `import` please use Node.js version >=12. 
- Core Node libraries
  - `fs`
  - `path`
  - `http`

### Node with Express
- Initializing a Node project - using `npm init`
- Installing dependencies and saving them to your `package.json`
- Why use express on top of Node? To create a web server
  - you can technically create one using just the `http` module, but it's a lot of code.
    - TODO: example code
  - Here's some examples of other web server code:
    - Ruby: https://blog.appsignal.com/2016/11/23/ruby-magic-building-a-30-line-http-server-in-ruby.html
- Serving different HTML files based on a route
  - getting the correct path w/ `path.resolve(__dirname, 'views') + 'about.html'` 
  - convention: `views` directory
- Middleware

### Building APIs with Express & the basics of CRUD
- API that we are building towards: Todo App? Tarot or Astrology related?
- How to build APIs with express:
  - `app.get`
  - `app.post`
  - `app.put`
  - `app.delete`
- `requests` and `response` ==> (res, req)
- Dynamic routes
  - url params
  - query params
- Storing/updating json object on the server
- Writing files to the server
- maybe for later: node-fetch/isomorphic fetch or external API requests from the server

### Interfacing with your API

- Quick intro to cURL
- Introduction to Postman
- using `fetch` to grab data
- render to front end using template strings -->


***
***
***

## STUDIO: BACKEND FOUNDATIONS WORKBOOK

Learn by doing with the [Back-End Foundations Workbook](../guides/backend-foundations-guide.md). Here you will encounter a set of guided challenges that will introduce you to the basic building blocks necessary to build a basic web server and API. 

* ↳ [Back-End Foundations Workbook](../guides/backend-foundations-guide.md)

***
***
***

## ASSIGNMENT 3: API Love You - Oh CRUD

* ↳ [Link to Assignment](../assignments/04_assignment.md)

***
***
***