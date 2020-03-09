# Express Basic Auth Guide

## About

This is an example of setting up a basic "challenge auth" with `express-basic-auth` package

## So you want users?

TBD

## Auth: Authentication & authorization

TBD

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

## References

* [Very Basic Express Authenication, @joeyklee](https://github.com/joeyklee/very-basic-express-auth-example)
  * [Express Basic Auth with NeDB](https://github.com/joeyklee/very-basic-express-auth-example/tree/v0.0.1-nedb)
  * [Express Basic Auth with MongoDB](https://github.com/joeyklee/very-basic-express-auth-example/tree/with-mongodb)
  * See working [DEMO](https://glitch.com/edit/#!/joeyklee-very-basic-express-auth-example?path=server.js:36:5)