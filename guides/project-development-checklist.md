# Project Development Checklist

- [Project Development Checklist](#project-development-checklist)
  - [Project Repository:](#project-repository)
  - [Git](#git)
  - [Client-side](#client-side)
  - [Server-side](#server-side)
  - [Databases](#databases)
  - [Deployment](#deployment)
- [Snippets](#snippets)
  - [Base CSS](#base-css)
  - [Example package.json](#example-packagejson)

## Project Repository:
- **README.md**
  - A markdown file at the root of your directory that includes:
    1. How to set up your project - includes installation process, how to run, develop, and deploy your project. 
    2. Credits and acknowledgements for the project.
- **Important documents**:
  - CODEOFCONDUCT.md - including your code of conduct
  - CONTRIBUTING.md - a document helping others how to contribute to your project if you are looking for help. You can also say, "Hi, I'm not currently looking for help."
  - LICENSE - a software license that is relevant for your project 
  - API.md - (if you have an API) 

## Git

- Use git to track your project as it develops
- initialize a folder as a git repository by:
  ```sh
  ~ $ cd /Desktop/my-todo-app
  (my-todo-app) $ git init
  ```
- You add changes with `git add .` and commit them  by `git commit -m "e.g. added a new navbar"`

## Client-side

- **HTML**
  - Use Semantic HTML - use the tags with the semantic meaning closest to what content it will hold. 
  - Follow BEM notation for applying classes to **every** DOM element.
  - Put your CSS in the `<head></head>` tags and your javascript at the end of your markup just before the last closing `</body>` tag.
- **CSS**
  - [Set your base css styles](#base-css) - reset your `margins`, `padding`, `box-sizing`, `font-size`, and `font-family`.
  - Follow BEM notation - every DOM element has a style
- **Javascript**
  - if you are running a web server to serve your HTML files, remember you don't need to have a localhost reference in your fetch() requests: e.g.
    ```js
    await fetch("http://localhost:3000/api/dogs", ...)
    ```
  can just be:
    ```js
    await fetch("/api/dogs", ...)
    ```


## Server-side
- start with running `npm init` to create a **package.json**
- **package.json**
    - Always include in [scripts: “start”:”node server.js”](#example-packagejson)
    - It is also helpful to include in your scripts: “dev”:”nodemon server.js” - to install nodemon as a devDependency do: “npm install nodemon -D”
    - ALWAYS install your dependencies using `npm install packageName` so that they get listed as dependencies in your package.json 
- Setting your environment variables in **.env**:
    - anything that you want to keep secret like the URL to your database.
    - variables to set in your **.env**:
      ```
      MONGODB_URI=<your mongodb url>
      ```
    - the variables defined in **.env** will show up as `process.env.<the name of your variable>`
    - Use all caps to make your variables identifiable.
- Setting up your **config.js**:
  - Use `npm install dotenv` to install the node library to read in your .env file
  - Always read your **.env** variables to a **config.js**. Use **config.js** then in your **server.js** file to make your env variables accessible to your application.
- Setting your **.gitignore**
    - node_modules
    - **.env**
    - And if you’re using an in memory database like NeDB you can ignore the database file probably as well.
- Always put your app.listen() at the end of your server.js

## Databases


## Deployment
* Web server / API
  * [Glitch]()
  * [Heroku]()
* Database server:
  * [MongoDB Atlas]()


***
***
***

# Snippets

## Base CSS
```css
*{margin:0;padding:0;box-sizing:border-box}
html{font-size:16px}
body{font-family:Arial, Helvetica, sans-serif}
a,a:link,a:visited{color:black;text-decoration:none}
```

## Example package.json
After creating a **package.json** file by running `npm init`, make sure to add a "run" script:

```json
{
  "name": "todo-app",
  "version": "1.0.0",
  "description": "",
  "main": "index.js",
  "scripts": {
    "test": "echo \"Error: no test specified\" && exit 1",
    "start": "node index.js",
  },
  "keywords": [],
  "author": "",
  "license": "ISC",
  "dependencies": {},
  "devDependencies": {}
}
```