# Databases Guide

## About

This is the databases guide. Here we briefly introduce that you might need to know about databases before starting to use them in your projects. 

## Table of Contents

- [Databases Guide](#databases-guide)
  - [About](#about)
  - [Table of Contents](#table-of-contents)
  - [Dynamic Data & Data persistence](#dynamic-data--data-persistence)
  - [What are data?](#what-are-data)
  - [What is a database?](#what-is-a-database)
  - [Why do we use database software?](#why-do-we-use-database-software)
    - [Storage](#storage)
    - [Indexing](#indexing)
    - [Querying](#querying)
    - [Data Models](#data-models)
  - [Database services](#database-services)
  - [NoSQL Databases](#nosql-databases)
    - [NeDB](#nedb)
    - [MongoDB](#mongodb)
    - [Others](#others)
  - [SQL Databases](#sql-databases)

## Dynamic Data & Data persistence

If you've been coding in JavaScript and you even gone through the [Backend Foundations Guide](./backend-foundations-guide.md) you will have had your first taste of what it means to dynamically update data living on a server. This is hugely important because it is, theoretically, the first time you will have be able to **persist** the changes to your data on your web projects. This means that any interactions you've had with your data while using your web application could be stored and reflected back not only to you but to others who would also access that same data by going to your website.  

This concept of having a place on the web where your data is living and having the means to access, create, update, and delete data dynamically by creating and API is central to our discussion of databases. 

## What are data?

What are data? Data (the plural of datum) can be anything - images, text, sound, paintings, lists, you name it. They are records or signals of phenomenon that can be used to produce "information" which can help to explain or describe a subject or phenomenon of interest.

Without launching into a while philosophical discussions (albeit an important one) about data, knowledge, and ontologies and epistomology, what is important for us is that in the context of web development, data most commonly will take the form of...
* text
* images
* video
* sound

... and these data will be organized into lists (e.g. arrays) or JSON objects in some way, shape, and form. 

These data will be stored in either, **in memory**, in a ["flat file"](https://www.techopedia.com/definition/25956/flat-file), or as some kind of [binary file](https://www.techopedia.com/definition/937/binary-file) in a[database software](https://www.techopedia.com/definition/1185/database-db).

These data, regardless if they are in the form of a flat file or being retrieved dynamically from a database software, will live somewhere on some kind of server infrastructure so that they can be used in some way -- e.g. read, create, updated, deleted -- by super cool/interesting/meaningful applications like the ones you're building in this class.

This raises the question, what exactly is a database? Read on to learn more.

See: [How do you say, "data", The Guardian](https://www.theguardian.com/news/datablog/2010/jul/16/data-plural-singular)

## What is a database?

On a super general level, a database is considered anything that helps to *store* and *organize* data. 
Let's take for example a library like the Brooklyn Public Library. The Brooklyn Public Library can be considered a kind of database; the books are the data, the library itself organizes them and makes it easy to find books. The key words here are "organize" and "easy to find." While it is one thing to collect data and store them, the key to a database's function is the part about organizing and **indexing** data such that things are easier to find.

Moving away from the library analogy, databases are "just" software. For example, I have a folder on my computer called "screenshots." My screenshots folder might be considered my database of screenshots that I've taken. On any modern computer, folders are generally outfitted with some additional functionality like the ability to sort, organize, and arrange the items within them. Because of my computer's indexing system, I can search for filenames within the folder (e.g. "cat gifs") and get a filtered selection of items who's name or metadata might contain those keywords. In this case, my computer and the "folder" itself is the software that acts like my database for my screenshots (the data). 

So if databases are *just* software, what does this mean for us in web development and programming more generally? Well, this means that your database can be as simple, for example, as a `JSON` file called `myFavoriteRestaurants.json` that contains a list of your favorite restaurants, where each entry contains the name, address, and the time you last visited. Anytime that you decide you want to go to dinner, you can check your `myFavoriteRestaurants.json` file and **query** for key words like "Brooklyn" or "Manhattan" to help narrow **search**. You can **add** new entries to your `myFavoriteRestaurants.json` when you go somewhere new, **update** existing entries when you visit them, and **delete** the restaurants who've become too hipster or expensive for your liking. Starting to see my point? Along with organizing your data, a database provides functionality for **searching**, **retrieving**, **adding**, **deleting**, and **updating** data that are part of the database. For the case of this `myFavoriteRestaurants.json` it is likely this list is relatively small so you can easily work with it *in-memory* in a text editor using JavaScript code in the Browser or in Node.js. But what if you have millions of favorite restaurants, or hundreds of millions? What if your list was so long that there'd be no way for you to even store that file on your machine? What would you do then?

This is where more robust database software comes in handy. We will eventually talk about [MongoDB]() as our main "production grade" database for our web applications (e.g. allows us to handle massive amounts of data), but first, we will briefly discuss what are common features of database software that make them important for us.

## Why do we use database software?

As mentioned above, we can run into limits of handling and storing data as flat files and *in-memory*. This is where database softwares come into handy. There are tons of different database softwares (now just referred to as "databases") out there. Each has its use cases and is optimized for different tasks (e.g. real-time vs. big data analysis vs. X, Y, Z). In general however, most/all databases have the following in common:
* storage
* indexing
* querying

### Storage

Storage is obviously first and foremost the most important thing, however not all databases store data the same way. You can count on databases storing data in some way, shape, or form. The way that data are stored will depend on the database itself. 

### Indexing

The secret sauce of databases is in the way that they are able to **index** data. A [database index](https://en.wikipedia.org/wiki/Database_index), "is a data structure that improves the speed of data retrieval operations on a database table at the cost of additional writes and storage space to maintain the index data structure. Indexes are used to quickly locate data without having to search every row in a database table every time a database table is accessed." (Wikipedia). When we say, "a databases ability to index data" we are referring to specific functionalities (e.g. functions written by programers) in the database itself that keep track of data in an efficient way. There are very impressive indexing algorithms out there and if you study computer science or engineering of some kind you quite likely will have encountered these in your studies. Lucky for us, a lot of other people have thought a lot about this and have come up with solutions so we can focus on other things (e.g. like building cool projects).

Indexes can be made on properties like text - e.g. user names - or even spatial properties like coordinates. 

### Querying

Databases can be queried in ways that allow for data retrieval based on specific properties. As we've established, databases are software and each software is written differently (some more drastically different than others). In any case, how you **query** a database will depend the database's API and the underlying philosophy or purpose of that database. 

You can say there are two different types of database types that are differentiated based on how we can query for data in those databases. There are:
* [SQL Databases](https://en.wikipedia.org/wiki/SQL) - Structured Query Language (SQL) databases
* VS.
* [NoSQL Databases](https://en.wikipedia.org/wiki/NoSQL) - No-Structured Query Language (SQL) or non-relational databases

Our focus in this class is NoSQL databases for the reason that they are generally well structured for web application use cases. 

### Data Models

Databases generally rely on having [structured data models](https://en.wikipedia.org/wiki/Data_model) to create predictability and standardization for the data that will live inside of them. You can think of it this way: data models allow you to define what goes in and what comes out. 

As an example, a data model or a data **schema** might look something like this:

```js
{
  "latitude": Number,
  "longitude": Number,
  "address": String,
  "name": String
}
```

By defining what *kinds* of data you expect to be associated with a given property in your database, you help to ensure that your data inputs and outputs are all the same **type**. Data models also allow your databases to do intelligent indexing like we discussed above. 


## Database services

So if databases are just software that store our data and make it easy to use, then how do we use these databases?

1. First things first: installation. Like any software, you'll have to install these database softwares onto your computer. Every time you want to use a different type of database, then you'll need to install it.
2. Second: starting & stopping. Again, like any software, you'll need to start your database before you can use any of the data you've added to it. Similarly, you can to stop your database if you're not using it. 
3. Third: interact with the database. Once again, like any software, you'll need to interact with the database for anything to happen. Often this will either occur using some kind of GUI, a command-line interface, OR via an API that you've built to interface with the database.

This third step warrants some additional explanation. We want to interface with our database. We can create our own APIs that interface with the database or we can use some kind of GUI or commandline interface. Regardless of how we want to interface with the database (hey that rhymes!), the way this happens is through connecting to the database through a unique URL where our database is *listening* for connections by other software. Yes, that's right, when we use a database, we are *connecting to it*. Hmmm doesn't that sound similar to how we can can *connect* our web client-side and server-side applications? If you think so, then you're correct! 

When you start a database on your local machine, your database is being *hosted* by your local machine. Similarly, if you start a database that you want people to be able to access from the web, an internet connected machine will **host** your database such that other web services can **connect** to it (provided they have the right credentials and are authorized to do so).

This last part is important: If you want to be able to get your data on the web, you will need to find somewhere to **host** your database. Lucky for us, there are many database hosting services - a.k.a databases as a service providers - that make it possible to host these complex database softwares on the web. 

You will find more details in the [Database services guide](./database-services-guide.md) for details on different database services for your projects. 

## NoSQL Databases

There are many types of databases out there. Each has its own unique qualities and uses.

The database type we are going to use in this class are called [NoSQL databases](https://en.wikipedia.org/wiki/NoSQL). NoSQL databases or non-relational databases are databases that organize data in structures (objects) that are not tabular. We use these types of databases in this course because they are a bit simpler to understand if you've been coding JavaScript (which you have!) and using JSON objects. NoSQL databases like [MongoDB]() organize data as **collections** of **documents** that contain **key/value** pairs. 

An example of NoSQL database that uses document storage (e.g. MongoDB) might look something like this:

```txt
Joey's Tree Database
+----------------------------------------+
| New York                               |
| +------------------------------------+ |  
| | document#001                       | |
| | document#002                       | |
| | document#003                       | |
| |                                    | |
| |                                    | |
| +------------------------------------+ |
|                                        |
+----------------------------------------|
```

Where `New York` is the collection and `document#001` might look something like:

```json
{_id:"a1b2c3d4e5g6", address:"370 jay st., brooklyn", species:"Maple"}
```

A query to such a NoSQL database might look something like this:

```shell
> db.getCollection('newyork').find({})
```

Looks familiar right? Kinda like JavaScript syntax, no? Since we're working with documents and keys/values, it would make sense that our syntax would reflect the kind of JavaScript-y object world we're used to.

We are going to introduce 2 types of non-relational databases for this class:
* [NeDB](https://github.com/louischatriot/nedb/) - this is a lightweight, simple flat file, JavaScript-based non-relational "database" which is great for learning, prototyping, and testing.
* [MongoDB](https://www.mongodb.com/) - this is a solid choice for a document-style NoSQL database for projects of any size. 

### NeDB

* [NeDB Guide](./nedb-guide.md)

### MongoDB

* [MongoDB Guide](./mongodb-guide.md)

### Others

There tons of other NoSQL databases. It is worth checking out:
* [PouchDB](https://pouchdb.com/)
* [RethinkDB](https://rethinkdb.com/docs/guide/javascript/)

And lots of others [Awesome-database](https://github.com/agarcialeon/awesome-database#document-store-)

## SQL Databases

There are many types of databases out there. Each has its own unique qualities and uses. SQL Databases are databases that organize data in a tabular fashion. 

Some common SQL databases you will encounter in your lifetimes include:
* [PostGreSQL](https://www.postgresql.org/)
* [MySQL](https://www.mysql.com/)
* [SQLite](https://sqlite.org/index.html)
* [MariaDB](https://mariadb.com/)
* [MSSQL]()

An example of SQL database that uses tabular storage (e.g. PostGreSQL) might look something like this:

```txt
Joey's Tree Database
+----------------------------------------+
| New York                               |
| +------------------------------------+ |  
| | item#001                           | |
| | item#002                           | |
| | item#003                           | |
| |                                    | |
| |                                    | |
| +------------------------------------+ |
|                                        |
+----------------------------------------|
```

Where `New York` would be a table and the `items` in that table would be organized as:

```json
_id,address,species
"a1b2c3d4e5g6", "370 jay st., brooklyn", "Maple"
"12qdc3423d23", "371 jay st., brooklyn", "Pine"
"236yrgw34435", "372 jay st., brooklyn", "Ginko"
```

A query to such a NoSQL database might look something like this:

```shell
> USE 'joeys-tree-database' SELECT * FROM 'newyork' ORDER BY 'address'
```

