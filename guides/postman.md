# Postman Guide

## Postman Interface 

If you fire up the Postman app, you're likely to eventually land on something like this:

![Postman Interface: Default options](/assets/postman-01.png)


If you select `Request` above, you are taken to a screen where you can:
* **select**: which kind of request you'd like to make: e.g. GET, POST, PUT, DELETE
* **input**: the API URL you'd like to make your requests to
* **select & input**: any `params`, `authorization`, `headers`, `body`, etc specification or data that are necessary to make your request work
  
![Postman Interface: selecting a request ](/assets/postman-02.png)


To practice with the Postman interface, let's use the posts API provided by the JSON Placeholder service -- `https://jsonplaceholder.typicode.com/posts` -- as our API to interact with.  

## GET

Using the interface, add the following:

* **method**: `GET`
* **url** `https://jsonplaceholder.typicode.com/posts`

![Postman Interface: GET request and result screenshot](/assets/postman-03.png)


## POST

### Without authorization

Using the interface, add the following:

* **method**: `POST`
* **url** `https://jsonplaceholder.typicode.com/posts`

Select the `body` tab, then:
* select: **x-www-form-urlencoded:**
* and add into the table:
  
  | KEY | VALUE |
  | :--- | --- |
  | title | hello world |
  | body  | A story about my first postman request |

Press **send**:

![Postman Interface: POST request and result screenshot](/assets/postman-04.png)


### With authorization

Using the interface, add the following:

* **method**: `POST`
* **url** `https://jsonplaceholder.typicode.com/posts`

Select the `body` tab, then:
* select: **x-www-form-urlencoded:**
* and add into the table:
  
  | KEY | VALUE |
  | :--- | --- |
  | title | hello world |
  | body  | A story about my first postman request |

Select the `authorization` tab, then select the authorization type that's relevant for you. In this case since our app doesn't need authorization, we can pretend and select `Bearer Token` and add in `abc123`:


![Postman Interface: POST request and result screenshot](/assets/postman-05.png)

Press **send**:

The result will be the same as the request above.



## PUT

You can make a PUT request by selecting the `PUT` method and ensuring that your `url` is pointed to the correct endpoint. In this case, it should go to:

```
https://jsonplaceholder.typicode.com/posts/:id
```

and assuming we have a post with the id of `1`, then we should make our PUT request to:

```
https://jsonplaceholder.typicode.com/posts/1
```

## DELETE

You can make a DELETE request by selecting the `DELETE` method and ensuring that your `url` is pointed to the correct endpoint. In this case, it should go to:

```
https://jsonplaceholder.typicode.com/posts/:id
```

and assuming we have a post with the id of `1`, then we should make our PUT request to:

```
https://jsonplaceholder.typicode.com/posts/1
```