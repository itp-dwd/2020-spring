# BACKEND FOUNDATIONS GUIDE

## ABOUT

This backend foundations guide is a roadmap to a beginning your knowledge and practice of server-side programming with Node.js. 

In this guide we focus on the foundational knowledge of server-side JavaScript with Node.js. 

## PRE-REQUISITES

Before continuing, you should make sure to have explored the following guides and resources:

* [front-end javascript guide](javascript-frontend-guide.md)


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
  - [A simple Node.js Script](#a-simple-nodejs-script)
- [NODE.JS & THE NODE PACKAGE MANAGER (NPM)](#nodejs--the-node-package-manager-npm)
  - [What is NPM and what are Node Modules](#what-is-npm-and-what-are-node-modules)
  - [Project management with package.json](#project-management-with-packagejson)
  - [Installing Node Modules and dependency management](#installing-node-modules-and-dependency-management)

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

If you ever wondered why we need to run a **local web server** when we work on clientside projects to access images and external files like `.json` data or `.js` files, it's because we need a *server* to *serve up* those external files living outside of the HTML context. (Is this of those, "OMG I get it now" moments?). Remember, your client-side JavaScript can only access what is going on in the browser, so in order to access those other files, you need server-side code to make those files living in your file system accessible to your browser. 

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
Before we can get into programming our own webservers, we will take a second to explore the basics of server-side JavaScript with Node.js. 

Let's start with answering the question: What is Node.js? Node.js is a JavaScript that runs on the server rather than in the browser. 

In the past, we might write server-side code in Python, PHP, Java, C/C++, or Ruby. Whether it is Python or Ruby or Node.js, they all more or less do the same thing -- they allow you to write code that accesses/manipulates/runs computation on the files and data on your local file system. 

Aside: In my own experiences doing research and data analysis, I was writing code in Python and R to take big data files, run scripts that would do data cleaning and processing, calculate statistics, and generate figures and graphs of the data we'd collected from our weather and pollution sensors. During this time, I never interfaced with the web browser. We would just write code that ran on our machines that would output files into a folder so we could analyze our results and write about it later. Never in this process did I have to interface with a browser or even the internet for that matter. We just wrote code that was meant to live (and die) on our machines (or to be shared with other scientists and researchers). Another way to think about this is like writing the code for software that just lives on your computer like the Arduino IDE or Microsoft Word and Excel -- those progams can interface with files and directories on your machine, but otherwise those software just live on your computer.  

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

- `require()` vs. `import` 
  - there are 2 ways to import packages but depends on the version of Node.js you're using. For usage of `import` please use Node.js version >=12. 
- Core Node libraries
  - `fs`
  - `path`
  - `http`

## A simple Node.js Script

A node.js script that does X

TBD

***
***
***
# NODE.JS & THE NODE PACKAGE MANAGER (NPM)

## What is NPM and what are Node Modules

## Project management with package.json

## Installing Node Modules and dependency management 



***
***
***


