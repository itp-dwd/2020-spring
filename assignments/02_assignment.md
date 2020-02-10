# Assignment 2: Making & Breaking the Grid - Swiss Poster Design

## Briefing

Your assignment this week is to **design** and **develop** a website about New York using a strong grid drawn from [Swiss Poster Design examples](https://duckduckgo.com/?q=swiss+poster+design&t=ffab&iax=images&ia=images). 

Your goal this week is to practice defining a grid and ensuring you can layout and position any and every element *exactly* as you want. This takes a keen awareness and knowledge of CSS layout and positioning, specifically with flexbox. You will be able to take artistic license in "making and breaking the grid" but in general, your task is to 




|     |     |     |
| :--- | --- | ---   |
|![Swiss Bauhaus Poster Design](https://mir-s3-cdn-cf.behance.net/project_modules/disp/846f1d30168169.560573d11654d.jpg) | ![Smashing Magazine, Swiss Poster Design Review](https://cloud.netlifyusercontent.com/assets/344dbf88-fdf9-42bb-adb4-46f01eedd629/30ec28ab-658a-4397-a974-580743f02566/poster3.jpg) | ![Designspiration, Swiss Poster Design](https://dspncdn.com/a1/media/692x/6f/6a/d1/6f6ad1ecf3ad3577d5b3e184339a82e0.jpg) |

## Required Reading

* [Web Design Process Guide](../guides/web-design-process.md)
* [Design for Developers - structuring the DOM and styling](https://www.taniarascia.com/design-for-developers/)
* [CSS Guide](../guides/css-guide.md)
  * Specifically:
    * [CSS: An art, a science, a nightmare (everything you should know) ](https://www.taniarascia.com/overview-of-css-concepts/)
    * The sections on layout - flexbox and BEM conventions
* [JavaScript Frontend guide](../guides/javascript-frontend-guide.md)
  * Specifically:
    * [JavaScript and the DOM](../guides/javascript-frontend-guide.md#javascript-and-the-dom) which includes selecting and updating the DOM in JavaScript and JavaScript Events
* [Dev Tools Guide](../guides/dev-tools.md)
* [You don't need a framework for responsive design](https://www.taniarascia.com/you-dont-need-a-framework/)

## Requirements

Your assignment will be comprised of four parts: `design` > `development` > `deployment` > `documentation`

### Part 1: Sketching, Wireframes, and Design specifications
Effective front end web development, is as about able to translate an interface or visual design into code and identifying how to combine content with layout, structure, and styling.

Part 1 of this assignment is about focusing on organizing **typography**, **layout**, and **color** *before* you start coding. We would like to see:

* 1. **Sketches**: Annotated hand-drawn sketches of your layout and content
* 2. **Wireframes**: Wireframes that translate your hand-drawn sketches into a digital format
* 3. **Design**: A "final" design that breathes life into your wireframes
* 4. **Style Guide**: Basic style guide that is specifies at the very least about your typographic hierarchy, your grid, and color palette and acts as your project's visual design source during development. 

NOTE: If you are coming from a UX design or classical design background and have done this work before, you'll know that it takes an IMMENSE effort to do all those aspects above with full fidelity. The point of this part of the assignment is to cue you into these steps as critical steps in your development process. Each of these steps could easily take an entire week so make sure to pace yourself and set constraints on the time/effort balancing design and development time. We are not expecting polished and pixel-perfect results here, but are looking to see that you can articulate your ideas on paper and in a design program, and extract out general guidelines for your developers (e.g. you) to work from.

### Part 2: Development

As a front end developer, your task is often to create faithful reproductions of the visual design of the web app/site that lands on your desk. Over time you will acquire new tips and tricks on how to make high fidelity recreations of the designs you've made or those that have been given to you. You will even be able to add delightful animations and add surprising effects that will tickle your users. 

For now, your job is to translate your own designs as faithfully as possible into code. In this step, you will identify how to take the specifications in your style guide and design (see part 1) and articulate them as HTML, CSS, and JavaScript. 

Here you will:
1. **Semantic and Structured HTML**: Create an HTML structure that best uses semantic HTML to structure your content
   * HINT: You should read your CSS and JavaScript in as external files.  
2. **Elegant CSS**: Define CSS rules that follow as best as possible BEM conventions that structure your layout and style your DOM elements
  * HINT: Remember the CSS Box model? You'll probably want to use `border-box` box-sizing on all of your elements using the *universal selector* so that your DOM elements are always constrained by the width and height you want. 
  
    ```css
    * {
      box-sizing: border-box;
    }
    ```
3. (UPDATE Feb 03 2020: Note that since we did not cover JavaScript Events in class, this is no longer a strict requirement. However you are welcome to add interactivity with JavaScript events if you'd like) **Interactivity**: Write JavaScript that fulfills the 5 below interactive elements that use the following events. The JavaScript should update the CSS using in response to the following events:
   * `onload`
   * `click`
   * `scroll`
   * `mouseover`
   * `onkeypress`
4. **Responsive page layout**: Your page should show some responsiveness to screen size. You will have to use a `@media` query to affect some layout changes to your page. 
   * HINT: Changing `flex-direction: row` to `flex-direction: column` on a flex container will do wonders here. Furthermore, changing the `font-size` will make a massive difference as well. 

### Part 3: Deployment
Your website will be served using a static web server on **Glitch** and will be pulled from a remote Github repository. You will need to practice good git tracking and connect your local git repository to a remote Github Repository. 

Consider structuring your project directory like so:

```
/myCoolProject
  README.md
  index.html
  /public
    /js
      main.js
    /css
      main.css
```

<!-- You can copy the code from Assignment `01` from last week and put your static HTML, CSS, and JavaScript files into the correct directories. 

**e.g.**:
* `index.html`
* `/views`:
  * `about.html`
* `/public`:
  * `/js`:
    * `main.js`
  * `/css`:
    * `main.css` -->
  
### Part 4: Documentation
* You must have a README.md that explains:
    * how to set up and run your application.
    * how you built your HTML page
    * inspiration, process documentation, struggles, references, and questions, like your ITP blog
    * and how you deployed your work to [Glitch.com](https://glitch.com).
  * You may use this [README template](/templates/readme-template.md) to structure your README documentation and blog post

## Submission

**Details:**
* Due Date: week 3 - Feb 10
* Your assignment must be turned in BEFORE midnight on Sunday, the day before class, Feb 9.

**📨All Assignments should be submitted to your respective section:**
* Section 1:
  * [Joey's Section - Assignment Submission Form](https://forms.gle/GkLsRM581kfyHg6W6)
* Section 2:
  * [Cassie's Section - Assignment Submission Form](https://forms.gle/pzxHjZtq1iP5WAyv9)

