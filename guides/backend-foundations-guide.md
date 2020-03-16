# BACKEND FOUNDATIONS GUIDE

## ABOUT

This backend foundations guide is a roadmap to a beginning your knowledge and practice of server-side programming with Node.js. 

In this guide we focus on the foundational knowledge of server-side JavaScript with Node.js. 

## PRE-REQUISITES

Before continuing, you should make sure to have explored the following guides and resources:

* [front-end javascript guide](javascript-frontend-guide.md)
* [Dev Tools Guide](dev-tools.md)
* [Node Debugger Guide](node-debugger.md)


- [BACKEND FOUNDATIONS GUIDE](#backend-foundations-guide)
  - [ABOUT](#about)
  - [PRE-REQUISITES](#pre-requisites)
- [CLIENT-SIDE JAVASCRIPT VS. SERVER-SIDE JAVASCRIPT](#client-side-javascript-vs-server-side-javascript)
- [SERVER-SIDE JAVASCRIPT WITH NODE.JS: THE BASICS](#server-side-javascript-with-nodejs-the-basics)
  - [WHAT IS NODE.JS](#what-is-nodejs)
  - [INSTALLING NODE.JS](#installing-nodejs)
  - [BASICS OF RUNNING SERVER-SIDE SCRIPTS](#basics-of-running-server-side-scripts)
    - [RUNNING JAVASCRIPT IN NODE.JS'S REPL ENVIRONMENT](#running-javascript-in-nodejss-repl-environment)
    - [RUNNING JAVASCRIPT AS A SCRIPT](#running-javascript-as-a-script)
  - [BASICS OF ACCESSING NODE.JS LIBRARIES](#basics-of-accessing-nodejs-libraries)
  - [A SIMPLE NODE.JS SCRIPT](#a-simple-nodejs-script)
  - [RECAP](#recap)
  - [REFERENCES](#references)
- [NODE.JS & THE NODE PACKAGE MANAGER (NPM)](#nodejs--the-node-package-manager-npm)
  - [What is NPM and what are Node Modules](#what-is-npm-and-what-are-node-modules)
  - [Project management with package.json](#project-management-with-packagejson)
  - [Installing Node Modules, dependency management, and the `node_modules` directory](#installing-node-modules-dependency-management-and-the-nodemodules-directory)
    - [Installing packages](#installing-packages)
    - [Excluding `node_modules` from git tracking](#excluding-nodemodules-from-git-tracking)
  - [Recap](#recap-1)
- [NODE.JS WITH EXPRESS.js](#nodejs-with-expressjs)
  - [What is Express.js?](#what-is-expressjs)
  - [Express.js Core Concepts](#expressjs-core-concepts)
  - [SIMPLE EXPRESS.JS WEB SERVER](#simple-expressjs-web-server)
    - [SETUP](#setup)
    - [DEPENDENCIES](#dependencies)
    - [YOUR WEBSERVER: `INDEX.JS`](#your-webserver-indexjs)
    - [YOUR SERVED STATIC HTML: `PUBLIC/INDEX.HTML`](#your-served-static-html-publicindexhtml)
    - [RUN THE WEB SERVER](#run-the-web-server)
    - [Tidying Up](#tidying-up)
  - [EXPRESS CONVENTIONS](#express-conventions)
    - [Serving your HTML views in the `views` directory](#serving-your-html-views-in-the-views-directory)
    - [ADDITIONAL NOTES](#additional-notes)
- [EXPRESS.JS APIS](#expressjs-apis)
  - [WHAT'S AN API?](#whats-an-api)
  - [EXPRESS API STRUCTURE](#express-api-structure)
  - [API ROUTES: PART 1 - HTTP VERBS](#api-routes-part-1---http-verbs)
    - [HTTP Verbs:](#http-verbs)
  - [CRUD Conventions](#crud-conventions)
  - [Introduction to CRUD with persistence: Pizza Topping API](#introduction-to-crud-with-persistence-pizza-topping-api)
    - [SETUP](#setup-1)
    - [The "Model": Reading and Writing from a JSON file](#the-%22model%22-reading-and-writing-from-a-json-file)
    - [The "Controller": Connecting endpoints to the Model](#the-%22controller%22-connecting-endpoints-to-the-model)
  - [CRUD with Express.js: Dream Collector](#crud-with-expressjs-dream-collector)
    - [SETUP](#setup-2)
    - [GET](#get)
    - [POST](#post)
    - [PUT](#put)
    - [DELETE](#delete)
  - [Example: API example and A Simple File-based data store](#example-api-example-and-a-simple-file-based-data-store)
- [Interfacing with your API](#interfacing-with-your-api)
  - [cURL](#curl)
  - [Postman](#postman)
  - [Client-side interfacing](#client-side-interfacing)
    - [Local development](#local-development)
    - [Changing your request URL for deployment](#changing-your-request-url-for-deployment)

***
***
***

# CLIENT-SIDE JAVASCRIPT VS. SERVER-SIDE JAVASCRIPT

In this guide we are talking about server-side JavaScript. This means that we are moving away from the client-side where we use JavaScript to add interactivity to our websites. 

With server-side JavaScript, what we're talking about is writing JavaScript for a server environment. This means that our server-side JavaScript does not have access to a browser context; no p5.js, no canvas, no web audio, no DOM manipulation, nada. 

So what then is server-side JavaScript for? Instead of writing JavaScript to interact with the DOM, now we're turning our attention to ways we can write JavaScript to interact with our computer's file system, including data that we want to process and store, databases that live on our computer, and other processes that do not live in the browser. You can think of server-side JavaScript as a way to write code that allows us to bridge together 2 environments that otherwise live separately: the browser and the server. We will see in subsequent sections how we can create APIs to open up connections between these two environments. 

Here we outline some of the major differences, uses, advantages, and disadvantages of client-side vs. server-side code:

| Features | **client-side** JavaScript | **server-side** JavaScript |
| :--- | --- | --- | 
| **Where it runs** | In a browser environment | On a server or your machine | 
| **Advantages** | 1. Has access to the browser and the web platform (e.g. canvas, web audio, DOM), 2. Feedback is potentially more visual (e.g. you can see how your JS affects the DOM) | 1. Has access to the file system of the machine, 2. potentially faster computation, 3. Potentially more storage and memory access | 
| **Disadvantages** | 1. Does not have access to your local file system | 1. Has no "window" or DOM or access to the browser environment, 2. Can be more abstract since feedback is only through the terminal | 
| **Purpose** | 1. For adding interactivity and functionality to websites and client facing applications and 2. To communicate with servers via APIs to get data and bring them to the client. | 1. For handling data, serving up websites, for interfacing with a database, for automating processes and 2. To create API endpoints for client-side applications to send and retrieve data.  | 

If you ever wondered why we need to run a **local web server** when we work on client-side projects to access images and external files like `.json` data or `.js` files, it's because we need a *server* to *serve up* those external files living outside of the HTML context. (Is this of those, "OMG I get it now" moments?). Remember, your client-side JavaScript can only access what is going on in the browser, so in order to access those other files, you need server-side code to make those files living in your file system accessible to your browser. 

This guide will show you how you can program your own web servers and build your own APIs to make files and data accessible from a local file system to your browser context. 

<!-- - Server-side JavaScript with **Node.js**
  - **In a nutshell**:
    - same language, different capabilities 
    - you *could* use any language (Python, Ruby, C++) on your computer, but it's nice using the same language for a whole project
  - **Doesn't have**:
    - `window`, no `document`, no `DOM`, no `canvas` (therefore no p5.js!)
  - **Does have**:
    - Access to the computer's file system
    - (Potentially) faster computation
    - Can be used in non-web contexts, for example, to crunch data
- Client-side Javascript in the **Browser**
  - **In a nutshell**:
    - Only JavaScript runs in a browser, so you don't have other options
    - Always used in conjunction with an HTML document
  - **Doesn't have**:
    -  file system (your computer's files) access
    -  `import` or `require`
 -  **Does have**
    -  access to `window`, `document`
    -  access to browser API's, like Web Audio and Canvas -->

***
***
***

# SERVER-SIDE JAVASCRIPT WITH NODE.JS: THE BASICS

## WHAT IS NODE.JS
Before we can get into programming our own web servers, we will take a second to explore the basics of server-side JavaScript with Node.js. 

Let's start with answering the question: What is Node.js? Node.js is a JavaScript that runs on the server rather than in the browser. 

In the past, we might write server-side code in Python, PHP, Java, C/C++, or Ruby. Whether it is Python or Ruby or Node.js, they all more or less do the same thing -- they allow you to write code that accesses/manipulates/runs computation on the files and data on your local file system. 

Aside: In my own experiences doing research and data analysis, I was writing code in Python and R to take big data files, run scripts that would do data cleaning and processing, calculate statistics, and generate figures and graphs of the data we'd collected from our weather and pollution sensors. During this time, I never interfaced with the web browser. We would just write code that ran on our machines that would output files into a folder so we could analyze our results and write about it later. Never in this process did I have to interface with a browser or even the internet for that matter. We just wrote code that was meant to live (and die) on our machines (or to be shared with other scientists and researchers). Another way to think about this is like writing the code for software that just lives on your computer like the Arduino IDE or Microsoft Word and Excel -- those programs can interface with files and directories on your machine, but otherwise those software just live on your computer.  

The neat thing about these server-side programming languages is that they allow you to write code so that can take files living on your local file system and *serve* up files and data to the internet so that other people can access: 

* the HTML for a website you built, 
* a data file you want to share (e.g. images or music or JSON or CSV data)
* ... and more?

## INSTALLING NODE.JS

Like any software, you need to install Node.js onto your machine so that you can use it. Other server-side programming languages like Python and Ruby should by default be already installed on your machines (if you're running MacOS) -- this is because different software on your computers were likely programmed by developers at Apple using Python or Ruby and therefore needed to be installed as necessary software to allow your computer to run those software.

Node.js is not by default installed on your machines and therefore you will need to install the Node.js runtime environment in order for your computer to be able to understand how to "run" Node.js code. 

* See [node.js installation guide](installing-nodejs.md)

## BASICS OF RUNNING SERVER-SIDE SCRIPTS

There are a number of ways to write server-side code. You can write server-side code in an: 

* **A.** Node.js REPL (read-evaluate-print-loop) environment: 
  * meaning you interactively write code directly in the terminal in a Node.js runtime environment (e.g. like you would in the browser's developer console) OR more commonly in 
* **B**. A Node.js "script": 
  * meaning a file that contains all of the code that you want to be run from top to bottom.

### RUNNING JAVASCRIPT IN NODE.JS'S REPL ENVIRONMENT

Open your terminal and type:
```sh
$ node
```

Your terminal will then look like:
```sh
> 
```

You can then start writing JavaScript:
```sh
> const a = 1
undefined
```

You can see how you can define variables and do addition as you would in normal JavaScript:
```sh
> const b = 2
undefined
> a + b
3
>
```

You can even define functions:
```sh
> function hello( name ){ console.log(`hello ${name}` )}
undefined
> hello('joey')
hello joey
undefined
>
```

You might be wondering: "Why does `undefined` keep coming up?" - others have wondered the same thing and you can read more about it here [node.js displays “undefined” on the console](https://stackoverflow.com/questions/8457389/node-js-displays-undefined-on-the-console)

### RUNNING JAVASCRIPT AS A SCRIPT

Running a script - code runs from top to bottom. Assuming you have a file called: `script.js`:

In `~/Desktop/script.js`

```js
const a = 1;
const b = 2;
console.log(`${a} + ${b} = ${a + b}`);
```

In your terminal
```sh
$ cd ~/Desktop/script.js
$ node script.js
```

You should see in your terminal:

```sh
1 + 2 = 3
```

## BASICS OF ACCESSING NODE.JS LIBRARIES 

Node.js has grown in large part because of a thriving open source community that have made **node modules** that make it easier to do certain programming tasks. These **node modules**, also called node **libraries**, are code packages that make it easier to do things like make web servers, communicate with database servers, read, parse, and write files, and even do complex computational tasks like geospatial analyses, scientific computing, and more.  

If you've programmed with p5.js, you know that in order to use p5.js you need to reference the p5.js library in your `index.html` as a `<script>`. In order for us to use libraries in Node.js you'll need to *import* or *require* them into your projects. 

| node.js version | library import syntax | example |
| :---            | ----                  | --- |
| `< 12`  | `require('package name')`| `const fs = require('fs')` |
| `>= 12`  | `import 'package name'`| `import * as fs from 'fs'` |

How do you tell which node version you're using? If I type in my terminal, the following, mine says v10.15.0, yours might say something different:
```sh
$ node -v
v10.15.0
```

There are some libraries that are part of the **core node libraries** which means we don't need to download anything using `npm` in order to use them. Instead, we can just import them directly into our projects and start using them. Some of the core node libraries include:

| library name | description |
| :---        | ---         |
| `'fs'`      | File System - a helper library for accessing files in your local file system |
| `'path'`    | Path - a helper library for helping to resolve file paths to files on your local file system | 
| `'http'`    | HTTP - a helper library for creating an HTTP server |

<!-- - `require()` vs. `import` 
  - there are 2 ways to import packages but depends on the version of Node.js you're using. For usage of `import` please use Node.js version >=12.  -->
  
<!-- - Core Node libraries
  - `fs`
  - `path`
  - `http` -->

Let's take a look at making our very first node.js script with some of the core libraries we mentioned above.

## A SIMPLE NODE.JS SCRIPT

In this short excursion, we will make a node.js script that:

1. reads and writes data to a file called "myData.json"
2. the contents of "myData.json" will be an array that stores a timestamp and the size of "myData.json" every time the script is run.

* **Step 0**: Create a folder called `data-logger`:
   ```sh
   $ mkdir ~/Desktop/data-logger
   ```

* **Step 0.5**: cd into that `data-logger` folder:
  ```sh
  $ cd ~/Desktop/data-logger
  ```

* **Step 1**: Create a file called: `index.js`
   ```sh
   $ touch index.js
   ```

* **Step 2**: Add your libraries to the top of the script
In `index.js`
   ```js
   // Step 2: Add your libraries to the top of the script
   const fs = require('fs');
   const path = require('path');
   ```

* **Step 3**: Set a placeholder for our data
  ```js
  // Step 3: Set a placeholder for our data;
  let data = [];
  ```

* **Step 4**: Get the path to our data
  ```js
  // Step 4: Get the path to our data
  const dataPath = path.resolve(__dirname + '/myData.json');
  ```

* **Step 5**: Load in existing data or create an empty data file
   ```js
   // Step 5: Load in existing data or create an empty data file
   if(fs.existsSync(dataPath)){
     // If a data file exists, then load it using fs.readFileSync()
     data = fs.readFileSync(dataPath);
     data = JSON.parse(data);
   } else {
     // otherwise create an empty json file in the directory we will write to later.
     fs.writeFileSync(dataPath, JSON.stringify(data));
   }
   ```

* **Step 6**:  get the file size of the file and the timestamp
   ```js
   // Step 6: get the file size of the file and the timestamp
   const fileSize = fs.statSync(dataPath).size / 1000000.0; // to get the size in mb
   const currentTime = new Date();

   ```

* **Step 7**: create a JSON object entry for the size of the myData.json and timestamp
   ```js
   // Step 7: create a JSON object entry for the size of the myData.json and timestamp
   const metadata = {
     size: fileSize,
     timestamp: currentTime
   }
   ```

* **Step 8**: push your metadata object to the "data" array
  ```js
  // Step 8: push your metadata object to the "data" array
  data.push(metadata);
  ```

* **Step 9**: write to your file
  ```js
  // Step 9: write to your file
  fs.writeFileSync(dataPath, JSON.stringify(data));
  ```

Run the script by doing:

```sh
$ node index.js
```

Now open your `myData.json` and see what you find!

```json
[{"size":0.000002,"timestamp":"2020-02-16T16:32:44.460Z"}]
```

If you run this script over and over again, you'll see the new entries appended to that array. Can you imagine how you might be able to remix this script in a way that allows you to continually store data about something interesting? Maybe you can store data collected from your own little weather station or something else? 

A note on `.readFileSync()` and `.writeFileSync()`: These are synchronous functions. The preferred alternative is to always use asynchronous functions -- `.readFile()` and `.writeFile()` -- and handle file writing with callback functions or promises and async/await. If you use 
 
## RECAP

So we've looked at using node.js libraries that are baked in to Node.js already. In the next section we are going to learn more about the NPM - node package manager - and the Node.js ecosystem and how to bring in 3rd-party libraries that make it easier to make more complex applications. 

## REFERENCES
* https://flaviocopes.com/how-to-check-if-file-exists-node/

***
***
***
# NODE.JS & THE NODE PACKAGE MANAGER (NPM)

Node.js thrives on an active community of people making open source software for the node.js ecosystem. These node.js libraries are centralized on NPM - the node package manager - a platform that allows node.js users to download and access the software built and contributed by other node.js users. These packages range the gamut from node packages that are a couple lines long with limited features to massive software projects that are hundreds and thousands of lines long with extensive features. It's always a good idea to check NPM for keywords of interest before starting a software project with Node.js - you might just find exactly what you need!

In this section we cover:
* the importance of the NPM community and open source software in the node.js ecosystem
* the structure of and convention of structuring node modules
* how the NPM universe allows you to document and organize your dependencies

## What is NPM and what are Node Modules

As mentioned above, NPM stands for Node Package Manager and is the server that serves up thousands of open source node modules for people to use in their node.js projects. You might be wondering, "how is it that *all* of these node modules just work?" If so, here's why. 

Node.js modules are a standard way of structuring node.js code so that they can be *required* or *imported* into a node.js project. 

* This is the `module.exports` syntax in Node.js `version < 12`:
  ```js
  function myCustomAdditionFunction(a, b){
    return a + b;
  }

  module.exports = myCustomAdditionFunction;
  ```

* or `export default` syntax in Node.js `version >= 12` :
  ```js
  function myCustomAdditionFunction(a, b){
    return a + b;
  }

  export default myCustomAdditionFunction;
  ```

Node.js code that uses `module.exports` or `export default` can then be used as a dependency in another script using the `require()` or `import` statements:

For example, if we have a folder structure like this:

```txt
/myProject
  index.js
  myCustomAdditionFunction.js
```

Then in `index.js` we could do:
```js
// import * as myAddFunction from './myCustomAdditionFunction.js';
const myAddFunction = require('./myCustomAdditionFunction.js');

console.log(myAddFunction(1, 2)) // 3;
```

You will not only use see this structure in node.js code all the time, but you will also write code structured this way. This will allow you to *modularize* your code, keep your code tidy, and help you to maintain the best Node.js coding best practices. 


## Project management with package.json 

Step 1 of Node.js coding best practices is to make sure you include all the metadata for your node.js project in a file called `package.json` in the root directory of your project. You can create this manually, but the most common method is to use the `npm init` command in your project directory:

```sh
$ cd myProject
$ npm init
```

You will then answer all of the questions prompted to you:

```sh
$ cd myProject
$ npm init
This utility will walk you through creating a package.json file.
It only covers the most common items, and tries to guess sensible defaults.

See `npm help json` for definitive documentation on these fields
and exactly what they do.

Use `npm install <pkg>` afterwards to install a package and
save it as a dependency in the package.json file.

Press ^C at any time to quit.
package name: (myProject)
version: (1.0.0) 0.0.1
description: a simple demo project
entry point: (index.js)
test command:
git repository:
keywords:
author: joeyklee
license: (ISC) MIT
About to write to /Users/username/myProject/package.json:

{
  "name": "myProject",
  "version": "0.0.1",
  "description": " a simple demo project",
  "main": "index.js",
  "scripts": {
    "test": "echo \"Error: no test specified\" && exit 1"
  },
  "author": "joeyklee",
  "license": "MIT"
}


Is this OK? (yes) yes
```
NOTE: You should use your Github username and select an appropriate license. 

As you can see, the `package.json` includes important info about your project. 

Your `package.json` will become your best friend. The `package.json` file will include all that you and others will need to know in order to get your project running, whether that is a list of dependencies to install or how to run your program. 

The `package.json` file is also of supreme importance for how servers and other platforms know which dependencies to install and how to run your code. 


## Installing Node Modules, dependency management, and the `node_modules` directory

### Installing packages
Ah! The moment we've been waiting for: downloading node modules from NPM. Its simple actually. 

Make sure you're in your project directory and in your terminal:

```sh
$ cd myProject
$ npm install <package name>
```

Let's take the example of installing `cat-me` - a node package for making super cool ascii art cats in node.js:

```sh
$ npm install cat-me
```

Now you can do:
in `~/myProject/index.js`
```js
const catMe = require('cat-me');

console.log(catMe());
console.log(catMe('nyan'));
```

See what happens!

Note also that in your `package.json` (assuming you did the `npm init` step) is that `cat-me` will be added as part of the `dependencies` property of your `package.json` file.

### Excluding `node_modules` from git tracking

Make sure to always add `node_modules` to your `.gitignore` file while using node. NEVER check all your node_modules into git tracking.

In your project root directory, in a file called `.gitignore`:
```txt
node_modules
```

## Recap

Now that you've seen how to install packages, import them into your projects, and take care of your project's dependencies, it is time to look into a specific Node package called *Express.js*. Express.js is designed specifically to help make it easier to make web servers and server-side APIs for the node.js environment. 

***
***
***

# NODE.JS WITH EXPRESS.js

## What is Express.js?

Express.js is a Node.js library built on top of Node's HTTP server module that serves as a lovely abstraction layer to make building web servers in Node.js easier.  In theory, you could never ever touch Express.js and code everything in vanilla Node.js code, however Express.js makes building web servers much much more simple.  

## Express.js Core Concepts 

The core concepts of Express can be categorized conceptually with these terms: **Middleware**, **Routing**, **Request and Response handling**, and **Views**.

Let's explain each of those terms with the metaphor of New York City's Subway lines:

* **Middleware**:
  * If an express.js application is the entire collection of all the subway lines, you can think if express middleware as the subway stops. Middleware are functions that are strung together in your Express.js application through which each subway train flows.  Your subway trains in this case are your data. 
  * On a technical level, middleware, also known as "middleware functions" are indeed functions. These middleware functions take 3 parameters: `(request, response, next)`, where `next` is a function that says, "Everything in this function that I wanted to accomplish is done, now proceed to the next middleware please."
  ```js
  app.get('/hello', handleHello1, handleHello2)

  function handleHello1( (req, res, next) => {
    console.log('hello');
    next();
  })
  function handleHello2( (req, res, next) => {
    console.log('Lovely person');
    res.end();
  })
  ```

* **Routing**:
  * If middleware are the stops that your data (the subway trains) are meant to flow through your program, Express.js routes dictate which middleware your data (the trains) are meant to flow. Some data (trains) will flow through same middleware (stops) and others will not. 
  * Routes are the endpoints of your Express API that allow people to access or submit data from your server. 
  * In the below code, we have the API endpoints specifying how you and your users can access certain data by those routes on your server. So for example I could make a GET request to: "https://myapp.com/hello", or "https://myapp.com/hello/1x2aa4facvsa" or make a POST request to "https://myapp.com/hello" and something would happen.
  ```js
  app.get('/hello', handleHello1, handleHello2);
  app.get('/hello/:id', getSpecificHello);
  app.post('/hello', addHelloToDatabase);
  ```
* **Handling Requests and Response**:
  * If routes are like specific subway lines and the middleware are like the specific stops your subway train takes, requests are like the people getting on the train at each station and the response are the people getting off of the train. Some train stations have elevators and escalators, others only have stairs. Some train stations are connected to malls and parks, others just put you on the street. You can think of handling requests as different data (people or trains) that come into your express application and responses as different ways those data get used (people get off the train, the train is re-routed or is delayed, etc).
  * Handling requests means that a client is trying to communicate with your server and sends some kind of information. So if someone made a request to "https://myapp.com/hello/1x2aa4facvsa", what you would get logged in your console would be "1x2aa4facvsa" the id string that was passed into the URL *parameters* aka `param` property of the request object.
  ```js
  app.get('/hello/:id', getSpecificHello);

  function getSpecificHello(req, res, next){
    console.log(req.params.id)
    // usually this would mean you'd search a database and retrieve the database entry for that specific id
  }
  ```
* **Views** (we are not really going to talk about rendering views on the server in this class!): 
  * Express.js allows you to render HTML on the server dynamically to send to a client's web browser. There are advantages and disadvantages to server-side rendering, but all you need to know for now is that it is possible. In this class, we don't discuss server-side rendering in favor of separating out client-side and server-side applications that communicate using AJAX requests through HTTP/HTTPS.
  * In our subway metaphor, views would be the outside world where our subway lines deliver us to. They are the endpoints to why we take the wonderful subway train to get from A to B.
  * In the case of what we will do in this class, we will serve our views from a static web server. 

## SIMPLE EXPRESS.JS WEB SERVER

Remember how when you've coded client-side projects in the past, you always had to run a local web server (probably using `python -m SimpleHTTPServer`)? Well, now we're going to look at how to write the code to make **your very own web server**. 

### SETUP 

```sh
# 1. create a project directory
~ $ mkdir ~/Desktop/my-first-webserver
# 2. change directories
(my-first-webserver) $ cd ~/Desktop/my-first-webserver
# 3. use npm init to create a package.json
(my-first-webserver) $ npm init
# 4. create an index.js file in the root directory
(my-first-webserver) $ touch index.js
# 5. create a folder called public
(my-first-webserver) $ mkdir public
# 6. create an index.html file in /public
(my-first-webserver) $ touch public/index.html
```
**Setup**: 

1. create a project directory called `my-first-webserver`
2. change directories
3. use `npm init` to create a package.json
4. create an index.js file in the root directory using `touch`
5. create a folder called `public`


### DEPENDENCIES

```sh
# 1. install the express.js dependency 
(my-first-webserver) $ npm install express
```

**Dependencies**:

1. install the express.js dependency using `npm install`


### YOUR WEBSERVER: `INDEX.JS`

```js
// 1. Load your dependencies
const path = require('path');
const express = require('express');
// 2. Instantiate an express instance
const app = express();
// 3. Define a port number to run your server on
const PORT = 3000;

// 4. Get the path to your public directory
const publicURL = path.resolve(`${__dirname}/public`);
// 5. Define the folder which will host your static files 
app.use(express.static(publicURL))

// 6. Define the route where your static HTML fill be found
app.get("/", (req, res, next) => {
  res.sendFile("index.html");
});

// 7. Start your webserver by listening to the port you defined
app.listen(PORT, () => {
  console.log(`see the magic at: http://localhost:${PORT}`)
});
```
**Express web server**: in your file `my-first-webserver/index.js`

1. Load your dependencies
2. Instantiate an express instance
3. Define a port number to run your server on
4. Get the path to your public directory
5. Define the folder which will host your static files 
6. Define the route where your static HTML fill be found
7. Start your webserver by listening to the port you defined

### YOUR SERVED STATIC HTML: `PUBLIC/INDEX.HTML`

In the `public/index.html`
```html
<!DOCTYPE html>
  <head>
    <meta charset="utf-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <title></title>
    <meta name="description" content="">
    <meta name="viewport" content="width=device-width, initial-scale=1">
    <link rel="stylesheet" href="">
  </head>
  <body>
    hello there lovely person
  </body>
</html>
```

### RUN THE WEB SERVER

```sh
(my-first-webserver) $ node index.js
see the magic at: http://localhost:3000
```

Go to http://localhost:3000 and see the website running.

### Tidying Up

* Create a file called `.gitignore` and add the following to make sure that you DO NOT TRACK YOUR NODE_MODULES in git tracking:
  ```txt
  node_modules
  .DS_Store
  ```

## EXPRESS CONVENTIONS

### Serving your HTML views in the `views` directory
In the above example of the express web server, we serve everything that lives in the "public" directory. A typical convention when you're building web applications is to put all of your HTML into a directory called `views`. This makes it easier for people coming to your full stack web application to find your HTML files that render into your front-end application code. 

This is the scaffold for what your basic node application might look like:
```txt
/myProject
  package.json
  .gitignore
  index.js
  /public
    /assets
      MrBubz.jpg
    /js
      main.js
    /css
      main.css
  /views
    index.html
    /about
      index.html
    /contact
      contact.html
  /node_modules
```

To serve your `views` directory as a static HTML endpoint, you can do:

```js
const viewsURL = path.resolve(`${__dirname}/views`);
app.use(express.static(viewsURL))
```

### ADDITIONAL NOTES

- Why use express on top of Node? To create a web server you can technically create one using just the `http` module, but it's a lot of code.
- You can create web servers in lots of other languages and essentially they follow the same approach
    - Ruby: https://blog.appsignal.com/2016/11/23/ruby-magic-building-a-30-line-http-server-in-ruby.html
    - Python web server: https://ruslanspivak.com/lsbaws-part1/



***
***
***

# EXPRESS.JS APIS

Express.js helps us make web servers. Part of what it means to "make a web server" is creating ways for our web servers to communicate with external client applications. In this section we will cover how building APIs in Express allow us to create server-side functionality that can pass data back and forth between a client, the server, other servers and eventually databases. 

## WHAT'S AN API? 

API stands for Application Programming Interface. 

## EXPRESS API STRUCTURE

In general you can think of creating Express APIs as defining "routes" where client applications can make requests to interface with your server. 

Using the **API endpoints** -- the routes -- that you define on your server, people will be able to send data and retrieve data to/from your server, access HTML views, and more. 

An overview of an express application looks something like this:

```js
// 1. Setup and load your libraries 

// 2. Connect to a database

// 3. Initialize express 

// 4. Define your API endpoints

// 5. Start listening
```

There are basically 5 steps and each of these steps will contain code that speaks very generally to how an Express app is structured. Most of the work in building a "back end" to an application is how you define the logic in step 4 where you are defining your API endpoints. 

In the following section we are going to cover how to build an API with Express that allows you to do CRUD -- create, read, update, and delete -- which is what lies at the core of any web application. 


## API ROUTES: PART 1 - HTTP VERBS

In this section we are going to focus on step 4 where we define our API endpoints. 

### HTTP Verbs:

HTTP/HTTPS is one of the main protocols that allow us to communicate across the web. In order to pass messages from clients to servers and vice versa in a clear way, part of the HTTP protocol includes what we might call HTTP verbs or HTTP request types. The HTTP Request types define what kind of client-server interaction we should expect. 

| **verb** | **description** | **translation** | **CRUD** |
| :--- | ---         | ---         | --- |
| POST | A client wants to create data on a server by sending it some data in a request         | "Hey! I have some data, can I leave it with you?" | `CREATE` |
| GET | A client requests data from a server  | "Hey! Can I GET some data?" | `READ` |
| PUT | A client is requesting to update data that already exists on a server | "Hey! Remember that data I gave you last week, can you update it with this new stuff?"         | `UPDATE` |
| DELETE | A client is requesting to delete data that exists on the server | "Hey! Remember that data I gave you, can you uh remove that, thank you bye!" | `DELETE` |

In Express.js we define in our code *how we expect* people to communicate with the server. As the designer and developer of your server's API, you will be creating the routes where you want people to interface with your server (and your data).

Hopefully, this makes sense conceptually. Let's now walk through how this translates into code using an example

## CRUD Conventions
Adapted from [Rails Routing from the Outside In](https://guides.rubyonrails.org/routing.html#crud-verbs-and-actions).

When creating an API, by convention, certain endpoints match with certain CRUD resource actions. Here's a helpful table:

| HTTP Verb	| Path | Controller Function | Used for     |
| --------- | ---- | ------------------- | ------------ |
| `GET` | `/toppings`	| `toppings#getToppings` | get a list of all toppings |
| `GET` | `/toppings?q=<query>`	| `toppings#getToppings` | get a filtered list of all toppings |
| `POST`| `/toppings`	| `toppings#createTopping`	| create a new topping |
| `GET` | `/toppings/:id`	| `toppings#getTopping`	| get a single topping |
| `PATCH/PUT` | `/toppings/:id` | `toppings#updateTopping` | update a specific topping |
| `DELETE` | `/toppings/:id`| `toppings#destroyTopping` | delete a specific topping |

Often, you will find that the actions your API needs to do fall outside of the CRUD actions. That's okay! CRUD is simply an organizational starting point, but does not need to be the *only* type of endpoints.

## Introduction to CRUD with persistence: Pizza Topping API

We are now going to build a pizza topping API. This is also covered as part of the [back end foundations workbook](https://github.com/itp-dwd/back-end-foundations-workbook).

### SETUP
```sh
# 1. Create a new project folder
~ $ mkdir ~/Desktop/pizza-topping-api
# 2. change directories
(pizza-topping-api) $ cd ~/Desktop/pizza-topping-api
# 3. create your server file
(pizza-topping-api) $ touch server.js
# 4. run npm init
(pizza-topping-api) $ npm init
# 5. install your dependencies: express - for creating your express app
(pizza-topping-api) $ npm install express
# 7. Create a folder called "db"
(pizza-topping-api) $ mkdir db
# 8. Create a file called "toppings.json"
(pizza-topping-api) $ touch db/db.json
# 9. Copy the contents of https://raw.githubusercontent.com/dariusk/corpora/master/data/foods/pizzaToppings.json to this file
(pizza-topping-api) $ curl https://raw.githubusercontent.com/dariusk/corpora/master/data/foods/pizzaToppings.json >> db/db.json
```

Your project scaffold will look like this now:

```txt
/pizza-topping-api
  index.js
  /db
    toppings.json
  /node_modules
```

In your `server.js` file now add the following code. The following subsections will explain each section

```js
// 1. Add your dependencies
const express = require("express");
const path = require("path");
const fs = require("fs");

// 2. Instantiate your Express application
const app = express();

// 3. Add your express middleware
// 3. Middleware: serve public as a static folder
app.use(express.static("public"));
// 3. Middleware: parse http request body as json
app.use(express.json());

// This is not necessary for the API, but let's keep it in, why not
app.get("/", (req, res) => {
  res.sendFile(path.join(__dirname, "views/index.html"));
});

// 4. Add functions to read/write to toppings.json when API requests are made
// 4.1 Returns the contents as JSON of toppings.json
function getToppings() {
  const contents = fs.readFileSync(path.join(__dirname, "./data/toppings.json"));
  const obj = JSON.parse(contents);
  return obj;
}

// 4.2 Adds a new topping to the pizzaToppings array,
// then saves the object to disk
function addTopping(topping) {
  const toppings = getToppings();
  // Push updates the original array
  toppings.pizzaToppings.push(topping);
  fs.writeFileSync(path.join(__dirname, "./data/toppings.json"), JSON.stringify(toppings));
  return toppings;
}

// 4.2 Deletes a topping from the pizzaToppings array,
// then saves the object to disk
function deleteTopping(toppingToDelete) {
  const toppings = getToppings();
  // filter does NOT change the original array
  toppings.pizzaToppings = toppings.pizzaToppings.filter(topping => topping !== toppingToDelete);
  fs.writeFileSync(path.join(__dirname, "./data/toppings.json"), JSON.stringify(toppings));
  return toppings;
}

// 5 Create API endpoints
// 5.1 GET /toppings - returns the list of all toppings
app.get("/toppings", (req, res) => {
  const toppings = getToppings();
  res.json(toppings);
});

// 5.2 POST /toppings - adds the topping in req.body.topping to the topping array
app.post("/toppings", (req, res) => {
  const topping = req.body.topping;
  const toppings = addTopping(topping);
  // often, updated list will be returned by API
  res.json(toppings);
});

// 5.2 DELETE /toppings/:name - removes the topping in :name from the topping array
app.delete("/toppings/:name", (req, res) => {
  const toppingToDelete = req.params.name;
  const toppings = deleteTopping(toppingToDelete);
  res.json(toppings);
});

// 6 Start the server
app.listen(3000, () => {
  console.log("Server is listening on port 3000!");
});

```

### The "Model": Reading and Writing from a JSON file
We are using a JSON file called `toppings.json` as our data store. We want our data to persist—this means that when we shut down and restart our server, the data will still be there. The JSON file is our **source of truth**. Therefore, every time we need to update the list of toppings, we need to read from the JSON file, update the JS object, and then write the object back to JSON. The functions that update data persistence are called the Model.

```js
function getToppings() {
  const contents = fs.readFileSync(path.join(__dirname, "./data/toppings.json"));
  const obj = JSON.parse(contents);
  return obj;
}

// Adds a new topping to the pizzaToppings array,
// then saves the object to disk
function addTopping(topping) {
  const toppings = getToppings();
  // Push updates the original array
  toppings.pizzaToppings.push(topping);

  //After updating the object, write back to disk
  fs.writeFileSync(path.join(__dirname, "./data/toppings.json"), JSON.stringify(toppings));
  return toppings;
}

// Deletes a topping from the pizzaToppings array,
// then saves the object to disk
function deleteTopping(toppingToDelete) {
  const toppings = getToppings();
  // filter does NOT change the original array
  toppings.pizzaToppings = toppings.pizzaToppings.filter(topping => topping !== toppingToDelete);

  //After updating the object, write back to disk
  fs.writeFileSync(path.join(__dirname, "./data/toppings.json"), JSON.stringify(toppings));
  return toppings;
}
```

### The "Controller": Connecting endpoints to the Model
The functions that handle API requests and route them to the right Model functions are called the Controller. They parse the data from the request and form the response.

```js
// 5 Create API endpoints
// GET /toppings - returns the list of all toppings
app.get("/toppings", (req, res) => {
  const toppings = getToppings();
  res.json(toppings);
});

// POST /toppings - adds the topping in req.body.topping to the topping array
app.post("/toppings", (req, res) => {
  const topping = req.body.topping;
  const toppings = addTopping(topping);
  // often, updated list will be returned by API
  res.json(toppings);
});

// DELETE /toppings/:name - removes the topping in :name from the topping array
app.delete("/toppings/:name", (req, res) => {
  const toppingToDelete = req.params.name;
  const toppings = deleteTopping(toppingToDelete);
  res.json(toppings);
});
```

## CRUD with Express.js: Dream Collector

We are going to build a dream collector. The dream collector store data in a static JSON file on your server, so there will be no database server, but rather a flat file to read and write from. 

### SETUP

```sh
# 1. Create a new project folder
~ $ mkdir ~/Desktop/dream-collector
# 2. change directories
(dream-collector) $ cd ~/Desktop/dream-collector
# 3. create your server file
(dream-collector) $ touch index.js
# 4. run npm init
(dream-collector) $ npm init
# 5. install your dependencies: express - for creating your express app
(dream-collector) $ npm install express
# 5. install your dependencies: morgan - for debugging and enhanced logging functionality
(dream-collector) $ npm install morgan
# 6. install a development dependency: 
(dream-collector) $ npm install nodemon -D
# 7. Create a folder called "db"
(dream-collector) $ mkdir db
# 8. Create a file called "db.json" in /db and add an empty array into the JSON file using echo
(dream-collector) $ echo [] >> db/db.json
```

Your project scaffold will look like this now:

```txt
/dream-collector
  index.js
  /db
    db.json
  /node_modules
```

In your `index.js` file now add the following code. The following subsections will explain each section

```js
// 1. add your dependencies
const fs = require('fs');
const path = require('path');
const express = require('express');
const logger = require('morgan');
const bodyParser = require('body-parser');
const PORT = 3000;

// 2. Read your data in ensuring that there is an empty array or valid data
const dataPath = path.resolve(`${__dirname}/db/db.json`);
let data = JSON.parse(fs.readFileSync(dataPath));

// 3. instantiate your express app
const app = express();

// 4. define your middleware: logging
app.use(logger('dev'));
// 4. define your middleware: request handling
app.use(bodyParser.urlencoded({
  extended: true
}));
// 4. define your middleware: result handling
app.use(bodyParser.json());

// 5. GET: get all dreams
app.get("/api/v1/dreams", (req, res, next) => {
  res.json(data);
});

// 6. GET: get only a specific dream
app.get("/api/v1/dreams/:id", (req, res, next) => {
  const selected = data.find( item => item.id === Number(req.params.id) );
  res.json(selected);
});

// 7. POST: create data
app.post("/api/v1/dreams", async (req, res, next) => {
  const newData = {
    dream: req.body.dream,
    id: data.length + 1,
  }
  // push the data to the data array
  data.push(newData);
  // write to the file
  await writeFile(dataPath, data);
  res.json(newData);
})

// 7. create a function that promisify's the fs.writeFile() function
function writeFile(dataPath, data){
  return new Promise( (resolve, reject) => {
    fs.writeFile(dataPath, JSON.stringify(data), (err) => {
      if(err){
        return console.error(err)
      } 
      resolve(data);
    })
  })
}

// 8. PUT: create data
app.put("/api/v1/dreams/:id", async (req, res, next) => {
  const selectedId = req.params.id;
  console.log(selectedId)
  const newDream = {
    dream: req.body.dream,
    id: selectedId
  }

  const updatedData = data.map(item => {
    if(item.id === Number(selectedId)){
      return newDream
    } 
    return item;
  });

  // set data to the updateData
  data = updatedData.slice();
  // write to the file
  await writeFile(dataPath, data);
  res.json(newDream);
});

// 9. DELETE: delete data
app.delete('/api/v1/dreams/:id', async (req, res, next) => {
  data = data.filter(item => item.id === Number(req.params.id));
  await writeFile(dataPath, data);
  res.json({"message":"successfully removed item"});
});

// 10. Start listening 
app.listen(PORT, ()=>{
  console.log(`listening at: http://localhost:${PORT}`)
});
```

### GET

**Step 5:**
```js
// 5. GET: get all dreams
app.get("/api/v1/dreams", (req, res, next) => {
  res.json(data);
});
```

**Step 6:**
```js
// 6. GET: get only a specific dream
app.get("/api/v1/dreams/:id", (req, res, next) => {
  const selected = data.find( item => item.id === Number(req.params.id) );
  res.json(selected);
});
```

### POST

```js
// 7. POST: create data
app.post("/api/v1/dreams", async (req, res, next) => {
  const newData = {
    dream: req.body.dream,
    id: data.length + 1,
  }
  // push the data to the data array
  data.push(newData);
  // write to the file
  await writeFile(dataPath, data);
  res.json(newData);
})

// 7. create a function that promisify's the fs.writeFile() function
function writeFile(dataPath, data){
  return new Promise( (resolve, reject) => {
    fs.writeFile(dataPath, JSON.stringify(data), (err) => {
      if(err){
        return console.error(err)
      } 
      resolve(data);
    })
  })
}
```


### PUT

```js
// 8. PUT: create data
app.put("/api/v1/dreams/:id", async (req, res, next) => {
  const selectedId = req.params.id;
  console.log(selectedId)
  const newDream = {
    dream: req.body.dream,
    id: selectedId
  }

  const updatedData = data.map(item => {
    if(item.id === Number(selectedId)){
      return newDream
    } 
    return item;
  });

  // set data to the updateData
  data = updatedData.slice();
  // write to the file
  await writeFile(dataPath, data);
  res.json(newDream);
});
```

* routing w/ URL parameters and query parameter

### DELETE

```js
// 9. DELETE: delete data
app.delete('/api/v1/dreams/:id', async (req, res, next) => {
  data = data.filter(item => item.id === Number(req.params.id));
  await writeFile(dataPath, data);
  res.json({"message":"successfully removed item"});
});
```





<!-- - How to build APIs with express:
  - `app.get`
  - `app.post`
  - `app.put`
  - `app.delete`
- `requests` and `response` ==> (res, req)
- 
- - Dynamic routes
  - url params
  - query params -->

<!-- ## Ephemeral Data Storage

TBD

## Example: API example and A Simple File-based data store

- Storing/updating json object on the server
- Writing files to the server
- maybe for later: node-fetch/isomorphic fetch or external API requests from the server -->

***
***
***

# Interfacing with your API

## cURL
> cURL is a commandline tool for creating network requests. The name stands for "Client URL" - https://en.wikipedia.org/wiki/CURL. 


- See: [Curl Cheatsheet](curl-cheatsheet.md)

## Postman
> Postman is a GUI based tool that allows you to test RESTful APIs. It is basically like cURL except with way more features and with a graphical user interface. 

- See: [Postman Cheatsheet](postman.md)


## Client-side interfacing

In the [Front-end JavaScript guide - Fetch API](javascript-frontend-guide.md#fetch-api) section, you saw how you can you the `fetch()` function to make network requests to 3rd party APIs. The only difference here is that now, you will be writing client-side code to interface with *your own api*. 


### Local development

When working locally, you will be making your network requests with the base url of your local development server. If you've been following along with this guide, it will be:

**Base URL:**
```
http://localhost:3000/
```

**API Routes**: for example
```
http://localhost:3000/api/v1/dreams
```

In your client side code, you can begin to write your GET, PUT, POST, DELETE requests to those API endpoints that you defined. You can see how you can send different requests with `fetch()` by passing in the relevant `method` in the **options** argument as well as any necessary `body` data. Those details are in the [javascript-frontend-guide - Fetch API](javascript-frontend-guide.md#fetch-api)


### Changing your request URL for deployment

When you have deployed to Glitch, for example, you will need to change your baseURL to your API such that it matches the URL to your application. 

**Base URL:**
```
http://localhost:3000/ ==> https://joeyklee-list-project.glitch.me/
```

**API Routes**: for example
```
http://localhost:3000/api/v1/dreams ==> https://joeyklee-list-project.glitch.me/api/v1/dreams
```


***
***
***
