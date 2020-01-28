# The Web Browser Guide

## Table of Contents
- [The Web Browser Guide](#the-web-browser-guide)
  - [Table of Contents](#table-of-contents)
  - [How the web browser works](#how-the-web-browser-works)
  - [The Page Lifecycle](#the-page-lifecycle)
  - [The Web Platform](#the-web-platform)

## How the web browser works
The web browser is a magical tool. Seriously. It is amazing if you start to look into all the things the browser does. But web browsers themselves are just software that are designed and coded like any other software you use on your machine. They caveat is that web browsers are designed to be your portal to the world-wide-web. 

In the browser, you type a URL to the top of the URL input, press enter, and voila! Movies, cat gifs, the news, the weather, books, and chats with friends all appear in their full glory. 

What we're going to learn is that web browsers are like any other software application. They are built by people, in different organizations and institutions, and all function more or less the same way: 

* Assuming your machine is connected to the internet, you can use your web browser, the **client**, to make HTTP requests (using URLs) which are fulfilled by servers that are connected to the **world-wide-wide** through the internet. Let's say you request to go to "https://en.wikipedia.org" ==> 
* Your HTTP request to Wikipedia's server, for example, will tell Wikipedia to send back a webpage which is comprised of HTML, CSS, and JavaScript and all of the accompanying media such as videos and images. ==> 
* When that HTML, CSS, and JavaScript make it back to your web browser, the client, your browser starts to do something very very exciting -- it starts to go through what is called the [Browser Rendering Pipeline](http://dbaron.github.io/browser-rendering/). Baked into your web browser is the ability to take the structural components of your HTML, the style and layout specifications of your CSS, and the functionality and interactivity of your HTML elements as defined in the JavaScript and mash them together in a way that allows that web page to function as the creators of that webpage had envisioned. ==> 
* Thrilled, that you see the beautiful Wikipedia home page, you decide you'd like to learn more about weather forecasting and type into the search bar: `weather forecasting` and press enter ==>
* Your browser has now made another HTTP request, except this time a `POST` request that sends some data to the Wikipedia server that you're searching for an article about `weather forecasting` and Wikipedia's server which finds and exact match, sends back another webpage with HTML, CSS, and JavaScript and the associated images and data that is part of the web page. ==>
* Your browser then goes through the [Browser Rendering Pipeline](http://dbaron.github.io/browser-rendering/) once again, mashing together the HTML, CSS, and JavaScript as it did earlier in the exact same order as it did and always will. 

![Image showing a Wikipedia article about "weather forecasting" and all of the network requests fulfilled by the browser](/assets/week02-browser-01.png)
Image: Image showing a Wikipedia article about "weather forecasting" and all of the network requests fulfilled by the browser


## The Page Lifecycle

See: [How does the browser page lifecycle work?](https://stackoverflow.com/questions/44044956/how-does-browser-page-lifecycle-sequence-work), [Browser Life Cycle](https://dzone.com/articles/browser-life-cycle), and [How Browsers Work: Behind the scenes of modern web browsers](https://www.html5rocks.com/en/tutorials/internals/howbrowserswork/)

An important concept for web development is understanding the "Browser page lifecycle" which is the order in which CSS, HTML, and JavaScript are "handled", that is calculated/parsed/rendered/executed. 

The lifecycle can be broken down generally into the process of:

1. constructing the dom
2. handling css
3. rendering the tree
4. building the layout
5. painting the pixels to the screen
6. javascript

| constructing the dom | handling css | rendering the tree | layout | paint | javascript |
| :---: | --- | --- | --- | --- | --- |
| ![](https://i.stack.imgur.com/qBRao.png) | ![](https://i.stack.imgur.com/035w3.png) | ![](https://i.stack.imgur.com/Y9eFa.png) | ![](https://i.stack.imgur.com/eSgwA.png) | Converting all the previous steps into pixels on the screen | Execute the javascript |

Quite likely you won't need to worry about steps 1 - 5 until you start diving deeper into web performance considerations (e.g. using `css transforms` rather than changing their position). However, you will need to be aware of and be able to make sure your JavaScript is executed at the right time and web the DOM is loaded. 

For this, you will need to keep your eye on 2 things:

1. make sure you are loading/referencing your external JavaScript files in the correct order

  ```html
  
  <body>
      <div id="app"></div>
      <!-- javascript files -->
      <!-- the p5js library -->
      <script src="js/p5.js"></script>
      <!-- your own custom class that relies on p5 -->
      <script src="js/Dots.js"></script>
      <!-- your main sketch file that need BOTH p5 and Dots.js -->
      <script src="js/sketch.js"></script>
  </body>
  ```


2. make sure that you are executing your JavaScript AFTER your DOM is successfully loaded. 

  ```js
  window.onload = function() {
     initialize();
     appendToDOM();
   }
  ```

  this can also be written:

  ```js
  window.addEventListener('DOMContentLoaded', function(){
    initialize();
    appendToDOM();
  })
  ```



## The Web Platform

If you're coming from NYU ITP's Intro to Computational Media course, you'll have used p5.js. All those fun *sketches* you made with JavaScript with animating circles, squares, and images were made possible because your web browser has the ability to draw shapes, images, and video as pixels that rendered into the window of the browser on something called the **canvas**. The canvas is one of your web browser's many offerings however. Baked into your web browser are features like audio recording, speech recognition, geolocation, storage, networking, and more. 

Your browser provides APIs to these features and offerings (e.g. the canvas API, the geolocation API, the speech API, etc). Together these APIs comprise the web browser and all the things you are able to experience while using a web browser and you visit different web sites and interact with different web applications.
