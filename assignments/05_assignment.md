# Assignment 5: The API of You: Living forever on the web

## Briefing

This week your assignment is to persist data in your Node.js/Express.js API with a database. You will write server-side JavaScript to do CRUD operations on a database, controlled by an API. Then, client-side JavaScript triggered by user actions will make API requests and read/write to the database.

## Readings
* [Databases Guide](../guides/databases-guide.md)
* [NeDB Guide](../guides/nedb-guide.md)
* [Database Services Guide](../guides/database-services-guide.md)
* [MongoDB Guide](../guides/mongodb-guide.md)

## Additional References
* TODO, find some

## Requirements

### Part 1: Final Project Proposal
* The final project presentation will be on March 23. You will need to build a full stack web application, with a database, API, a dynamic front end, and a design.
* You can build on a previous week's project! No need to do everything from scratch.
* You will do a **6 minute** presentation, with time for feedback and questions.
* There will be *guest critics*!
* Cassie and Joey will give you feedback on your proposal

### Part 2: Design and Interface
* Before figuring out what your API and database look like, it's helpful to start from what you want your website to be capable of. What's the point of working on an endpoint that a user will never interact with?
* Make some sketches, wireframes, visual designs, and/or a style guide. 
* Make a list of requirements.
* After making a list of requirements, try to make a plan for how you will accomplish this with code. This will include things like
  * Data Model
  * API endpoints
  * User events
  * JS/HTML/CSS Pseudocode

### Part 3: Development
* **Database**:
  * You must have an NeDB or MongoDB database
  * Your data model must be documented
* **Server-Side**:
  * You will use `npm` to manage your dependencies
  * You will use `express` to create your api
  * Your endpoints will be documented
* **Client-side**:
  * You will use the `fetch()` API to make requests to your API

### Part 4: Deployment
* Your code should be pushed to Github
* Your website should be deployed to **Glitch**, putting from a remote GitHub repository
* Your `package.json` should have all of the necessary components in order for you application to run. Make sure you have a `start` script (`"start": "node server.js"`)
* You database should be deployed to:
  * If you are using NeDB, your database will be deployed to Glitch
  * If you are using Mongo, your database will be deployed to MongoDB Atlas
* If necessary, you have a `.env` in your Glitch project which contains your Mongo connection string 

### Part 5: README Documentation
* You must have a `README.md` that explains:
    * how to set up and run your application.
    * how you built your HTML page
    * inspiration, process documentation, struggles, references, and questions, like your ITP blog
    * and how you deployed your work to [Glitch.com](https://glitch.com).
  * You may use this [README template](/templates/readme-template.md) to structure your README documentation and blog post

## Submission

**Details:**
* Due Date: Week 6 - March 9
* Your assignment must be turned in BEFORE midnight on Sunday, the day before class, March 9.

**📨All Assignments should be submitted to your respective section:**
* Section 1:
  * [Joey's Section - Assignment Submission Form](https://forms.gle/GkLsRM581kfyHg6W6)
* Section 2:
  * [Cassie's Section - Assignment Submission Form](https://forms.gle/pzxHjZtq1iP5WAyv9)