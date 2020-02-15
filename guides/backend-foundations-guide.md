# Backend Foundations Guide

## About

This backend foundations guide is a roadmap to a beginning your knowledge and practice of server-side programming with Node.js. 

In this guide we focus on the foundational knowledge of server-side JavaScript with Node.js. 

## Pre-requisites

Before continuing, you should make sure to have explored the following guides and resources:

* [front-end javascript guide](javascript-frontend-guide.md)


# Client-side JavaScript vs. Server-side JavaScript

In this guide we are talking about server-side JavaScript. This means that we are moving away from the client-side where we use JavaScript to add interactivity to our websites. 

With server-side JavaScript, what we're talking about is writing JavaScript for a server environment. This means that our server-side JavaScript does not have access to a browser context; no p5.js, no canvas, no web audio, no DOM manipulation, nada. 

So what then is server-side JavaScript for? Instead of writing JavaScript to interact with the DOM, now we're turning our attention to ways we can write JavaScript to interact with our computer's file system, including data that we want to process and store, databases that live on our computer, and other processes that do not live in the browser. You can think of server-side JavaScript as a way to write code that allows us to bridge together 2 environments that otherwise live separately: the browser and the server. We will see in subsequent sections how we can create APIs to open up connections between these two environments. 

Here we outline some of the major differences, uses, advantages, and disadvantages of client-side vs. server-side code:

| Features | **client-side** JavaScript | **server-side** JavaScript |
| :--- | --- | --- | 
| **Where it runs** | In a browser environment | On a server or your machine | 
| **Advantages** | 1. Has access to the browser and the web platform (e.g. canvas, web audio, DOM), 2. Feedback is potentially more visual (e.g. you can see how your JS affects the DOM) | 1. Has access to the file system of the machine, 2. potentially faster computation, 3. Potentially more storage and memory access | 
| **Disadvantages** | 1. Does not have access to your local file system | 1. Has no "window" or DOM or access to the browser environment, 2. Can be more abstract since feedback is only through the terminal | 
| **Purpose** | 1. For adding interactivity and functionality to websites and client facing applications and 2. To communicate with servers via APIs to get data and bring them to the client. | 1. For handling data, serving up websites, for interfacing with a database, for automating processes and 2. To create API endpoints for clientside applications to send and retrieve data.  | 

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