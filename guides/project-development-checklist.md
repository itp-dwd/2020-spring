# Project Development Checklist

- [Project Development Checklist](#project-development-checklist)
  - [Project Repository](#project-repository)
  - [Git](#git)
  - [Client-side](#client-side)
  - [Server-side](#server-side)
  - [Databases](#databases)
  - [Deployment](#deployment)
- [Snippets](#snippets)
  - [Boilerplate express app scaffold](#boilerplate-express-app-scaffold)
  - [HTML Boilerplate](#html-boilerplate)
  - [CSS Boilerplate](#css-boilerplate)
  - [JavaScript Boilerplate](#javascript-boilerplate)
  - [Add nodemon as a devDependency](#add-nodemon-as-a-devdependency)
  - [Network calls to an api living at the same base url](#network-calls-to-an-api-living-at-the-same-base-url)
  - [Included in .env](#included-in-env)
  - [included in .gitignore](#included-in-gitignore)
  - [initialize git](#initialize-git)
  - [Example package.json](#example-packagejson)

## Project Repository

| ✅ | Feature | Description |
| :------ | :------ | ----------- |
| ☑️ | **README.md** | A markdown file at the root of your directory that includes: 1. How to set up your project - includes installation process, how to run, develop, and deploy your project. 2. Credits and acknowledgements for the project. |
| ☑️ | **CODEOFCONDUCT.md** | a document laying out the rules for engaging in your software project |
| ☑️ | **CONTRIBUTING.md** | a document helping others how to contribute to your project if you are looking for help. You can also say, "Hi, I'm not currently looking for help." |
| ☑️ | **LICENSE** | a software license that is relevant for your project |
| ☑️ | API.md | (if you have an API) that includes your API documentation or use a documentation generator |


## Git

| ✅ | Feature/command | Description |
| :------ | :------ | ----------- |
| ☑️ | `$ git init` | initialize a folder as a git repository by |
| ☑️ | **.gitignore** | add files and folders you want to ignore. See [example of what's included in gitignore](#included-in-gitignore) |
| ☑️ | `$ git add .` | You add all changes since the last commit |
| ☑️ | `$ git commit -m "e.g. added a new navbar"` | commit changes with a message |



## Client-side

| ✅ | Feature/command | Description |
| :------ | :------ | ----------- |
| ☑️ | **HTML** | See [HTML Boilerplate](#html-boilerplate) // Use Semantic HTML - use the tags with the semantic meaning closest to what content it will hold. //  Follow BEM notation for applying classes to **every** DOM element. |
| ☑️ | **CSS** | See [CSS Boilerplate](#css-boilerplate) // Put your CSS in the `<head></head>` tags // Reset your `margins`, `padding`, `box-sizing`, `font-size`, and `font-family`. // Follow BEM notation - every DOM element has a style |
| ☑️ | **Javascript** | See [JS Boilerplate](#javascript-boilerplate) // Put your javascript at the end of your markup just before the last closing `</body>` tag. // A [note on baseURLs for API calls](#network-calls-to-an-api-living-at-the-same-base-url) |



## Server-side

| ✅ | Feature/command | Description |
| :----- | ----- | ----------- |
| ☑️ | `$ npm init` | creates a new node project by generating a **package.json**|
| ☑️ | **package.json** | Always include in [scripts: “start”:”node server.js”](#example-packagejson) // ALWAYS install your dependencies using `npm install packageName` so that they get listed as dependencies in your package.json // add [nodemon as a devDependency](#add-nodemon-as-a-devdependency) |
| ☑️ | .env | Setting your environment variables //anything that you want to keep secret like the URL to your database. // the variables defined in **.env** will show up as `process.env.<the name of your variable>` //  Use all caps to make your variables identifiable. |
| ☑️ | **config.js** | Use `npm install dotenv` to install the node library to read in your .env file // Always read your **.env** variables to a **config.js**. Use **config.js** then in your **server.js** file to make your env variables accessible to your application.  |
| ☑️ | Boilerplate express app| See [here for your boilerplate express app scaffold](#boilerplate-express-app-scaffold) |


## Databases

| ✅ | Feature/command | Description |
| :----- | ----- | ----------- | 
| ☑️ | NeDB | [NeDB Guide](./mongodb-guide.md) |
| ☑️ | MongoDB | [MongoDB Guide](./mongodb-guide.md) |
| ☑️ | Cloud hosted MongoDB | [Database Services Guide](./database-services-guide.md) |


## Deployment

| ✅ | Feature/command | Description |
| :----- | ----- | ----------- | 
| ☑️ | [Glitch](https://glitch.com/) | Web server / API - Platform as a service |
| ☑️ | [Heroku](https://heroku.com) | Web server / API - Platform as a service |
| ☑️ | [MongoDB Atlas](https://www.mongodb.com/cloud/atlas) | database as a service |



***
***
***

# Snippets

## Boilerplate express app scaffold

```
todo-app/
  .env
  .gitignore
  package.json
  index.js
  config.js
  public/
    js/
      main.js
    styles/
      main.css
    assets/
  views/
    index.html
  models/
    todo.js
  node_modules/
```

## HTML Boilerplate

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="utf-8" />
    <meta http-equiv="x-ua-compatible" content="ie=edge" />
    <meta name="viewport" content="width=device-width, initial-scale=1" />

    <title></title>

    <link rel="stylesheet" href="css/main.css" />
    <link rel="icon" href="images/favicon.png" />
  </head>

  <body>
    <script src="js/scripts.js"></script>
  </body>
</html>
```

## CSS Boilerplate
```css
*{margin:0;padding:0;box-sizing:border-box}
html{font-size:16px}
body{font-family:Arial, Helvetica, sans-serif}
a,a:link,a:visited{color:black;text-decoration:none}
```

## JavaScript Boilerplate

```js
window.addEventListener('DOMContentLoaded', async() => {
  // your javascript code will go below here
});
```

## Add nodemon as a devDependency

```sh
$ npm install nodemon -D
```

and add it to your `"scripts"` in **package.json**

```json
"scripts": {
  "start":"node index.js",
  "dev":"nodemon index.js"
}
```

## Network calls to an api living at the same base url

I f you are running a web server to serve your HTML files, remember you don't need to have a localhost reference in your fetch() requests: e.g.

```js
await fetch("http://localhost:3000/api/dogs", ...)
```
can just be:
```js
await fetch("/api/dogs", ...)
```

## Included in .env

```
MONGODB_URI=<your mongodb url>
```

## included in .gitignore

```
node_modules
.env
```

## initialize git

```sh
~ $ cd /Desktop/my-todo-app
(my-todo-app) $ git init
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