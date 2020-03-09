# Express Basic Auth Guide

- [Express Basic Auth Guide](#express-basic-auth-guide)
  - [About](#about)
  - [So you want users?](#so-you-want-users)
  - [Express basic Auth: A minimal (temporary) solution](#express-basic-auth-a-minimal-temporary-solution)
    - [Setup](#setup)
  - [Multiple users?](#multiple-users)
    - [List of users](#list-of-users)
  - [Further exploration](#further-exploration)
  - [References](#references)

## About

This is an example of setting up a basic "challenge auth" with `express-basic-auth` package. This will add a "really thin" layer authentication and authorization layer around your web application which requires users to "log in" before using your application or specific routes on your API.

Note: this is by no means a replacement for handling authentication and authorization on a more robust level with things like password hashing, JWT tokens, etc. 

## So you want users?

So let's say that you work at the MTA and you're building a new application that helps commuters to better access the real-time transit data for their commute from home to work. In the app, people can save their home location and their work location and set the timing for when they usually travel to and from home and work. 

In order to build this application, you'll need to have a database of users that stores details about your users like their username, email, and a password (never store raw, plain-text passwords -- always be hashing!). By creating a users database and the appropriate API endpoints for people to POST their data to your API, you can allow people to:
1. **Register** with your application - people can create an account on your service that is stored to the users database that includes their username, email, and password (again, never store plain-text passwords, always be hashing!)
2. **Authenticate** their identity before using your application - on arrival to your application, people can log-in to your application by submitting their username/email and password and your server will be programmed (by you of course!) to match their username/email and password against your users database to deem whether or not that person's log-in details are correct. 
3. Be **Authorized** to perform certain actions - It is one thing to be logged in (authenticated) but it is another thing to have the permissions to do certain things in your application. Probably you don't want me to be able to change your settings and preferences and I certainly don't want you to be able to see where I live and go to work. Therefore, you'll need to add methods to **authorize** certain actions based on who is making the requests to your API.

Those are the key, conceptual components of supporting users in an application. Other essentials to supporting users include:
1. user verification and password resetting using automated email
2. password reset
3. log out
4. password verification - password hashing and unhashing 
5. And much more!


In this short guide, we are going to take a look at adding authentication and authorization to a web application. "Proper" user authentication and authorization is HARD and requires a lot of care, so with this in mind, I outline what this guide is and what this guide is not below.

What this guide is:
1. a conceptual and technical introduction to authentication and authorization using the `express-basic-auth` npm module best suited for prototyping or for small scale situations in which you want to password protect your application during development.
2. a gross simplification of the important needs and considerations for setting up a **complete** authentication and authorization functionality for a web application.

What is guide is not:
1. A definitive guide on user authentication and authorization. You can read about some of the [challenges to these kinds of tutorials here](https://hackernoon.com/your-node-js-authentication-tutorial-is-wrong-f1a3bf831a46)
2. a secure way of handling user data

## Express basic Auth: A minimal (temporary) solution

`express-basic-auth` is an Express.js module that is a "Simple plug & play HTTP basic auth middleware for Express."

How it works:

1. ...
2. ...
3. ...

![Express basic auth screenshot](../assets/express-basic-auth-01.png)

### Setup
```sh
$ npm install dotenv express express-basic-auth nedb
```

**.env**
```
# YOU SHOULD CHANGE THESE
USERNAME=joeyklee
PASSWORD=super_secret_password
```

**config.js**
```js
require('dotenv').config()
module.exports = {
    USERNAME: process.env.USERNAME,
    PASSWORD: process.env.PASSWORD,
    PORT: process.env.PORT || 3000,
}
```

## Multiple users?

Imagine if you had a group project that you wanted to restrict access to more than just 1 person. You could create a list of users that you could check the basic auth inputs against. 

### List of users
Imagine you have a file called: **db/users.js** - ENSURE THIS FILE IS ADDED TO YOUR **.gitignore** so you do not check it into your files.

```js
module.exports = [
    {username: "joey", password: "california"},
    {username: "cassie", password: "jersey"},
  ]


```
**Note**:
* you should NEVER store people's passwords as strings. This is just for testing purposes in case you need a very minimals solution for password protecting your application. It is NOT meant to be something for "production."

```js
/****************************
 * your authentication 
 ****************************/
const challengeAuth = basicAuth({
    authorizer: myAuthorizer,
    challenge: true,
    unauthorizedResponse:getUnauthorizedResponse
})
//Custom authorizer checking if the username and password are in your users array
function myAuthorizer(username, password) {
    return users.some(item => {
      return username == item.username && password == item.password
    })    
}
function getUnauthorizedResponse(req) {
    return 'not authorized'
}
```

## Further exploration

We only looked at 
* [Fullstack User Authentication and Authorization Tutorial w/ Node.js/Express.js, MongoDB, and JWT](https://joeyklee.github.io/fullstack-user-auth/#/)
  * [CODE](https://github.com/joeyklee/list-project) | [DEMO](https://joeyklee-list-project.glitch.me/)

## References

* [Very Basic Express Authenication, @joeyklee](https://github.com/joeyklee/very-basic-express-auth-example)
  * [Express Basic Auth with NeDB](https://github.com/joeyklee/very-basic-express-auth-example/tree/v0.0.1-nedb)
  * [Express Basic Auth with MongoDB](https://github.com/joeyklee/very-basic-express-auth-example/tree/with-mongodb)
  * See working [DEMO](https://glitch.com/edit/#!/joeyklee-very-basic-express-auth-example?path=server.js:36:5)