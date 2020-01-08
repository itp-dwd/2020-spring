# Week 03: Back-end Foundations

## Essential Questions

- What is the "back-end" / server-side programming?
- What is a server side programming language? How does it differ from client-side programming in the browser?
- What is Node.js? How does it relate to Express.js?
- What is an API? 
- What is REST?
- What is CRUD?
- How do we persist data? Can we persist data on a server without a database?
- What is the difference between server-side code and the server machine? How is this related to a platform-as-a-service (PaaS)?

## Introduction
This week we will be focusing our attention on server-side programming, otherwise known as the "back-end" of web applications.

### Outcomes & Goals

In this class we will be:
* Learning to program a server with Node.js
* Writing server-side JavaScript to create our own REST APIs that allow us to communicate between our client and server to perform CRUD operations.

Students will walk away with a deeper understanding of:
* The terminal / command-line
* NPM, Node.js and Express.js
* REST API structure
  

## Topics

### JavaScript in the Browser vs Node
- Node
  - In a nutshell:
    - same language, different capabilities 
    - you *could* use any language (Python, Ruby, C++) on your computer, but it's nice using the same language for a whole project
  - No:
    - `window`, no `document`, no `DOM`, no `canvas` (therefore no p5.js!)
  - Benefits:
    - Access to the file system
    - (potentially) faster computation
  - You should know:
    - Node can be used for lots of things not just as a server. You can use it to crunch data, 
- Browser
  - In a nutshell:
    - Only JavaScript runs in a browser, so you don't have other options
  - No:
    -  file system (your computer's files) access
    -  

### Diving in to Node.js 
- `require()` vs. `import` 
  - there are 2 ways to import packages but depends on the version of Node.js you're using. For usage of `import` please use Node.js version >=12. 
- `fs`
- `path`
- `http`
- Code runs from top to bottom.
- how to debug? ==> lots of console.log() :) 

### Node with Express
- Why use express on top of Node? To create a web server
  - you can technically create one using just the `http` module, but it's a lot of code.
    - TODO: example code
  - Here's some examples of other web server code:
    - Ruby: https://blog.appsignal.com/2016/11/23/ruby-magic-building-a-30-line-http-server-in-ruby.html
- Serving different HTML files based on a route
  - getting the correct path w/ `path.resolve(__dirname, 'views') + 'about.html'` 
  - convention: `views` directory

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
- render to front end using template strings

### What we are not covering

NOTE: ...

Topics we are not covering, but are of importance:
* ...
* ...
* ...


## Pacing / Duration
<!-- Number of total hours the class session will take. Please try to take into account transition time between instruction and hands on exercises if any prep is necessary. -->

- Break down of the class schedule example: 
  - :15 Overview, context, examples and vocabulary 
  - :20 Instruction & hands on exercise 
  - :15 Wrap-up discussion & sharing, reflection or journal and next steps

## Materials Needed
<!-- What hardware, software, or other materials will students or teachers need for lessons. -->

* Laptop & Power charger
* Text Editor (VS Code)
* Web browser (chrome or firefox preferred, but safari is ok)
* Node.js installed (with NVM?)
* Terminal/command-line

### Exercises To Do Before Class
What materials (readings, tasks, exercises) should students complete before class to be prepared for the lesson.

TBD

### Vocabulary (example)
* term:
  * route:
    * ...
  * 

## Studio Exercise Descriptions
Descriptions of each exercise or phase of class. Similar to pacing but with more description of steps.

## References
Include any sources cited, but not directly linked in the unit.