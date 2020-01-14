# Week 01: Web Foundations

## Slides
* ↳ [Link to Week 1 Slides: Web Foundations](https://docs.google.com/presentation/d/1XIUdrdMb3u-Duhg9I7kL0kJz1uhQUeRylDFYlX5dfeg/edit?usp=sharing)

## Exercises To Do Before Class
<!-- What materials (readings, tasks, exercises) should students complete before class to be prepared for the lesson. -->
* Fill out the appropriate form based on your section:
  * Joey: 
  * Cassie:

### Essential Questions

- What are web applications?
- Why build web applications? Why to not build web applications? 
- What is the internet?
- What is a server? How is is different from a platforms-as-a-service? 
- What do we mean when we say the front-end (client side) vs. the back-end (server side) vs. devOps?
- How does communication work across the internet?

## Introduction

This week, we will be starting out journey as developers of the web. 

As part of this week's lecture and discussion, we will go through a (very) quick history of the web and define some important concepts and definitions related to the internet and web development. 

A majority of the class will be focused on setting up your development environments and getting you into the practice of developing and deploying web applications through your first assignment.


### Outcomes & Goals

This week your goal is to be able to speak to these following points:

* **Development environment**:
  * Git/Github:
    * What is Git? What is Github? and how do they relate to web/software development?
    * How does git track changes in files? What are the commands to add and commit commit changes to files?
    * How do you connect your local git repository to the remote git repository?
  * Command line:
    * Basics of of the command line: how to navigate between folders, how to create files, how to create folders.
    * Using the command line to: install open source software, set up git locally, connect to a local git repository to a remote github repository, set up a simple Node.js project with npm. 
* **Client-side**:
  * How to make an HTML page
  * The components of an HTML page
  * The importance of semantically meaningful HTML
  * Why do we need a server to serve up your HTML page?

## Topics
### How the Internet Works
- What is the Internet? A global network of computers connected to each other. This is different from the World Wide Web (WWW), which is the collection of information that can be accessed via the Internet. 
- How do computers communicate with each other? Using HTTP (Hyper-Text Transfer Protocol), it's the language that computers speak to each other on the Internet. 
- the Internet infrastructure
- Simplest concept: there's a computer and it has some code on it that tells it how to send and receive information (e.g. html files, images, videos, emails, etc).  
- IP addresses, ports, etc.


### Modern Web Applications
- front end vs back end vs database vs hosting vs database hosting
- why build we build web applications / why not?
- what is a web *application* vs a website? (e.g. having database vs just static pages)


### Development Tools
- VSCode 
- showing hidden files and folders
- Command line (in VSCode vs Terminal application)
- Git (why?)
- HTML (using an index.html, linking to other files, using file urls)
- Node.js (vs Browser, and why it exists)
- `npm`
- Express, serving files

### Web Development & Creative Practice
- how do different people use web development as part of their careers?
- guest speakers??
- web applications have many different uses and goals
- Profession web development vs using web development as a creative tool

### What we are not covering

Topics we are not covering, but are of importance:
* ...
* ...
* ...


## Pacing / Duration
<!-- Number of total hours the class session will take. Please try to take into account transition time between instruction and hands on exercises if any prep is necessary. -->
- :15 Introductions
- :15 Expectations, Logistics, Syllabus
- :15 Introduction to the Internet and Modern Web Development
- :45 Development Tools and Installation
- :45 Your first website, pushing to GitHub, deploying to Glitch
- :15 Deployment and documentation expectations (README, GitHub, Glitch)


## Materials Needed
<!-- What hardware, software, or other materials will students or teachers need for lessons. -->

* Laptop & Power charger
* **Text Editor** (VS Code):
  * [VS Code - Visual Studio Code](https://code.visualstudio.com/)
* **Web browser** (Chrome or Firefox preferred, but safari is ok): as a developer, you should be testing with multiple browsers! Please make sure to have both Chrome and Firefox at least.
  * [Chrome Download](https://www.google.com/chrome/)
  * [Firefox Download](https://www.mozilla.org/en-US/firefox/new/)
* **GitHub Account**:
  * [Sign up with Github.com](https://github.com/)
  * [Student Developer Pack](https://education.github.com/pack)
* **Glitch Account**:
  * [Sign up with Glitch.com](https://glitch.com/)
* **GitHub Desktop**
  * [Download](https://desktop.github.com/)

### Vocabulary (example)
* Internet: a global network of computers connected to each other
* IP Address: short for Internet protocol address, a unique of the form **nnn.nnn.nnn.nnn** where nnn is a number from 0-255.
* World Wide Web (WWW): the collection of information that can be accessed via the Internet. 

## Studio Exercise Descriptions
<!-- Descriptions of each exercise or phase of class. Similar to pacing but with more description of steps. -->
- Setting up development environment

### Using a text editor
- Using VSCode

### Using Git and GitHub
- Installing git (how does this work on Windows??)
- Initializing a Git repository
- [Coding Train - Git and GitHub for Poets](https://www.youtube.com/playlist?list=PLRqwX-V7Uu6ZF9C0YMKuns9sLDzK6zoiV)
- Documentation for deploying to Glitch.com from GitHub

### Node.js and the back end
- Downloading Node
- TODO: Should students download Node directly or use `nvm`?
- How to run a node script from the command line

### Using the command line
- TODO: how do you use unix on Windows??
- Using git
- Moving around directories

### Creating a static server with Node and Express
- [Example tutorial](https://alligator.io/nodejs/serving-static-files-in-express/), but maybe make our own

### Deploying to Glitch.com


## References
<!-- Include any sources cited, but not directly linked in the unit. -->
* [How Does the Internet Work?](https://web.stanford.edu/class/msande91si/www-spr04/readings/week1/InternetWhitepaper.htm)


<!-- 

Notes 

* Short history of the web?

* Blogs to follow
* What we are not going to learn in the class
  * list of topics/themes?
  * knowing what you know vs what you don't yet!
* Doing web development vs. working professionally as a developer vs. working professionally as a developer in industry vs. studio, etc
* Conceptual overview of how the web works?
* Overview of terms
* Clarification of terms
  * e.g. server vs platform as a service 
  * e.g. serverside javascript vs serverside XYZ
* The browser and the DOM
* Development tools 
  * git / github
  * text edior (vs code ) 
  * iterm2 or equivalent?
  * glitch account and/or heroku?

* Practice:
  * Git exercise + build a simple webpage
  * connecting github repo to glitch
  
* additional thoughts:
  * thinking about when to build from scratch vs. using templates. 
  * javascript patterns
    * think about state management, not polluting global scope, etc. 
    * e.g. pub-sub, MVC, MVVM, etc

-->

<!-- 

### Lecture
* Course overview & logistics
* Web Foundations:
  * in concept
  * in practice

### Studio
* warm up

### Assignment
* Part 0: Setup your development environment
  * Git/Github
  * Command-line tools
  * Install node.js
* Part 1: Create a simple webpage using HTML. It could be a point and click game, a quiz, a choose-your-own-adventure story, fiction, poetry, or art. 
* Part 2: Create a Node.js HTTP server to serve your file(s).
* Part 3: Push your project to a repository on GitHub
* Part 4: Deploy to Glitch by importing from GitHub
 -->