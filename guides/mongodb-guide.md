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
    - [Project Settings with .env](#project-settings-with-env)
    - [Glitch Settings](#glitch-settings)
  - [Simplifying with Mongoose.js, the mongodb adapter](#simplifying-with-mongoosejs-the-mongodb-adapter)
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

### Project Settings with .env

### Glitch Settings


## Simplifying with Mongoose.js, the mongodb adapter

## Data Models

## Querying

## Creating

## Updating

## Deleting




## Learn By Example

* [Express.js & Mongodb example code](https://github.com/joeyklee/sandbox/tree/master/express/express-mongo)
* **advanced**: [Basic Authentication with Express & MongoDB](https://github.com/joeyklee/very-basic-express-auth-example/tree/with-mongodb)
* **advanced**: [The List Project](https://github.com/joeyklee/list-project) & [Fullstack User Authentication Tutorial](https://github.com/joeyklee/fullstack-user-auth)

