# Week 01: Web Foundations

## Slides
* ↳ [Link to Week 1 Slides: Web Foundations](https://docs.google.com/presentation/d/1XIUdrdMb3u-Duhg9I7kL0kJz1uhQUeRylDFYlX5dfeg/edit?usp=sharing)

## About
This week, we will be starting out journey as developers of the web. 

As part of this week's lecture and discussion, we will go through a (very) quick history of the web and define some important concepts and definitions related to the internet and web development. 

A majority of the class will be focused on setting up your development environments and getting you into the practice of developing and deploying web applications through your first assignment.

## Exercises To Do Before Class
<!-- What materials (readings, tasks, exercises) should students complete before class to be prepared for the lesson. -->
* Fill out the appropriate form based on your section:
  * Joey: 
  * Cassie:


### Outcomes & Goals

This week your goal is to be able to speak to these following points:

* **Web Foundations**
  * Internet:
    * What is the Internet?
    * What is everything that happens when you navigate to a website?
    * What are websites comprised of?
  * Web Applications:
    * What is the difference between a website and a web application?
    * What is the front end/client-side?
    * What is the back end/server-side?
    * What is a database?
    * What is DevOps (developer operations)?
* **Development environment**:
  * Git/Github:
    * What is Git? What is GitHub? What is GitHub Desktop? How do they relate to web/software development?
    * How does git track changes in files? What are the commands to add and commit changes to files?
    * How do you connect your local git repository to the remote git repository?
  * Command line:
    * What's the difference between the command line and a GUI (graphical user interface)?
    * How do you use the command line to navigate a computer?
    * How do you use the command line to write software?
    * How do you use the command line to use git?
* **Client-side**:
  * What are all of the components of a front end website?
  * How do you create an HTML page?
  * What are the components of an HTML page?
  * Why do we need a server to serve up your HTML page?
* **Deployment**
  * How do you serve and test your site locally?
  * How do you make your website accessible via the Internet?
  * What is Glitch.com?

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

## Topics
### How the Internet Works
When we're creating websites and web applications, it's helpful to understand the infrastructure of the Internet. This helps us understand all of the steps in creating a website from scratch.

What is the Internet? It's a global network of computers connected to each other. They're not all directly connected to each other, which would look something like this:

<img src="https://mdn.mozillademos.org/files/8443/internet-schema-2.png" width="300" alt="Naive incorrect Internet diagram" />

Instead, computers are connected to intermediary routers, provided by an Internet Service Provider (ISP), whose only job is to direct messages from one computer to another. 

<img src="https://mdn.mozillademos.org/files/8453/internet-schema-7.png" alt="Accurate Internet diagram with ISP routers" width="300">

The Internet is different from the World Wide Web (WWW), which is the collection of information that can be accessed via the Internet. You can think of a library building as the Internet, and the books stored in the library as the world wide web.

Each computer has a unique IP (Internet Protocol) address, which you can think of like a street address. How would you be able to get mail if your address weren't unique? These addresses are of the form **nnn.nnn.nnn.nnn**, where nnn is a number from 0-255 (2^8 - 1).

![Two computers connected to the Internet with unique IP addresses](https://web.stanford.edu/class/msande91si/www-spr04/readings/week1/InternetWhitepaper_files/ruswp_diag1.gif)

When you navigate to a url in your browser, how is this translated to a website on the world wide web? A special type of computer, called a server, is holding all of the data and files necessary to make that website work. When you navigate to a url, your request is routed to the appropriate server, which gives you back all of the data you need. These are all of the steps:
1. You enter a URL into your browser, e.g. https://neopets.com. This url is called a "domain name". 
2. The browser converts the domain name into an IP address using a DNS (Domain Name Server). This special type of server contains a database that maps domain names to IP address.
3. Your browser sends a HTTP request to the computer at the returned IP address. HTTP stands for Hyper-Text Transfer Protocol, and it is then language that browsers and web servers speak to each other in.
4. The web server sends back an HTTP response, containing the website's HTML (Hyper-text Markup Language) document. Every single website has an HTML document which contains the structure of the web page, and also lists any additional resources the browser needs to request.
5. Your browser starts rendering the HTML, converting the HTML code to visual elements, known as the DOM (Document Object Model).
6. Your browser requests any additional resources linked to in the HTML, i.e. images, videos, javascript files, css, and repeats steps 3-5.
7. Once the website is loaded, your browser executes any JavaScript scripts, which could things like modify the DOM or make additional HTTP requests.

There's a couple of other specifics about how requests and servers work. When computers communicate with each other over the Internet, they also communicate over specific ports. These are a number between 0-65535 (2^16 - 1). The port specifies which application or service to connect to on a server. Computers run lots of applications at once, so the port is crucial to knowing which one to connect to. Ports are appended to the end of an IP address, i.e. **nnn.nnn.nnn.nnn:pppp**. When you navigate to a website, often the port is implicit; for example, https://neopets.com:443 is the same as https://neopets.com. The IP address with the port, of the format nnn.nnn.nnn.nnn:pppp is called a **socket**. 

Applications that are running on a computer, that are waiting for HTTP requests on a specific port are called **web servers**. It's confusing that the word server can refer to a physical computer connected to the Internet, and also a piece of software that returns HTML/JavaScript/CSS/JSON/etc. In this class we will primarily be talking about servers as a software application. 

We will eventually be creating web servers that run on our own computers. How do we access them from a browser? Your local computer has a special IP address, **127.0.0.1**, which is aliased to "localhost". When we create these web servers, we'll give them a specific port too, usually something like 8000 or 8080.

#### References
* https://web.stanford.edu/class/msande91si/www-spr04/readings/week1/InternetWhitepaper.htm
* https://developer.mozilla.org/en-US/docs/Learn/Common_questions/How_does_the_Internet_work
* https://wsvincent.com/what-happens-when-url/


### Modern Web Applications
- How are web applications structured? 
  - Front end - Code that runs in the browser. Typically consists of writing HTML, CSS, and JavaScript, creating interfaces for users to interact with
  - Back end - Code that runs on a server. This code consists of working with data and business logic. Could work in a variety of languages (in this class, JS running using Node.js), and interact with databases (in this class, MongoDB).
  - DevOps - 
- front end vs back end vs database vs hosting vs database hosting
- why build we build web applications / why not?
- what is a web *application* vs a website? (e.g. having database vs just static pages)


### Development Tools
- Development tools are applications that you work with in order to create web applications. 
- VSCode 
- showing hidden files and folders
- Command line (in VSCode vs Terminal application)
- Git (why?)
- HTML (using an index.html, linking to other files, using file urls)


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