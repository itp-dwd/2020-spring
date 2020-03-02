# MongoDB Guide

## About

The MongoDB Guide!

## Table of Contents

- [MongoDB Guide](#mongodb-guide)
  - [About](#about)
  - [Table of Contents](#table-of-contents)
  - [Setup: Your database in the cloud](#setup-your-database-in-the-cloud)
  - [Installation: Local installation and setup](#installation-local-installation-and-setup)
    - [MacOS](#macos)
    - [Windows](#windows)
  - [Running MongoDB](#running-mongodb)
    - [Starting](#starting)
    - [Stopping](#stopping)
  - [Interactive Mongo](#interactive-mongo)
    - [MongoDB GUI: Studio3T App](#mongodb-gui-studio3t-app)
    - [MongoDB via Commandline](#mongodb-via-commandline)
  - [MongoDB with Node.js/Express.js](#mongodb-with-nodejsexpressjs)
    - [Simplifying with Mongoose.js, the mongodb adapter](#simplifying-with-mongoosejs-the-mongodb-adapter)
    - [Data Models](#data-models)
    - [Querying](#querying)
    - [Creating](#creating)
    - [Updating](#updating)
    - [Deleting](#deleting)
  - [MongoDB Atlas: Hosting your database on the web](#mongodb-atlas-hosting-your-database-on-the-web)
    - [Project Settings with .env](#project-settings-with-env)
    - [Glitch Settings](#glitch-settings)
  - [Learn By Example](#learn-by-example)


## Setup: Your database in the cloud

For starters we recommend directly starting to use a MongoDB database services like [MongoDB Atlas](https://www.mongodb.com/cloud/atlas). Why? Because this will allow us to quickly start reading and writing data in our web applications without fussing with local installation quirks and hiccups. 

You can follow along the [Database services guide - MongoDB Atlas](./guides/../database-services-guide.md#mongodb-atlas) to set up your database service in the "cloud." 


## Installation: Local installation and setup

### MacOS

* It is recommended to install MongoDB using [Homebrew]() for mac:
  * See installation notes [MongoDB Homebrew Installation for Mac](https://github.com/mongodb/homebrew-brew)

### Windows

* See installation notes [MongoDB Windows Installation](https://docs.mongodb.com/manual/tutorial/install-mongodb-on-windows/)

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

## MongoDB with Node.js/Express.js

### Simplifying with Mongoose.js, the mongodb adapter

### Data Models

### Querying

### Creating

### Updating

### Deleting

## MongoDB Atlas: Hosting your database on the web

### Project Settings with .env

### Glitch Settings


## Learn By Example

* [Express.js & Mongodb example code](https://github.com/joeyklee/sandbox/tree/master/express/express-mongo)
* **advanced**: [Basic Authentication with Express & MongoDB](https://github.com/joeyklee/very-basic-express-auth-example/tree/with-mongodb)
* **advanced**: [The List Project](https://github.com/joeyklee/list-project) & [Fullstack User Authentication Tutorial](https://github.com/joeyklee/fullstack-user-auth)

