# Week 02: Front-end Foundations

## Slides
* ↳ [Link to Week 1 Slides: Web Foundations](https://docs.google.com/presentation/d/1XIUdrdMb3u-Duhg9I7kL0kJz1uhQUeRylDFYlX5dfeg/edit?usp=sharing)

## About

This week, we will be focusing on the *design* and *development* **process** and **syntax** of building front-end user interfaces and web sites. 

Emphasis this week will be on exploring frontend web development in the service of translating web designs to code. 

### Outcomes & Goals

This week your goal is to be able to speak to these following points:

* **Web Design(ing)**:
  * Sketching: 
    * Why is it important to sketch while designing for the web (and in general)?
  * Wireframing: 
    * What is a wireframe? Why are they important for the web design process?
    * What is a lo-fidelity wireframe?
    * What is a hi-fidelity wireframe?
    * What are ways to make wireframes?
    * What are best practices for wireframing?
  * Visual Design:
    * What is a lo-fidelity design?
    * What is a hi-fidelity design?
    * What is a click dummy? 
  * Style Guide:
    * What is a style guide?
    * What are the basic components of a style guide?
    * Why is a style guide important for web design and development?
* **Frontend Web Development**:
  * The Browser:
    * What is the web browser? What does it mean when the browser has an API and what are its functions?
    * What are the browser's developer tools?
    * How can you use the browser developer tools to debug your HTML/CSS/JavaScript?
  * HTML:
    * What is HTML? and what is the DOM?
    * What is the primary purpose of HTML?
    * Why is it important to use semantically meaningful tag names?
    * How do you translate the content of web designs into HTML?
  * CSS:
    * What is CSS?
    * What is the primary purpose of CSS?
    * How do you translate the layout and styles of web designs into CSS? And how do you effectively apply CSS `classes` and `ids` to HTML to best achieve the specifications of a web design?
    * What is the BEM convention for CSS? Why are CSS conventions helpful?
  * JavaScript
    * What is JavaScript?
    * What is the primary purpose of client side JavaScript?
    * How can you select HTML elements with JavaScript? What is the roll of CSS classes and ids in this context?

<!-- 
## Essential Questions

- How does the web browser work?
- What is the DOM? 
  - Why is it important to use semantically relevant tags instead of just "divs"?
- What are events? What are event listeners?
- How do we handle user inputs using HTML Forms? 
- What are the unique roles of HTML, CSS, and JavaScript?
- What does it mean to be "asynchronous" in development? How and why is this relevant for web development?
- What are JavaScript Array functions and how can they be used to achieve different tasks?

 -->

 ## Pacing / Duration
- :30 Review & Questions
- :30 Web Designing
- :XX Topic
- :XX Topic
- :XX Topic

## Materials Needed

* Laptop & Power charger
* **Text Editor** (VS Code):
  * [VS Code - Visual Studio Code](https://code.visualstudio.com/)
* **Web browser** (chrome or firefox preferred, but safari is ok): as a developer, you should be testing with multiple browsers! Please make sure to have both Chrome and Firefox at least.
  * [Chrome Download](https://www.google.com/chrome/)
  * [Firefox Download](https://www.mozilla.org/en-US/firefox/new/)
* **GitHub Account**:
  * [Sign up with Github.com](https://github.com/)
  * [Student Developer Pack](https://education.github.com/pack)
* **Glitch Account**:
  * [Sign up with Glitch.com](https://glitch.com/)
  

# Topics

## Web Design(ing)

Building front end web applications is about addressing both the **visual design** of the client facing interface and the **functionality** of the web application. 

In this class, we briefly introduce you to the the basic process and components of web design and then address how these designs come to materialize through code.

### Research: User Resarch, Defining Requirements, Moodboards, and Inspiration

**Research**: Before anything else, any and every good design process will begin with **research**. Researach about your users, their needs, their desires, their pain points, their delights, what motivates them, what inspires them, what scares them, what keeps them engaged, what truly benefits them, and so on. 

**Requirements**: Your research will inform **the requirements** for your application. Does your design need to be interactive or is it a passive interaction? Does the subject warrant a certain color palette? Do certain typographic considerations need to be made based on your users or based on the briefing from your client or company's style guide? Does your site need to allow people to log-in to a service? Do you need to display data on the site? Based on questions such as these, you will define a requirements list of what **features** and **functionality** the front-end of your site/application will need. You can also add your own "nice-to-haves" section!

**Moodboards & Inspiration**: Simultaneously while you're researching and defining and refining your requirements, it helps to being collecting materials that can inform your web application's design concept. You can use services like [Are.na]() or [Pinterest]() or just use a folder full of images to collect inspiration of websites, images, interaction types, typography, colors, layouts, etc that might come to influence your visual design.

### Sketching

![Web Design Sketches Photo](https://designmodo.com/wp-content/uploads/2011/09/Web-and-Mobile-Wireframe-Sketches-1.jpg)

The reality is that there's a lot of overhead to coding, especially when it comes to refactoring and entire code base, updating entire layouts due to a change in design, having to change colors, typography, font-sizes, and more. The point of sketching is to help you put your ideas on paper, to get feedback on those ideas, to assess the viability and appropriateness of your solutions to your/incoming requirements and more. 

Your sketches can be as epic or as simple as you desire, but the point is to have visual material that you can use to ask yourself and others if the requirements you've defined are being addressed in your structure and layout. The structure and layout defined in your sketches can be made clearer when you create wireframes. What are wireframes you ask? Find out in the next section!

### Wireframing

![Wireframe example from Wikipedia](https://upload.wikimedia.org/wikipedia/commons/4/47/Profilewireframe.png)

[Wireframing](https://en.wikipedia.org/wiki/Website_wireframe) is the process of taking what you've done in your sketches, considering your requirements, and beginning to translate those ideas into a more clear [information architecture](https://en.wikipedia.org/wiki/Information_architecture) which will eventually lead to a visual design. Wireframing is a *process* and not just a *product* of work that you do as a web designer/developer that allows you to identify "the practicality of a design concept" and to identify functionality, user flows, and experience of your application. It is by nature, iteritive and meant to help you reduce the overhead to major code changes downstream. The idea is to resolve your interactions and flows in the wireframes before moving on to production (though it can be helpful to begin *prototyping* with code in tandem).

As written in the [Wireframe Wikipedia](https://en.wikipedia.org/wiki/Website_wireframe):
> A website wireframe, also known as a page schematic or screen blueprint, is a visual guide that represents the skeletal framework of a website. Wireframes are created for the purpose of arranging elements to best accomplish a particular purpose...The website wireframe connects the underlying conceptual structure, or information architecture, to the surface, or visual design of the website. Wireframes help establish functionality and the relationships between different screen templates of a website. An iterative process, creating wireframes is an effective way to make rapid prototypes of pages, while measuring the practicality of a design concept. Wireframing typically begins between “high-level structural work—like flowcharts or site maps—and screen designs.” Within the process of building a website, wireframing is where thinking becomes tangible.*


### Visual Designing

![Example Visual Design from Dribbble, Zarah Rosiana](https://cdn.dribbble.com/users/3961357/screenshots/9511356/media/73dcdfa79eb5f0acd795127a94a91290.png)

While wireframes will begin to look and feel like the final design of your application, the **visual design** of your application is what you envision your application to look like in the end. This means adding all of the elements that will be on the final pages, even the real copy (e.g. text). Your visual design will include the image assets, styled buttons, correct margin spacing, colors, and typography. The v**isual design is your map** to how you will develop the front end of your web application and will be the metric of your success for your front end code.


### Style Guide

The style guide is your reference for all things related to the design of your application. This includes the specifications for all the aspects of your application that need specifying such as:
* logos
* colors
* typography
* iconography
* illustrations
* buttons/links
* input forms styles
* navigation
* and more...

![Duolingo Style Guide Screenshot](https://miro.medium.com/max/1536/1*igcvdM0mqD7haMdbgUORQg.png)

This document is a general reference for how different components of your site should look. 

You can look at different style guide examples here:
* [IBM Design Language](https://www.ibm.com/design/language/layout/overview)
* [BBC - GEL Design Patterns](https://www.bbc.co.uk/gel/guidelines/category/foundations)
* DuoLingo had a good one, but has been taken off the web!


## Part 2: Front End Development & HTML5

### The Browser

#### How the web browser works
The web browser is a magical tool. Seriously. It is amazing if you start to look into all the things the browser does. But web browsers themselves are just software that are designed and coded like any other software you use on your machine. They caveat is that web browsers are designed to be your portal to the world-wide-web. 

In the browser, you type a URL to the top of the URL input, press enter, and voila! Movies, cat gifs, the news, the weather, books, and chats with friends all appear in their full glory. 

What we're going to learn is that web browsers are like any other software application. They are built by people, in different organizations and institutions, and all function more or less the same way: 

* Assuming your machine is connected to the internet, you can use your web browser, the **client**, to make HTTP requests (using URLs) which are fulfilled by servers that are connected to the **world-wide-wide** through the internet. Let's say you request to go to "https://en.wikipedia.org" ==> 
* Your HTTP request to Wikipedia's server, for example, will tell Wikipedia to send back a webpage which is comprised of HTML, CSS, and JavaScript and all of the accompanying media such as videos and images. ==> 
* When that HTML, CSS, and JavaScript make it back to your web browser, the client, your browser starts to do something very very exciting -- it starts to go through what is called the [Browser Rendering Pipeline](http://dbaron.github.io/browser-rendering/). Baked into your web browser is the ability to take the structural components of your HTML, the style and layout specifications of your CSS, and the functionality and interativity of your HTML elements as defined in the JavaScript and mash them together in a way that allows that web page to function as the creators of that webpage had envisioned. ==> 
* Thrilled, that you see the beautiful Wikipedia home page, you decide you'd like to learn more about weather forecasting and type into the search bar: `weather forecasting` and press enter ==>
* Your browser has now made another HTTP request, except this time a `POST` request that sends some data to the Wikipedia server that you're searching for an article about `weather forecasting` and Wikipedia's server which finds and exact match, sends back another webpage with HTML, CSS, and JavaScript and the associated images and data that is part of the web page. ==>
* Your browser then goes through the [Browser Rendering Pipeline](http://dbaron.github.io/browser-rendering/) once again, mashing together the HTML, CSS, and JavaScript as it did earlier in the exact same order as it did and always will. 

![Image showing a Wikipedia article about "weather forecasting" and all of the network requests fulfilled by the browser](/assets/week02-browser-01.png)
Image: Image showing a Wikipedia article about "weather forecasting" and all of the network requests fulfilled by the browser


#### The Browser API

If you're coming from NYU ITP's Intro to Computational Media course, you'll have used p5.js. All those fun *sketches* you made with JavaScript with animating circles, squares, and images were made possible because your web browser has the ability to draw shapes, images, and video as pixels that rendered into the window of the browser on something called the **canvas**. The canvas is one of your web browser's many offerings however. Baked into your web browser are features like audio recording, speech recognition, geolocation, storage, networking, and more. 

Your browser provides APIs to these features and offerings (e.g. the canvas API, the geolocation API, the speech API, etc). Together these APIs comprise the web browser and all the things you are able to experience while using a web browser and you visit different web sites and interact with different web applications.


### HTML

At the most basic level, you can think of HTML as the **content** and **structure** of your user/client facing web page. 

The **content** is all of the text, images, videos, and just stuff that you want to reach your users. 

That content is **structured** using HTML in what is called the DOM or Document Object Model. The DOM, as its name suggests is a model for structuring a document with objects. 

The document is your webpage and your objects are the various things on your webpage. Those "things" on the webpage include things like paragraphs of text, headlines, titles, forms, buttons, images, videos, and more. 

The objects on your web page are expressed as **HTML tags** that generally have semantic meaning to the content those tags hold.

For example, the `<p> </p>` tag stands for "paragraph" 
```html
<p> This is my love letter to you.</p>
```

Another example, the `<h1> </h1>` tag stands for "header 1", or the main header or title of your page: 
```html
<h1>My Ode to Rainbows</h1>
```

![Simple HTML Page](/assets/week02-html-01.png)


#### Syntax

Here's some HTML tags you might start exploring

| Tag     | HTML tags                                | description                                         | example                                                                                                                                                                      |
|---------|------------------------------------------|-----------------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| h1      | `<h1></h1>`                              | Header 1                                            | <h1>Hello</h1>                                                                                                                                                               |
| h2      | `<h2></h2>`                              | Header 2                                            | <h2>Hello</h2>                                                                                                                                                               |
| h3      | `<h3></h3>`                              | Header 3                                            | <h3>Hello</h3>                                                                                                                                                               |
| h4      | `<h4></h4>`                              | Header 4                                            | <h4>Hello</h4>                                                                                                                                                               |
| h5      | `<h5></h5>`                              | Header 5                                            | <h5>Hello</h5>                                                                                                                                                               |
| p       | `<p></p>`                                | paragraph                                           | <p>I love you</p>                                                                                                                                                            |
| img     | `<img src="" alt="">`                    | image tag                                           | <img src="https://external-content.duckduckgo.com/iu/?u=http%3A%2F%2Fanimalsneedkisses.files.wordpress.com%2F2009%2F01%2Fllamas.jpg&f=1&nofb=1" alt="alpacas" width="100px"> |
| video   | `<video src="" alt="f">`                 | image tag                                           | <video src="https://thumbs.gfycat.com/PortlyMealyAfricanparadiseflycatcher-mobile.mp4" alt="funny video of puffy animals" autoplay width="200px">                            |
| a       | `<a href="" target="" rel=""></a>`       | link tags                                           | <a href="https://github.com/itp-dwd/2020-spring" target="_blank" rel="noreferrer">Link to ITP DWD course</a>                                                                 |
| form    | `<form method=""></form>`                | form                                                | <form method=""><input type="text" name="search" placeholder="e.g. search"> <input type="submit" value="submit"></form>                                                      |
| input   | `<input type="" name="" placeholder="">` | input                                               | <input type="text" name="search" placeholder="e.g. search">                                                                                                                  |
| button  | `<button></button>`                      | button                                              | <button>Click me</button>                                                                                                                                                    |
| div     | `<div></div>`                            | div, a generic box                                  | <div>I'm a div</div>                                                                                                                                                         |
| section | `<section></section>`                    | a section of content                                | <section>This is a section</section>                                                                                                                                         |
| nav     | `<nav></nav>`                            | navigation                                          | <nav>Navigation goes here</nav>                                                                                                                                              |
| ol      | `<ol></ol>`                              | ordered list, 1,2,3                                 | <ol><li>item number 1</li><li>item number 2</li> </ol>                                                                                                                       |
| ul      | `<ul></ul>`                              | unordered list                                      | <ul><li>item number 1</li><li>item number 2</li> </ul>                                                                                                                       |
| li      | `<li></li>`                              | list element, usually goes inside `ul` or `ol` tags | <li>item number 1</li>                                                                                                                                                       |
| aside   | `<aside></aside>`                        | an aside                                            | <aside>This is an aside</aside>                                                                                                                                              |
| article | `<article></article>`                    | an article                                          | <article>This is an article</article>                                                                                                                                        |

More tags and their suggested usage can be found at the [HTML5 Doctor Element Index](http://html5doctor.com/).


#### Structure

As we spoke about earlier, the DOM is comprised of objects that are defined by those HTML tags we see above. Your role in creating the structure of an HTML page is to take those tags and to create meaningful "parent and child" relationships between those elements. This means that your role as a front end developer is to think about **meaningful heirarchies** ideally reflect your information architecture and semantically organize your content into the DOM tree.


### CSS

### JavaScript






***
***
*** 

## Exercises To Do Before Class
<!-- What materials (readings, tasks, exercises) should students complete before class to be prepared for the lesson. -->

* Introduction to the DOM: https://www.taniarascia.com/introduction-to-the-dom/
* Basic HTML File: https://www.taniarascia.com/basic-html5-file/
* Design for Developers: https://www.taniarascia.com/design-for-developers/
* You don't need a CSS Framework: https://www.taniarascia.com/you-dont-need-a-framework/
* CSS: An Art, A Science, a Nightmare (Everything you should know): https://www.taniarascia.com/overview-of-css-concepts/



## Topics
<!-- This section can have many subheaders (h3's). This should list all of the topic areas, (e.g. Git, Using the command line), with links to guides and references.  -->

### HTML & the DOM
- HTML is the content and structure
- The DOM 
- Accessibility and semantic HTML. TODO link to a guide for accessible HTML?
- Don't know which element to use? See [HTML Doctor](http://html5doctor.com/).

### CSS
- CSS is the styling and layout
- Cassie's experience learning CSS: "CSS is poorly designed, but you learn a few hacks to make it work for you."
- TODO: Design of website layout that we are working towards (Holy Grail? Other?)
- Using HTML to include CSS
- The Box Model
  - What are all the ways to change the size of a DOM element with CSS?
    - width
    - height
    - border
    - margin
    - padding
- TODO What CSS attributes should we talk about?
  - `box-sizing`: border-box or content-box?
- CSS Selectors: ids and css classes
- How to name classes? Using BEM (why BEM? specificity). ONLY USE CLASSES. 
- Using Developer Tools to Debug CSS
- Nice to think about:
  - css animations
  - pseudo-classes
  - keyframe animations
  - layouts:
    - block
    - flexbox
      - 1-D display
    - css grid:
      - 2-D layouts
- CSS Tips and Advice
  - Don't use floats for layout because they can be confusing. Only use them to wrap text around another element.
  - Only use classes (and sometimes tag names for more general styles) to apply styles to elements.
  - `vertical-align: middle` doesn't do what you think it does.
  - Almost always use `* { box-sizing: border-box }`
  - units: `em`, `rem`, `px` ==> I'd always go for `rem` if possible.

### JavaScript
- "Vanilla JavaScript"
- Selecting DOM Elements by DOM type or CSS class or ID
  - Accessing Elements in the DOM: https://www.taniarascia.com/how-to-access-elements-in-the-dom/
  - Traversing the DOM: https://www.taniarascia.com/how-to-traverse-the-dom/
  - Making Changes to the DOM: https://www.taniarascia.com/how-to-make-changes-to-the-dom/
- Event binding / Event firing / listening
- Handling forms (only in the browser)
- `fetch`


### What we are not covering

NOTE: It should be noted that we are covering foundational knowledge of client side web development with HTML5. This is by no means a comprehensive deep dive into the intricacies and wonders of client side programming with HTML5, single page web applications, and front-end frameworks like Vue.js and React.js or build tools like Parcel and Webpack. Additionally we do not cover browser extensions or bookmarklets which are very exciting, but outside the scope of this course. 

Topics we are not covering, but are of importance:
* CSS Frameworks (i.e. Bootstrap, Semantic UI, Material)
* Front End JavaScript Frameworks (React, Vue, Angular)




### Vocabulary (example)
* DOM:
  * Document Object Model
* HTML:
  * Hypertext markup language
* CSS:
  * Cascading style sheets
* BEM:
  * Block-Element-Modifier
* AJAX:
  * Asynchronous Javascript And XML
* Callback functions:
  * ...

## Studio Exercise Descriptions
<!-- Descriptions of each exercise or phase of class. Similar to pacing but with more description of steps. -->

TBD

## References
<!-- Include any sources cited, but not directly linked in the unit. -->

TBD

<!-- 
### Lecture
* Focus on the "front-end":
  * HTML5: HTML, CSS, JavaScript
  * Layout: DOM and CSS
  * CSS Best practices using BEM
  * Adding Interactivity with Javascript

### Studio:

### Assignment
* Add interactivity using JavaScript to your Week 1 assignment. Feel free to use "vanilla" JavaScript or to use p5.js.
* Add styling using CSS and BEM conventions.
* Push your project to a repository on GitHub
* Deploy to Glitch by importing from GitHub
 -->


 <!-- 
 
 ### Lecture
* Focus on the "back-end":
  * Programming a server Node.js
  * Making programming a server easier with Express.js
  * Client-server communication: AJAX, RESTful APIs
  * Making API requests with Postman

### Studio
### Assignment
* Build on your previous work.
* Create an API using Express.js. 
* Use AJAX to fetch data from your API.
* Update your HTML with the fetched data.
* Deploy to Glitch
  -->