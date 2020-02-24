# Assignment 4: API Love You - Oh CRUD

## Briefing

This week your assignment is to **leap into the world of server-side programming** with Node.js/Express.js. In this project, you will write server-side JavaScript to **create an API** that accepts AJAX request coming from a client-side web application (that you've built) to **create**, **read**, **update**, and **delete** data that are living on your server. 

## Readings

* [What is Node.js](https://www.youtube.com/watch?v=RF5_MPSNAtU&t=5s)
* [Building and API in Node.js Series - Coding Train](https://www.youtube.com/watch?v=P-Upi9TMrBk&list=PLRqwX-V7Uu6Yyn-fBtGHfN0_xCtBwUkBp)

## Additional References
* [Data & APIs Coding Train Series by @shiffman](https://www.youtube.com/playlist?list=PLRqwX-V7Uu6YxDKpFzf_2D84p0cyk4T7X)
* [Simple Express API Tutorial by @joeyklee](https://github.com/joeyklee/simple-express-api)

## Requirements

### Part 1: Designing your API
* Similar to the previous weeks' assignments, you will start by designing your API on paper. You will be required to conceptually diagram how your requests and data will flow between your client and server. 

### Part 2: Development
* **Server Side**:
  * You will need to use `npm init` to create your Node project
  * You will add dependencies using `npm install`
  * Your server-side code will use Express.js to define meaningful API routes that allow you to CREATE, READ, UPDATE, and DELETE data on the server using http requests. You will use:
    * GET: `app.get()`
    * POST: `app.post()`
    * PUT: `app.put()`
    * DELETE: `app.delete()`
  * You will create multiple endpoints that do at least one of the following:
    * Access an API that can't be used client-side, due to CORS or Authentication reasons
    * You will read and write to a JSON file data store
  * Your client side code will be served through your web server by:
    * 1. creating a static file server middleware
    * 2. setting the default API route of your server to send the `index.html` file in your static file directory.
  * You will add the keyword `start` followed by the command to run your server.js file to the "script" property of your `package.json` so you can start your server by running `npm start` (otherwise it won't work with Glitch!). In `package.json`:
  ```json
  "scripts": {
    "test": "echo \"Error: no test specified\" && exit 1",
    "start": "node server.js"
  },
  ```
* **Client Side**:
  * You will use the `async/await` and the `fetch()` function to make network requests that allow your client to communicate with your server's API.
  * The data from the API will be transformed dynamically, using JS, into HTML
  * The focus this week is on creating an API and connected it to the browser, so the design and layout can be simple.
  * Your client side code (HTML, CSS, JavaScript) will be served through your `express` web server.
  * This static server will also serve any necessary CSS and image/video/etc. files

This is how your code should be structured:
```
package.json
package-lock.json
.gitignore
index.js
db/
  data.json
server/
  other-server-side-js-file.js
public/
  js/
    main.js
  css/
    main.css
  assets/
```


### Part 3: Deployment
Your website will be served using **Glitch** and will be pulled from a remote Github repository. You will need to practice good git tracking and connect your local git repository to a remote Github Repository. 

### Part 4: API Documentation
* You must have a file in your repository called `API.md` that contains a list of all endpoints, with the following information:
  * The route, i.e. `/toppings`
  * The HTTP verb, i.e. `GET`
  * Query string parameters, i.e. `q=pepperoni`
  * Any URL parameters, i.e. `/toppings/:name`
  * Request body format, i.e.
  ```json
  {
    topping: "pepperoni"
  }
  ```
  * Response format, i.e.
  ```json
  { 
    description: "A list of pizza toppings.",
    pizzaToppings: [
      "pepperoni",
      "ham",
      "pineapple",
      ...
    ]
  }
  ```
  
### Part 5: README Documentation
* You must have a `README.md` that explains:
    * how to set up and run your application.
    * how you built your HTML page
    * inspiration, process documentation, struggles, references, and questions, like your ITP blog
    * and how you deployed your work to [Glitch.com](https://glitch.com).
  * You may use this [README template](/templates/readme-template.md) to structure your README documentation and blog post

## Submission

**Details:**
* Due Date: Week 5 - March 2
* Your assignment must be turned in BEFORE midnight on Sunday, the day before class, March 2.

**📨All Assignments should be submitted to your respective section:**
* Section 1:
  * [Joey's Section - Assignment Submission Form](https://forms.gle/GkLsRM581kfyHg6W6)
* Section 2:
  * [Cassie's Section - Assignment Submission Form](https://forms.gle/pzxHjZtq1iP5WAyv9)