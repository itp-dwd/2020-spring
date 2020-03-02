# Week 05: Databases

## SLIDES
* ↳ [Link to Week 5 Slides: Databases](https://docs.google.com/presentation/d/1dY3tUGLn87aO7lqKDjcfaXvsgrOjDIJFya9DzKVPBJs/edit?usp=sharing)

## ABOUT

This week we will learn how to persist data in web applications using a database. We will learn about CRUD conventions for data storage and retrieval.

Emphasis this week will be understand the need for databases, rather than using a JSON data store, CRUD conventions, and connecting user events to API requests to database actions. 

### OUTCOMES & GOALS

In this class we will be:
* Translating UI/UX designs into data models
* Learning the vocabulary of NoSQL databases
* Learning about Rest API/CRUD conventions
* Learning how to set and retrieve data from NeDB

Students will walk away with a deeper understanding of:
* Data Models
* NoSQL Databases
* CRUD
* How web applications consume custom, dynamic data

* **Data Models**
  * What is a data model?
  * How do you translate interface design into a data model?
* **NoSQL Database**
  * What is a document?
  * What is a collection?
  * What is an id/ObjectID?
  * What is a key-value pair?
  * What is a key-array pair?
  * What is a nested document?
  * How do you relate documents to each other?
  * What types of relationships can documents have?
* **Databases + CRUD**
  * How do you map data actions to API endpoints?
  * What are conventions, and what are choices that you, as the developer, need to make?
* **Deployment**
  * How do you use databases in a production web application?
  * What does it mean to responsibly store data?
  * What are ways that you can let users have control over their data?'

<!-- 
- Why do we need databases?
- What are the different types of databases?
- How is the data in databases structured?
- In a document-based NoSQL database, what is a
  - document?
  - id? ObjectID? unique id?
  - schema?
  - collection?
- What does it mean to responsibly store data?
- What are ways that you can let users have control over their data?
 -->

## WHAT WE ARE NOT COVERING
- Advanced databases (indexes, tree structures,join tables, etc.)

## PACING / DURATION
* :30 Homework/Review
* :20 Translating interfaces to JSON
* :30 Using a JSON file data store
* :5 Break
* :60 Using NeDB
* :5 Assignment

## MATERIALS NEEDED

* ↳ please see [MongoDB Guide - Setup](../guides/mongodb-guide.md)


## TOPICS

### Data Persistence
* [Database Guide - Dynamic Data & Data persistence](../guides/databases-guide.md#dynamic-data--data-persistence)

### What are Data?
* [Database Guide - What are data?](../guides/databases-guide.md#what-are-data)

### What is a Database?
* [Database Guide - What is a database?](../guides/databases-guide.md#what-is-a-database)

### Databases are software
* [Database Guide - Why do we use database software?](../guides/databases-guide.md#why-do-we-use-database-software)
  - [Storage](../guides/databases-guide.md#storage)
  - [Indexing](../guides/databases-guide.md#indexing)
  - [Querying](../guides/databases-guide.md#querying)

### Database Services
* [Database Guide - Database services](../guides/databases-guide.md#database-services)

### NoSQL / Non-relational Databases
* [Database Guide - NoSQL Databases](../guides/databases-guide.md#nosql-databases)
  - [NeDB](../guides/databases-guide.md#nedb)
  - [MongoDB](../guides/databases-guide.md#mongodb)


***
***
***

## STUDIO: MongoDB Atlas Setup & Workbook

### MongoDB Atlas Setup

* ↳ [MongoDB Atlas Setup](../guides/database-services-guide.md#mongodb-atlas)

### Workbook
Learn by doing with the [Databases Workbook](https://github.com/itp-dwd/databases-workbook). Here you will encounter a set of guided challenges that will introduce you to the basic building blocks necessary to build a basic web server and API. 

* ↳ [Database Foundations Workbook](https://github.com/itp-dwd/databases-workbook)

***
***
***

## ASSIGNMENT 5: The API of You: Living forever on the web 

* ↳ [Link to Assignment](../assignments/05_assignment.md)

***
***
***


<!--
via:
* https://github.com/ITPNYU/ICM-2019-Code/blob/master/weeks/01_intro.md
* https://github.com/eyebeam/curriculum/blob/master/TEMPLATE.md
-->

<!-- 
### Lecture
* Databases
  * Persisting data with a NoSQL database (as opposed to SQL databases like PostGres or SQLite)
    * NEDB
    * MongoDB
  * CRUD
* Deployment
  * Platform as a service (PaaS), virtual machines, 

### Studio
### Assignment
* Building on your previous assignment, add persistent data using a database.
* (Using templates?)
* Deploy to Heroku
 -->