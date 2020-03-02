# MongoDB Guide

## About

The MongoDB Guide!

## Table of Contents

- [MongoDB Guide](#mongodb-guide)
  - [About](#about)
  - [Table of Contents](#table-of-contents)
  - [Getting Started](#getting-started)
    - [Option 1: Database in the cloud](#option-1-database-in-the-cloud)
    - [Option 2: Database local installation](#option-2-database-local-installation)
      - [MacOS](#macos)
      - [Windows](#windows)
- [MongoDB: Local Development](#mongodb-local-development)
  - [Running MongoDB](#running-mongodb)
    - [Starting](#starting)
    - [Stopping](#stopping)
  - [Interactive Mongo](#interactive-mongo)
    - [MongoDB GUI: Studio3T App](#mongodb-gui-studio3t-app)
    - [MongoDB via Commandline](#mongodb-via-commandline)
- [MongoDB with Node.js/Express.js](#mongodb-with-nodejsexpressjs)
  - [MongoDB Atlas: Hosting your database on the web](#mongodb-atlas-hosting-your-database-on-the-web)
    - [Todo App: Project scaffold](#todo-app-project-scaffold)
    - [Setup](#setup)
      - [Scaffold the app](#scaffold-the-app)
      - [Install your dependencies](#install-your-dependencies)
      - [Define your environment variables and configuration](#define-your-environment-variables-and-configuration)
        - [.gitignore](#gitignore)
        - [config.js](#configjs)
        - [.env](#env)
        - [package.json](#packagejson)
    - [Add boilerplate html to **views/index.html**](#add-boilerplate-html-to-viewsindexhtml)
    - [Add your "hello world" Express App](#add-your-%22hello-world%22-express-app)
    - [Defining API Endpoints](#defining-api-endpoints)
  - [Data Models](#data-models)
  - [Querying](#querying)
  - [Creating](#creating)
  - [Updating](#updating)
  - [Deleting](#deleting)
  - [Learn By Example](#learn-by-example)


## Getting Started

### Option 1: Database in the cloud

For starters we recommend directly starting to use a MongoDB database services like [MongoDB Atlas](https://www.mongodb.com/cloud/atlas). Why? Because this will allow us to quickly start reading and writing data in our web applications without fussing with local installation quirks and hiccups. 

You can follow along the [Database services guide - MongoDB Atlas](./guides/../database-services-guide.md#mongodb-atlas) to set up your database service in the "cloud." 


### Option 2: Database local installation

Typically as a developer, you'll develop locally and then push to the "cloud." This is the case for everything - your client side code, your server-side code, and your database server. As this is the case, setting up your local development environment includes installing your database locally. 

It should be noted that these installations can sometimes be fussy, so that's why we recommend [Option 1](#option-1-database-in-the-cloud) above to minimize lost time. If you want to get setup, however, you can follow the installation notes provided below.

#### MacOS

* It is recommended to install MongoDB using [Homebrew for mac](https://brew.sh/):
  * [Installation Guide](https://joeyklee.github.io/fullstack-user-auth/#/tutorial/01_installation)
  * Additional installation notes from MongoDB are supplied here: [MongoDB Homebrew Installation for Mac](https://github.com/mongodb/homebrew-brew)

#### Windows

* See installation notes [MongoDB Windows Installation](https://docs.mongodb.com/manual/tutorial/install-mongodb-on-windows/)

***
***
***

# MongoDB: Local Development

All of the notes below are relevant for working with a local installation of MongoDB.

## Running MongoDB

### Starting

In your terminal:
```sh
$ mongod
```

### Stopping

In your terminal where mongo is running, press: `control` + `c`

## Interactive Mongo

### MongoDB GUI: Studio3T App

You can download and install the [Studio 3T](https://studio3t.com/download/) App to view your MongoDB database, the collections, and documents through a GUI.

* [Studio 3T](https://studio3t.com/download/)

1. First, make sure you're running mongo:
   ```sh
   $ mongod
   ```
2. Then open up Studio3T
3. If it is your first time, you'll need to **create** a new connection, where:
   * name: `mongodb`
   * address:`localhost:27017`


### MongoDB via Commandline

1. First, make sure you're running mongo:
   ```sh
   $ mongod
   ```
2. Then open up your commandline, then start the mongo shell:
  ```sh
  $ mongo
  >
  ```
3. You can see the commands here at [Working with the mongo shell](https://docs.mongodb.com/manual/mongo/#working-with-the-mongo-shell):
   * To see which database you're currently using
   ```sh
   > db
   ```
   * To switch to a database
   ```sh
   > use treeDatabase
   ```
   * To insert a document to a collection
   ```sh
   > use treeDatabase
   > db.newyork.insertOne( { address: "370 Jay St., Brooklyn, NY"} );
   ```

***
***
***

# MongoDB with Node.js/Express.js

In this class, we will be interfacing with MongoDB databases. Essentially our task as developers is to connect the dots between our client side interfaces and the data living in our our databases through the APIs we design and build.

As you have seen in the [NeDB guide](./nedb-guide.md), you can create Express APIs that allow you to interface with different databases. Depending on the database that you connect to, the syntax and structure will change, sometimes slightly, other times more dramatically. 

When interfacing with MongoDB, we will be writing our server-side code to:
1. Connect with a MongoDB server hosted either locally or remotely.
2. CREATE, READ, UPDATE, and DELETE data stored in the MongoDB database that is being hosted locally or remotely.

For this guide, we assume that you will be connecting to a remote MongoDB instance hosted by MongoDB Atlas.

## MongoDB Atlas: Hosting your database on the web

Before continuing please be sure to set up MongoDB Atlas as detailed in the [Database services guide - MongoDB Atlas](./guides/../database-services-guide.md#mongodb-atlas).

### Todo App: Project scaffold

Scaffold your project like so
```txt
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

**Where**:
* **.env**: *file*
  * The `.env` file defines variables that will be picked up by your `process.env` variable. The variables you define here are generally things you want to **keep private** from the public. This includes the url to your **MongoDB atlas** server url.
* **.gitignore**: *file*
  * includes files and folders you want to ignore
  ```
  # ignore all those dependencies
  node_modules
  # ignore weird mac files
  .DS_Store
  $ ignore the .env file with your secret info
  .env
  ```
* **package.json**: *file*
  * generated using: `npm init`
* **index.js**: *file*
  * where your server code will live
* **config.js**: *file*
  * This is where you will store your configuration variables from your 
* **public/**: *directory*
  * includes public assets like your client facing javascript and css styles and images
* **models/**: *directory*
  * the directory where your database schema will live.
  * **models/todo.js**: *file*
    * we will write some javascript here that defines our database model for our todo data
* **views/**: *directory*
  * includes any index.html views that you will send to the client

### Setup

#### Scaffold the app

Scaffold the app by adding the following
```sh
~ $ cd Desktop
(desktop) $ mkdir todo-app
(desktop) $ cd todo-app
(todo-app) $ npm init
(todo-app) $ touch .env .gitignore index.js config.js
(todo-app) $ mkdir public public/js public/styles public/assets models views
(todo-app) $ touch views/index.html models/todo.js public/js/main.js public/styles/main.css
```

#### Install your dependencies

In your terminal:
```sh
$ npm install express morgan mongoose dotenv
$ npm install nodemon -D
```

#### Define your environment variables and configuration

##### .gitignore
* Set which things you want to ignore in `.gitignore`:
  ```txt
  # ignore all those dependencies
  node_modules
  # ignore weird mac files
  .DS_Store
  $ ignore the .env file with your secret info
  .env
  ```

##### config.js
* define your `config.js`. Here we define 2 **key/value** pairs, one for `PORT` and the other for `MONGODB_URI`:
  ```js
  require('dotenv').config();
  module.exports = {
    PORT: process.env.PORT || 3000,
    MONGODB_URI: process.env.MONGODB_URI || 'mongodb://localhost:27017/todo-app'
  }
  ```
  * we use the `require('dotenv').config()` to pull any environment variables defined in our `.env` file.
  
##### .env
* add your MongoDB Atlas URL to the `.env` file:
  ```
  MONGODB_URI='mongodb+srv://<yourUserName>:<yourPassword>@dwd-projects-ksn8b.gcp.mongodb.net/<yourCollectionName>?retryWrites=true&w=majority'
  ```
  * the `MONGODB_URI=` to the URL defined in:
    ![The URL that you'll need to pick up](../assets/mongodb-atlas/mongodb-atlas-12.png) 

##### package.json
* add your `start` and `dev` scripts to the `package.json`:
  ```json
  {
    "name": "todo-app",
    "version": "1.0.0",
    "description": "",
    "main": "index.js",
    "scripts": {
      "test": "echo \"Error: no test specified\" && exit 1",
      "start": "node index.js", 
      "dev": "nodemon index.js"
    },
    "keywords": [],
    "author": "",
    "license": "ISC",
    "dependencies": {
      "dotenv": "^8.2.0",
      "express": "^4.17.1",
      "mongoose": "^5.9.2",
      "morgan": "^1.9.1"
    },
    "devDependencies": {
      "nodemon": "^2.0.2"
    }
  }
  ```  
  * Notice under `"scripts"`:
    ```json
    "scripts": {
      "test": "echo \"Error: no test specified\" && exit 1",
      "start": "node index.js", 
      "dev": "nodemon index.js"
    },
    ```

### Add boilerplate html to **views/index.html**

```html
<!DOCTYPE html>
  <head>
    <meta charset="utf-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <title></title>
    <meta name="description" content="">
    <meta name="viewport" content="width=device-width, initial-scale=1">
    <link rel="stylesheet" href="./styles/main.js">
  </head>
  <body>
    <h1>hello world</h1>
    <script src="./js/main.js"></script>
  </body>
</html>
```

### Add your "hello world" Express App

In your **index.js**:
```js
const fs = require('fs');
const path = require('path');
const express = require('express');
const bodyParser = require('body-parser');
const app = express();
const config = require('./config');

const PORT = config.PORT;

// Handle data in a nice way
app.use(bodyParser.urlencoded({extended: true}));
app.use(bodyParser.json());
const publicURL = path.resolve(`${__dirname}/public`);

// Set your static server
app.use(express.static(publicURL));

// Set your static html file
app.get("/", (req, res) => {
  res.sendFile( path.resolve(__dirname + "/views/index.html"))
});

// ---- ADD YOUR API ENDPOINTS HERE ----

// Start listening
app.listen(PORT, () => {
  console.log(`see the magic: http://localhost:${PORT}`);
})
```

Now run:

```sh
(todo-app) $ npm run dev
```

You should see:

![Hello world site served](../assets/mongodb-guide-01.png);


### Defining API Endpoints

We are going to create a CRUD style API with the following endpoints:
* `/api/v1/todos`
  * GET
  * POST
* `/api/v1/todos:id`
  * PUT
  * DELETE
  
Before we add our MongoDB into the mix, let's define our API endpoints in `index.js`. Where you see the comment `// ---- ADD YOUR API ENDPOINTS HERE ----`, add the following:

```js
// ---- ADD YOUR API ENDPOINTS HERE ----
// GET: "api/v1/todos"
app.get("/api/v1/todos", async (req, res) => {
  try{
    res.json({})
  } catch(error){
    console.error(error);
    res.error(error);
  }
});

// POST: "api/v1/todos"
app.post("/api/v1/todos", async (req, res) => {
  try{
    res.json({})
  } catch(error){
    console.error(error);
    res.error(error);
  }
});

// PUT: "api/v1/todos:id"
app.put("/api/v1/todos:id", async (req, res) => {
  try{
    res.json({})
  } catch(error){
    console.error(error);
    res.error(error);
  }
});

// DELETE: "api/v1/todos:id"
app.delete("/api/v1/todos:id", async (req, res) => {
  try{
    res.json({})
  } catch(error){
    console.error(error);
    res.error(error);
  }
});
```

Now if you navigate to: `http://localhost:3000/api/v1/todos`, a `GET` request will be triggered and you should see an empty JSON file is returned:

```json
{}
```

![Empty json is returned](../assets/mongodb-guide-02.png)

Hooray! If this is working, then your API is working! The next steps are to:
* connect to mongodb
* define a data model
* start defining the API routes

## Data Models

## Querying

## Creating

## Updating

## Deleting




## Learn By Example

* [Express.js & Mongodb example code](https://github.com/joeyklee/sandbox/tree/master/express/express-mongo)
* **advanced**: [Basic Authentication with Express & MongoDB](https://github.com/joeyklee/very-basic-express-auth-example/tree/with-mongodb)
* **advanced**: [The List Project](https://github.com/joeyklee/list-project) & [Fullstack User Authentication Tutorial](https://github.com/joeyklee/fullstack-user-auth)

