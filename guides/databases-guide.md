# Databases Guide

## About

## Introduction to data persistence


## What is a database?


## Why do we use data

## Databases as software

## Databases as a service


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

Where `document#001` might look something like:

```json
{_id:"a1b2c3d4e5g6", address:"370 jay st., brooklyn", species:"Maple"}
```


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



