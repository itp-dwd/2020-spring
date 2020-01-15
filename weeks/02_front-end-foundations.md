# Week 02: Front-end Foundations

## Slides
* ↳ [Link to Week 2 Slides: Front end Foundations](#)

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

As you're reading this, you might get the feeling that what goes into an HTML page are pretty arbitrary. It's true that you can pretty much swing however you'd like, but there are some essentials. The boilerplate below has the key components:

This is via [Tania Rascia's Basic HTML5 Skeleton File](https://www.taniarascia.com/basic-html5-file/):
```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="utf-8" />
    <meta http-equiv="x-ua-compatible" content="ie=edge" />
    <meta name="viewport" content="width=device-width, initial-scale=1" />

    <title>Add your own title here</title>

    <link rel="stylesheet" href="css/main.css" />
    <link rel="icon" href="images/favicon.png" />
  </head>

  <body>
    <script src="js/scripts.js"></script>
  </body>
</html>
```
Notice we have:

* `<!DOCTYPE html>`: definition specifying `html` as the type of document
  * `<html lang="en">`: we have the outer-most `html` tag with a specification that this is `en` for english
    * `<head>`: we have a `head` tag that contains:
      * `meta` tags describing our page
      * `title` 
      * and our css `link` tags that link to our css style sheet
      * and a css `link` tag to a `favicon` which is the little icon that is shown in your browser tab
    * `</head>`: closing head tag
    * `<body>`: we have a `body` tag which is where the rest of our HTML will go:
      * (this is where all of your HTML would go: the divs, sections, header, main, etc)
      * at the very end we have our `script` tags
    * `</body>` : closing body tag
  * `</html>`: closing html tag


Now with this boilerplate, you can start adding the structure and content of the page you'd like to build within the `<body></body>` tags.

Here's a quick example of a basic HTML page:

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="utf-8" />
    <meta http-equiv="x-ua-compatible" content="ie=edge" />
    <meta name="viewport" content="width=device-width, initial-scale=1" />

    <title>Add your own title here</title>

    <!-- CSS can be read in via file reference or within the style tags -->
    <style>
      body{ 
        background-color: tomato;
        color:black;
      }
    </style>
    <!-- <link rel="stylesheet" href="css/main.css" /> -->
    <link rel="icon" href="images/favicon.png" />
  </head>

  <body>
    <div id="app">
        <!-- Navigation -->
        <nav>
          <p>Quick Links</p>
          <ul>
            <li> <a href="https://itp.nyu.edu/registration/Schedule.php?year=2019&semester=Fall" target="_blank">ITP Schedule</a></li>
            <li> <a href="https://tisch.nyu.edu/itp" target="_blank">ITP Home</a></li>
          </ul>
        </nav>
        <!-- header -->
        <header>
          <h1>My ITP Favorites</h1>
          <h2>A webpage for all my ITP favorite things</h2>
        </header>
        <!-- main body content -->
        <main>
            <!-- section -->
            <section>
              <h2>The People of ITP</h2>
              <ul>
                <li><a href="https://tisch.nyu.edu/itp/itp-people/faculty" target="_blank">Faculty</a></li>
                <li><a href="https://tisch.nyu.edu/itp/itp-people/staff" target="_blank">Staff</a></li>
                <li><a href="https://tisch.nyu.edu/itp/itp-people/alumni" target="_blank">Alums</a></li>
                <li><a href="https://tisch.nyu.edu/itp/itp-people/current-students" target="_blank">Current Students</a></li>
                <li><a href="https://tisch.nyu.edu/itp/itp-people/faculty/somethings-in-residence-sirs" target="_blank">Fellows</a></li>
              </ul>
            </section>
            <!-- section -->
            <section>
              <h2>My favorite courses at ITP</h2>
              <!-- article 1 -->
              <article>
                <header>
                  <h3>ICM</h3>
                </header>
                <p>I love ICM because the instructors are SO smart and cool and they care about my learning SO much. It's crazy.</p>
              </article>
              <!-- article 2 -->
              <article>
                <header>
                  <h3>Dynamic Web</h3>
                </header>
                <p>I love Dynamic Web Development because the instructors are SO smart and cool and they care about my learning SO much. It's crazy.</p>
              </article>
            </section>
        </main>  
    </div>
    <!-- JavaScript can be read in via file reference or within the script tags -->
    <script>
        setInterval( function(){
            const r = Math.random()*255;
            const g = Math.random()*255;
            const b = Math.random()*255;
            document.body.style.backgroundColor = `rgb( ${r}, ${g}, ${b})`
        }, 1000)
    </script>
  </body>
</html>
```

If you copy & paste the above code into a blank text file ==> then save it as `index.html` or `my-itp-page.html` ==> and double-click on that file, you'll see something like this in your browser:

![GIF of the bare bones HTML page created above](../assets/week02-html-02.gif)

The point of the above exercise is to see how HTML can be nested within tags to create relationships between `parent` and `children` tags and how there might also be `sibling` tags, and more. 

We know that our page has some structure that is semantically meaningful, but to our website viewers, they just see the content we've provided to them in the rawest form. What if we wanted to create our own layout, apply styling to the links and titles, add new typography, and make some better color choices? That's where CSS comes in. Read on for more.

NOTE: explore defining the HTML structure before putting too much or any CSS onto the page. A well structured HTML page will naturally reveal the architecture it is meant to showcase. 

### CSS

> Cassie's experience learning CSS: "CSS is poorly designed, but you learn a few hacks to make it work for you."

Cascading Style Sheets (CSS). It's wonderful, it's horrible, it's the way we apply layout and style to our DOM. Love it or hate it, it's what we've got and frankly, it can feel like magic once you get an handle on it. With CSS you can create delightful animations, fancy hover effects, and dynamic and engaging visual interfaces. The trick is to practice, practice, practice and get a feel for the materiality of CSS as it interacts with HTML and JavaScript.

CSS can be broadly categorized by the properties that affect:

* **layout**: where things are on the page
  * `display`
    * `block`
    * `inline`
    * `inline-block`
    * `flex`
    * `grid`
    * `none`
  * `position`
    * `fixed`
    * `absolute`
    * `relative`
  * margins:
    * `margin`, `margin-top`,`margin-right`, `margin-bottom`, `margin-left`
* **aesthetics**: how an element looks
  * color:
    * `background-color`
    * `border`
  * typography:
    * `color`
    * `font-family`
    * `font-size`
    * `font-weight`
    * `line-height`
    * `letter-spacing`
  * size:
    * `width`
    * `max-width`
    * `min-width`
    * `height`
    * `max-height`
    * `min-height`
    * `box-sizing`
    * `padding`, `padding-top`,`padding-right`, `padding-bottom`, `padding-left`
  * shape:
    * `border-radius`

Those properties that can take a "length" or "size" value can be styled using different units:

The units you'll likely use most:
| unit |  description | example |
| :---- | ---         | --- |
| `px` | absolute pixel units | `div { width: 32px; height: 32px }` |
| `rem` | relative units to the font-size of the root element |  `div { width: 2rem; height: 2rem }` |
| `%` | percentages |  `div { width: 50%; height: 50% }` |
| `vw` | relative to the view width |  `div { width: 100vw; height: 200px }` |
| `vh` | relative to the view height | `div { width: 100vw; height: 80vh }` |

You can see the other absolute and relative units at the [W3 Schools Link on CSS Units](https://www.w3schools.com/CSSref/css_units.asp)


#### HTML default styles and layouts 

Before we continue, I will take a second to explain that your web browser and different HTML elements have **default styles** associated with them.

For example all header tags like `h1`, `h2`, `h3` etc are all `block` level elements and take up 100% of the line that they are on. Other features like `button`s are styled with rounded borders, have a light grey background, and create the illusion of being depressed when clicked. `input` tags also have outlines and white backgrounds by default and sliders also come with their default styles as well. 

Some examples:

* **link tag**: by default they are blue with an underline
  * <a href="#">I'm a link tag</a>
* **block quote**: 
  * <blockquote>Block quotes have a mean left and right margin</blockquote>

You can see a list of those default values at the [W3 Schools - CSS Default Values Reference](https://www.w3schools.com/cssref/css_default_values.asp). 

It's helpful to know that different HTML elements have their default styling and as a result will affect your layout and views if you do not override them. 

If you want to have complete control over the the styles of your HTML elements, you can use the [CSS Normalize](https://necolas.github.io/normalize.css/) package to normalize all the CSS styles of all the HTML elements across different browsers.


#### Layouts: `inline` vs `block` Elements

![Illustration of different display properties](https://i.stack.imgur.com/mGTYI.png)

As mentioned above, HTML elements come with default styles. As we begin to talk about layouts in CSS, we start our discussion at `inline` vs `block` level elements. 

In simple terms:

* `display:block`: makes an element a block level element which means it will take up the entire level that it exists on. Headers like `h1` and `h2` tags 
* `display:inline`: makes the element take up only as much space as the content within it, and it means that any other elements following it will try to fit themselves onto the the same line (assuming they are also `inline` elements). Inline elements like `input`, `button`, `a` tags are are examples of inline elements. The height and width of an`inline` element CANNOT be defined.
* `display:inline-block`: are similar to `inline` elements in that they only take up as much space as the content within them, HOWEVER, `inline-block` elements can take `height` and `width` definitions. 

A demo of these 3 display properties can be found here:

* ↳ [Block, Inline, Inline-Block Demo](https://editor.p5js.org/joeyklee/sketches/whr4o6F70)

![Screenshot of block, inline, or in-line block display](/assets/week03-css-display-01.png)

In a more realistic scenario, you might want to try to format a page using just block and inline elements, and you'll start to see that, while powerful, you'll start to run into some limits. In the following demo, you'll see some new syntax that we've not talked about including references to:

* `transform: translate(<X>, <Y>)`
* `margin: 0 auto`
* pseudo classes for `<a>` tags such as `:active`, `:link`, `:visited`
* the `::after` pseudo class
* and `float:left` 
* `background-image: url()`

See the demo here:

* ↳ [CSS layout using block, inline-block, and float](https://editor.p5js.org/joeyklee/sketches/6pQmvN2Bs)

![CSS layout using block, inline-block, and float](/assets/week03-css-layout-01.png)

What is important to recognize is the existence of these properties and that we use them to create layouts when we're limited with our layout and positioning tools. To get around some of these limitations, there are more advanced and tried and true layout methodologies that you will master on your developer journey. These are `flexbox` and `grid`. In this course will focus on `flexbox`, but `grid` will no doubt be part of your CSS tool set as you continue to learn.
  

#### Layouts: Flexbox

![CSS Flexbox Illustration](https://crouhana.com/wp-content/uploads/2016/01/css3-flexbox.jpg)

Flexbox! This is going to be the main focus of our discussion on CSS layouts. Why? Because, flexbox is:

* well supported across browsers,
* not hacky (e.g. using floats -- float:left, float:right, etc -- can be tricky)
* and it's well documented with lots of examples and resources to draw from. 

##### Flexbox essentials: parents of the flex

##### Flexbox essentials 1: what you need to know:

* `display:flex` 
  * sets the parent DOM element as a **flexbox** container. By default, if the `flex-direction` property is not set, your DOM element will be set to  `flex-direction:row`.
* `flex-direction: (row|column)` 
  * a flexbox container can organize it's child elements either **horizontally** as a `row` or **vertically** as a `column`. Setting the `row` or `column` defines the **main axis**. How the child elements are **aligned** or **justified** will depend on the the **main axis**. 
* The power of flexbox container lies in it's ability to:
  * **justify** how those child elements are distributed *along the defined main axis* and to
  * * **align** the child elements *perpendicular to the defined main axis* (aka the **cross axis**).

Let's take a look at what this means. 

When your parent flexbox container is set to: `flex-direction:row`, 
* your **main axis** is going in the *horizontal* direction
* your **cross axis** is going in the *vertical* direction
* This means that:
  * `justify-content:(flex-start | flex-end | center | space-between | space-around | justify-between)` will change how your items are distributed *horizontally*. In the gif below, the content is justified with space between each item. 
  * `align-items:(flex-start | flex-end | center | space-between | space-around | justify-between)` will change how your your items are distributed *vertically*. In the gif below, the items are switching between `flex-start` (the the vertical start of the row) and `flex-end` (the vertical end of the row).
  
  ![](../assets/week03-css-flex-02.gif)

When your parent flexbox container is set to: `flex-direction:column`, 
* your **main axis** is going in the *vertical* direction
* your **cross axis** is going in the *horizontal* direction
* This means that:
  * `justify-content:(flex-start | flex-end | center | space-between | space-around | justify-between)` will change how your items are distributed *vertically*. In the gif below, the content is justified with space between each item. 
  * `align-items:(flex-start | flex-end | center | space-between | space-around | justify-between)` will change how your your items are distributed *horizontally*. In the gif below, the items are switching between `flex-start` (the the horizontal start of the column) and `flex-end` (the horizontal end of the column).
  
  ![](../assets/week03-css-flex-03.gif)

##### Flexbox essentials 2: also good to know

You can get pretty far by knowing what is in the [flexbox essential 1 section](#flexbox-essentials-1-what-you-need-to-know), however, there's more! 

**What if I want my elements to wrap in a flex container?**

You can specify: `flex-wrap: (nowrap | wrap | wrap-reverse)` on your flex container.

A flex container knows when it's child elements have wrapped onto multiple rows or columns. When you are working with flex containers where elements are **wrapping** onto **multiple** rows or columns, you will have to use **align-content** & **justify-content** appropriately depending on what you've defined as your **main axis**. 

As we did above, let's look at what happens when we change our **main axis** but change how the **align-content** property.

When your parent flexbox container is set to: `flex-direction:row`, and `flex-wrap: wrap`:

* your **main axis** is going in the *horizontal* direction
* your **cross axis** is going in the *vertical* direction
* This means that:
  * `align-content:(stretch | flex-start | flex-end | center | space-between | space-around | justify-between)` will change how each row of content is distributed within the flex container.
  
  ![](../assets/week03-css-flex-04.gif)

When your parent flexbox container is set to: `flex-direction:column`, and `flex-wrap: wrap`: 

* your **main axis** is going in the *vertical* direction
* your **cross axis** is going in the *horizontal* direction
* This means that:
  * `align-content:(stretch | flex-start | flex-end | center | space-between | space-around | justify-between)` will change how each column of content is distributed within the flex container.
  
  ![](../assets/week03-css-flex-05.gif)

##### Flexbox essentials 3: children of the flex

So far we've been talking specifically about the flex container -- the parent -- and we've seen how setting different properties on the parent container affect the children elements within it. 

It turns out that the children of a flex container can take on special properties that affect their **size**, **order**, and **position**.

* **properties that affect flexbox children's size**
  * `flex-grow: <integer>`
  * `flex-shrink: <integer>`
  * `flex-basis: ( rem| % | auto)`

* **properties that affect flexbox children's order**
  * `order: <integer>`

* **properties that affect flexbox children's position**
  * `align-self: (auto | flex-start | flex-end | center | baseline | stretch);`

See: [CSS Tricks - A Guide to Flexbox, "Properties of the Children"](https://css-tricks.com/snippets/css/a-guide-to-flexbox/) to see how these properties of flexbox children take shape.


##### Quick flexbox reference: flexbox layouts

* [vertically centering things](https://editor.p5js.org/joeyklee/sketches/4pHlQa7KT)
* [the holy grail](https://editor.p5js.org/joeyklee/sketches/pl_3cVLuM)


##### Flexbox references:
* [CSS Tricks - A Guide to Flexbox](https://css-tricks.com/snippets/css/a-guide-to-flexbox/)
* [Flexbox Froggy Game](https://flexboxfroggy.com/)


#### Media Queries & Responsive Layouts

![Illustration of Responsive web design across different devices and screen sizes](https://external-content.duckduckgo.com/iu/?u=https%3A%2F%2Fcdn-images-1.medium.com%2Fmax%2F2000%2F1*uCt7-Nb0vv1yrIAFUZpXjQ.jpeg&f=1&nofb=1)

Responsive design, whut whuuuut. In our modern web world, with so many different devices and screen sizes, responsive design is the name of the game. 

Luckily, CSS gives us the ability to apply different styles depending on the size of the screen or the device being used through **media queries**. You can learn more about the intricacies of CSS media queries later on, but for now, here's the general workflow.

For a desktop first layout (as opposed to mobile first):

* Step 1: define your CSS styles as you would normally based on the browser window of your computer. 
* Step 2: identify **screen size breakpoints** where you've identified where your web page styles start to break down or otherwise look cluttered or for lack of better words, "not good". Common break points:
  * small devices: < `600px`
  * small tablets and large phones: `768px`
  * laptops and big tablets: `992px`
  * large laptops/large screens: `1200px`
* Step 3: begin applying **media queries** based on those breakpoints throughout your stylesheet. 

##### Media queries in action: `@media`

The way media queries work is by defining a **lower** and **upper** boundary for the size of screen that your styles should apply to. 

**Changing the typography size:**

* ↳ [CSS Media Query Demo - changing the title size](https://editor.p5js.org/joeyklee/sketches/s-zkOMFOZ)

![CSS Media queries changing the title size](../assets/week03-css-media-queries-01.gif)


**Changing the layout:**

* ↳ [CSS Media Query Demo - changing the layout](https://editor.p5js.org/joeyklee/sketches/2qOSdoNzr)

![CSS Media Query Demo - Changing the layout](../assets/week03-css-media-queries-02.gif)


#### BEM: 

By now you've probably looked a bunch of the CSS code and the HTML and thought, "wow, what a mess!" If you haven't, then kudos, you're like a superhuman. For the rest of us, the HTML/CSS mashup can be tricky to read, write, and maintain. Without best practices and good conventions and otherwise just a compass to follow, the arbitrariness of how to structure and identify HTML elements with CSS can be totally overwhelming and confusing. 

SO, somewhere out there in the big 'ol universe, someone came up with what is called BEM or the Block-Element-Modifier convention for CSS naming and HTML structuring. 

The basic premise is that your frontend is composed of **blocks** of HTML. Within those blocks, you have **elements**. Those **blocks** and **elements** can be given **modifiers** which act add additional styling to that **block** or **element** that is appended to. 

You can read more about how to logically separate out what is a **block** vs an **element** vs a **modifier** at this [Introduction to BEM](http://getbem.com/introduction/).

As a quick example, let's take a look below. You'll notice that:
* every HTML object receives a `class` name. 
* a **block** is usually the parent container and is implemented like so: e.g. `class="header"`
* a **element** is an element that is reliant on the block and is implemented like so: e.g `class="header__title"`
* a **modifier** is an flag that changes the style of an element or block and is implemented like so: e.g. `class="header__title header__title--pink` or `class="header header--pink`.

We have a header **block**, and a **title** element, with a pink **modifier**.
```html
<body>
  <!-- our block -->
  <header class="header">
    <!-- our element with a modifier-->
    <h1 class="header__title header__title--pink">Vancouver, I love you.</h1>
  </header>
</body>
```

```css
/* our block is a 200px tall and 100% wide that aligns all the elements to the center */
.header{
  display:flex;
  flex-direction: row;
  align-items:center;
  justify-content:center;
  width:100%;
  height:200px;
}

/* our &__title element of our header */
.header__title{
  font-size: 3rem;
}
/* our title modifier */
.header__title--pink{
  color:pink;
}
```

As outlined beautifully in this article [BEM by example](https://seesparkbox.com/foundry/bem_by_example) is to resist the temptation to create complex nested BEMs with infinity underscores separating elements. (I'll admit I've broken this rule too many times and regret it every single time). Keep your BEM organized and shallow, so you can keep track of the way your styles are being applied, but don't feel like this is a hard and fast rule. Rules are (sometimes) meant to be broken. 

via [BEM by example](https://seesparkbox.com/foundry/bem_by_example) - this example does a good job expressing best practices for shallow naming for BEM. As you see the BEM convention across the web, you'll see that it isn't always so simple to keep things shallow, but you should try!
```html
<!-- DO THIS -->
<figure class="photo">
  <img class="photo__img" src="me.jpg">
  <figcaption class="photo__caption">
    <blockquote class="photo__quote">
      Look at me!
    </blockquote>
  </figcaption>
</figure>

<style>
  .photo { }
  .photo__img { }
  .photo__caption { }
  .photo__quote { }
</style>


<!-- DON'T DO THIS -->
<figure class="photo">
  <img class="photo__img" src="me.jpg">
  <figcaption class="photo__caption">
    <blockquote class="photo__caption__quote"> <!-- never include more than one child element in a class name -->
      Look at me!
    </blockquote>
  </figcaption>
</figure>

<style>
  .photo { }
  .photo__img { }
  .photo__caption { }
  .photo__caption__quote { }
</style>
```

##### BEM References:
* [Get BEM](http://getbem.com/introduction/)
* [Maintainable CSS With BEM](https://www.integralist.co.uk/posts/bem/#4)
* [‘Why BEM?’ in a nutshell](https://blog.decaf.de/2015/06/24/why-bem-in-a-nutshell/)
* [BEM by example](https://seesparkbox.com/foundry/bem_by_example)

#### Supplementary -- Layouts: Grid

![CSS Grid illustration](https://res.cloudinary.com/practicaldev/image/fetch/s--bS_SjGm5--/c_limit%2Cf_auto%2Cfl_progressive%2Cq_auto%2Cw_880/https://thepracticaldev.s3.amazonaws.com/i/4h381z8znyw4w0vcnv8z.png)

We are not going to go into CSS grid here in detail, but you should know that CSS grid is quite likely going to be part of your future as a web developer. The major innovation of CSS grid is that, for the first time, you can now create 2-D layouts. This is big! With all the other CSS layout properties, we were only given the ability to create 1-D layouts that we puzzeled together in creative ways. Now with `grid` you can:

On your parent element, specify:
* the number of columns, 
* the number of rows,
* the gap between columns,
* the gap between rows,

And on your children elements, specify:
* how many columns and rows each child element should fill

In the end, using CSS grid can be verbalized like,
> "I want a 3 column grid, with 8 rows. 
> 
> In the first 2 rows, I want my header to occupy all 3 columns. 
> 
> In the next of the 4 rows, I want to have on the left, an area for an aside element that takes up 1 column, and a main element that takes up 2 columns.
> 
> Last, I want a footer element that up the last 2 rows and occupies all 3 columns."

![CSS Grid layout](/assets/week03-css-grid-01.png)

In CSS Grid, this would look like:

```html
<html>
  </head>
    <style>
        *{
          box-sizing:border-box;
          margin:0;
          padding:0;
        }
        html, body{
          width:100%;
          height:100%;
        }
        #app{
          width:100%;
          height:100%;
          display:grid;
          grid-template-columns: 1fr 1fr 1fr;
          grid-template-rows: repeat(8,1fr); /* also: 1fr 1fr 1fr 1fr 1fr 1fr 1fr 1fr */
          grid-row-gap: 1rem;
          grid-column-gap: 1rem;
        }
        .header{
          grid-column-start: 1;
          grid-column-end: 4;
          grid-row-start: 1;
          grid-row-end: 3;
          background-color: blue;
        }
        .aside{
          grid-column-start: 1;
          grid-column-end: 2;
          grid-row-start: 3;
          grid-row-end: 7;
          background-color: yellow;
        }
        .main{
          grid-column-start: 2;
          grid-column-end: 4;
          grid-row-start: 3;
          grid-row-end: 7;
          background-color: red;
        }
        .footer{
          grid-column-start: 1;
          grid-column-end: 4;
          grid-row-start: 7;
          grid-row-end: 9;
          background-color: pink;
        }
    </style>
  </head>
  <body>
    <div id="app">
    <header class="header"></header>
    <aside class="aside"></aside>
    <main class="main"></main>
    <footer class="footer"></footer>
    </div>
  </body>
</html>
```

There's a lot more to know about CSS grid, but hopefully you can see how grid can be helpful for creating 2D layouts in the browser.

Some CSS Grid references: 
* [NYT Open, CSS Grid for Designers](https://open.nytimes.com/css-grid-for-designers-f74a883b98f5)
* [CSS Grid generator](https://cssgrid-generator.netlify.com/)




<!-- 
#### Box Model

#### Position

#### Display

#### Units

#### BEM: The Block-Element-Modifier Convention
-->

#### CSS References:
* http://learnlayout.com/
* https://flukeout.github.io/
* https://flexboxfroggy.com/
* https://codepip.com/games/grid-garden/ 


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