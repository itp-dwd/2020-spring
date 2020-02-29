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
$ npm install express dotenv
```

## Installation

```sh
$ npm install nedb
```

## Inserting

## Finding

## Sorting

## Updating

## Removing

