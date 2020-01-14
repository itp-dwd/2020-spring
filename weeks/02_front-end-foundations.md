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
    * 
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
  

## Topics

### Web Design(ing)

Building front end web applications is about addressing both the **visual design** of the client facing interface and the **functionality** of the web application. 

In this class, we briefly introduce you to the the basic process and components of web design and then address how these designs come to materialize through code.

#### Research: User Resarch, Defining Requirements, Moodboards, and Inspiration

**Research**: Before anything else, any and every good design process will begin with **research**. Researach about your users, their needs, their desires, their pain points, their delights, what motivates them, what inspires them, what scares them, what keeps them engaged, what truly benefits them, and so on. 

**Requirements**: Your research will inform **the requirements** for your application. Does your design need to be interactive or is it a passive interaction? Does the subject warrant a certain color palette? Do certain typographic considerations need to be made based on your users or based on the briefing from your client or company's style guide? Does your site need to allow people to log-in to a service? Do you need to display data on the site? Based on questions such as these, you will define a requirements list of what **features** and **functionality** the front-end of your site/application will need. You can also add your own "nice-to-haves" section!

**Moodboards & Inspiration**: Simultaneously while you're researching and defining and refining your requirements, it helps to being collecting materials that can inform your web application's design concept. You can use services like [Are.na]() or [Pinterest]() or just use a folder full of images to collect inspiration of websites, images, interaction types, typography, colors, layouts, etc that might come to influence your visual design.

#### Sketching



#### Wireframing

#### Visual Designing

#### Style Guide


### Front End Development & HTML5



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