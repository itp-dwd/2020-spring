# NeDB Guide

## About

According to the author of NeDB, NeDB is an:
> Embedded persistent or in memory database for Node.js, nw.js, Electron and browsers, 100% JavaScript, no binary dependency. API is a subset of MongoDB's and it's plenty fast.

This is a guide to using NeDB as your database in your small-scale, full-stack web applications or server-side scripts.

## Why NeDB?

I will start with saying by saying, "I love NeDB." I love it because it provides a very simple means of storing and retrieving data for small projects and prototypes and it can be easily swapped out when the need for a more sophisticated/full-featured database server/service arises.

* Advantages:
  * NeDB is simple to install
  * You can easily look into your "database", edit items, and delete items - your "database" is "just" a human-readable JSON file.
  * The API is very similar to MongoDB and can be easily swapped out.
* Disadvantages:
  * At some point it stops making sense to use NeDB because it cannot scale to tons of data (at that point, it makes sense to use MongoDB)


## NeDB Documentation
For the full list of everything you can do, and all of the things that aren't covered in this guide:
* [NeDB Documentation on Github](https://github.com/louischatriot/nedb)


## Setup

```sh
$ npm init
$ touch .gitignore .env config.js index.js
```

```txt
/my-project
  .env
  .gitignore
  package.json
  config.js
  index.js
  /public
    /js
    /style
  /views
    index.html
```

```sh
$ npm install --save express dotenv
```

## Installation

```sh
$ npm install --save nedb
```

## Connecting
```js
// First import the nedb library
const Datastore = require("nedb");

// Then connect to a file that will store your database
// Note that NeDB will automatically create this file if it doesn't already exist!
const db = new Datastore({filename: "toppings.db", autoload: true});
```

## Inserting
```js
// When inserting data into the database, it must be an Object
// it can't be an Array, or string, or number
const topping = {name: "pepperoni"};

// DB insertion is an asynchronous action, therefore it needs a callback
db.insert(topping, (err, newDoc) => {
  if (err) {
    console.log(err);
  }

  // will look like {"name":"pepperoni","_id":"CtQFQ7jN9XckY8FD"}
  // You'll notice that newDoc has an _id!
  console.log(newDoc);
});

// You can also insert multiple objects at once
const toppings = [{name: "ham", name: "pineapple"}];
db.insert(toppings, (err, newDocs) => {
  if (err) {
    console.log(err);
  }

  // will look like [{"name":"ham","_id":"CtQFQ7jN9XckY8FD"}, {"name":"pineapple","_id":"lfH97yuIBKq8TIRL"}]
  // newDocs is an array here!
  console.log(newDocs);
})
```

## Finding
```js
// pass an empty object to find to return all of the objects
db.find({}, (err, docs) => {
  if (err) {
    console.log(err);
  }
  console.log(docs);
});

// You can also find based on any attributes
// note that they must match exactly
db.find({name: "pepperoni"}, (err, docs) => {
// ...
});

db.find({_id: "CtQFQ7jN9XckY8FD"}, (err, docs) => {
// ...
});

// There's also findOne to find only one document
db.findOne({name: "pepperoni"}, (err, doc) => {
// ...
});
```

## Operators
```js
// TODO add operators
```

## Sorting
```js
// syntax is the attribute to sort on then
// 1 is ascending order, -1 is descending order
// you need to add exec to get a callback when the operation is done
db.find({}).sort({ name: 1 }).exec((err, docs) => {
  // ...  
});
```

## Updating
When updating a document, there are different ways to specify *how* you update the document:

1. Replace **all attributes** of the document
```js
// The syntax for updating is 
// (1) Find the documents you want to update
// (2) Specify the new attributes
// (3) Options
// (4) Callback when this operation is done
const options = {
  returnUpdatedDocs: true, //defaults to false, tells NeDB to return updated docs
  multi: false, // defaults to false, tells NeDB that this operation can affect multiple documents
  upsert: false // defaults to false, if true, NeDB will insert a new document if your find returns no documents
};

db.update({ name: "sausage" }, { name: "Italian sausage" }, options, (err, numAffected, affectedDocuments) => {
  // ...
});
```

2. Replace **specified attributes** of the document, using `$set`
```js
// The syntax for updating is 
// (1) Find the documents you want to update
// (2) Specify the new attributes
// (3) Options
// (4) Callback when this operation is done
const options = {
  returnUpdatedDocs: true, //defaults to false, tells NeDB to return updated docs
  multi: false, // defaults to false, tells NeDB that this operation can affect multiple documents
  upsert: false // defaults to false, if true, NeDB will insert a new document if your find returns no documents
};

db.update({ name: "sausage" }, {$set: { name: "Italian sausage" } }, options, (err, numAffected, affectedDocuments) => {
  // ...
});
```

## Removing
```js
// The syntax for removing is 
// (1) find the document(s) you want to remove
// (2) Options
// (3) Callback when this operation is done
const options = {
  multi: false // defaults to false, tells NeDB that this operation can affect multiple documents
};

db.remove({ name: "pepperoni" }, options, (err, numRemoved) => {
  // ...
});
```

## Learn by Example

* [Data Selfie App with NeDB](https://github.com/joeyklee/data-selfie-app)
* [The Weather Here App with NeDB](https://github.com/joeyklee/the-weather-here)
* [CRUD API - P5, Express, NeDB](https://github.com/joeyklee/simple-express-api)
* [Data & APIs, Coding Train](https://github.com/CodingTrain/Intro-to-Data-APIs-JS)
* **advanced**: [Basic Authentication with Express & NeDB](https://github.com/joeyklee/very-basic-express-auth-example/tree/with-nedb)


