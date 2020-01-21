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
  * Joey’s survey: https://forms.gle/i1mHxxPhuU8mv3Ac6
  * Cassie’s survey: https://forms.gle/Lkj9ue9VwD6ubFmV6


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
Web applications have lots of different components, but they are primarily composed of:
- Front end: Also known as client side code, this is the code that runs within a browser, which includes HTML, CSS, JavaScript, and media. This code is sent from a web server but is not executed there. 
- Back end: Also known as server-side code, this is the code that runs on a hardware server connected to the Internet. This code could be Python, Ruby, Rust, Haskell, etc. but in the context of this class is JavaScript running in Node.js.
- Database: This stores and persists your website's data. This can be a lot of information! The back end will typically fetch a portion of this data to send to the front end (e.g. if you went to the Wikipedia page for "Capybara", the backend would fetch the "Capybara" entry in the database and nothing else). In this class we will be using MongoDB. 

TODO insert a diagram, probably create one because none of the ones on the internet are good. 

When we create web applications, we run and test these different components on our local computer. When we are happy with what we have and ready to put it on the internet, we need to transfer this code to a computer that can serve files to the internet. This process is called **deployment**. Many companies provide servers that you can transfer your website files to, this is called **hosting**. These companies include Digital Ocean, AWS, and Google; for this class we will be using Glitch.com and Heroku. 


### Development Tools
In order to create websites and web applications, we use different tools to write, test, and deploy our code. These are called **development tools**. There are many different choices of tools; however, the ones we will go over in this class are used by many professional web developers and are the preferred tools of your instructors Cassie and Joey.

#### Text Editor
A text editor is an application in which you can create and edit text files. It's different from an application like Microsoft Word, in that it's specifically for writing code, rather than English. It's the place you write your HTML/JS/etc. files. 

In this class we will be using [VSCode](https://code.visualstudio.com/). It comes with a ton of features to make writing code easier, including tons of syntax highlighting and tons of extensions.

**Introduction Guide**: [Code Academy's Getting Started with VSCode](https://www.codecademy.com/articles/visual-studio-code)
**Intermediate Guide**: [Flavio Copes's A VSCode Tutorial](https://flaviocopes.com/vscode/)

#### Command Line
Have you ever opened the "Terminal" application (or maybe "Windows Command Prompt") on your computer? This is called a **command line interface**. You're probably used to interacting with your computer using its GUI (Graphical User Interface), made up of icons, windows, dropdown menus, and other visual components, which you use to perform actions on your computer. The command line is a different interface to your computer, in which you can only tell your computer what to do using text commands. Sometimes it can be frustrating to interact with your computer using the command line, but it gives you access to tools you can't use from the GUI. Many of the tools used to create web applications can only be used on the command line, therefore it's important to learn how to use it.

See the [command line guide](../guies/commandline.md) to get starting using the command line.

#### Version Control
When working on a piece of writing, it's common to make many drafts before settling on a final version. The same thing happens when you write software. Version control software keeps track of all of the changes you make, and stores them in a "ledger". It also helps you collaborate with other people—you can see the changes that you made, and ones that another person made. It's a pretty powerful tool, and invaluable when writing code.

The most widely used version control software is **Git**. In this class we will be using git as a command line tool. See [git guide](../guides/git.md) for an in-depth guide to getting started with git.

#### Source Code Hosting
[GitHub](https://github.com/) is a website for hosting and exploring source code. Many open source projects are hosted on this site, from [VSCode](https://github.com/microsoft/vscode) to [p5.js](https://github.com/processing/p5.js). We'll be using it in this class to host our code (and the git revision history) online. At first, we will use GitHub Desktop to push our **git repository** to GitHub, but mainly we will be using git from the command line.

#### Deployment
Once we're ready to make our web application public, we can deploy it. This is different from putting your code on GitHub, as this is a site for looking at the course code, versus the application that is created when the source code is executed. For this class we will be using [Glitch](https://glitch.com/) and later on [Heroku](https://www.heroku.com/).

See the [guide to importing a git repository to Glitch](https://help-center.glitch.me/help/import-git/) for a guide to deployment.

**NOTE**: Glitch is also an in browser code editor (like the [p5.js Web Editor](https://editor.p5js.org/)). However, for this class we will be writing all of our code locally, then pushing to GitHub, then importing your GitHub repository to Glitch.

### Your first deployed website
Now we're going to walk through creating our first website from scratch!

1. Create a new project folder and open it in VSCode. I have a folder in my home directory called "Development" where all of my code lives, but you can put it wherever works for you.
```sh
$ mkdir ~/Development/first-website
$ cd ~/Development/first-website
$ code .
```
**NOTE**: `code` opens VSCode from the command line. You may have to open VSCode and run "Shell Command: Install 'code' command in PATH".
2. Create a new file and save it as `index.html`.
3. Add the following content:
```html
<!DOCTYPE html>
<html>
  <head>
    <meta charset="utf-8" />
  </head>
  <body>
    <h1>Welcome to My Homepage</h1>
    <p>I hope you have a great day.</p>
  </body>
</html>
```
4. Save this and go back to your command line
5. Serve your site locally by running
```sh
$ python -m SimpleHTTPServer
```
6. Test your site by navigating to http://localhost:8000
![First Website Preview](../assets/first-website-preview.png)
7. Initialize your git repository and commit your changes.
```sh
$ git init
$ git add .
$ git commit -m "Initial commit"
```
8. Use GitHub Desktop to push your repository to GitHub.
![Gif Showing how to connect and push git repository](../assets/github_desktop.gif)
9. Get your repository's URL
![First Website GitHub](../assets/first-website-github.png)
10. Create a "New Project" on Glitch from your git repository URL
![Cloning git repo to Glitch gif](../assets/glitch_clone.gif)
11. Click "Show" -> "In a New Window" and you're done!
![Previewing Glitch project](../assets/glitch_show.gif)

### HTML
* ↳ [HTML Guide](../guides/html-guide.md)

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