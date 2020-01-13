# cURL cheatsheet

## About

The cURL cheatsheet is a handy reference for using cURL. Adapted from: https://devhints.io/curl

This short guide will explain 4 main ways you'll be using `curl` to interact with an API. This API can be either one you create or another API or service that is available on the web.

For your practice, we will use the `https://jsonplaceholder.typicode.com/posts` as our API to interact with.  
Additional documentaiton can be found here:
* https://jsonplaceholder.typicode.com/guide.html
* https://jsonplaceholder.typicode.com/

Now let's get started.

## GET

### Assumed GET request

If you want to `GET` posts from the API, by default `curl` will send a `GET` request if no method is specified.

```sh
curl https://jsonplaceholder.typicode.com/posts
```

This will return:

```json
[
  {
    "userId": 1,
    "id": 1,
    "title": "sunt aut facere repellat provident occaecati excepturi optio reprehenderit",
    "body": "quia et suscipit\nsuscipit recusandae consequuntur expedita et cum\nreprehenderit molestiae ut ut quas totam\nnostrum rerum est autem sunt rem eveniet architecto"
  },
  {
    "userId": 1,
    "id": 2,
    "title": "qui est esse",
    "body": "est rerum tempore vitae\nsequi sint nihil reprehenderit dolor beatae ea dolores neque\nfugiat blanditiis voluptate porro vel nihil molestiae ut reiciendis\nqui aperiam non debitis possimus qui neque nisi nulla"
  },
  ... the list goes on
]
```


### Explicit GET request

If you'd like to specify the **method** of your request, you can use the `-X` flag followed by the method `GET`. 

```sh
curl -X GET https://jsonplaceholder.typicode.com/posts
```

The results look the same as above: 
```json
[
  {
    "userId": 1,
    "id": 1,
    "title": "sunt aut facere repellat provident occaecati excepturi optio reprehenderit",
    "body": "quia et suscipit\nsuscipit recusandae consequuntur expedita et cum\nreprehenderit molestiae ut ut quas totam\nnostrum rerum est autem sunt rem eveniet architecto"
  },
  {
    "userId": 1,
    "id": 2,
    "title": "qui est esse",
    "body": "est rerum tempore vitae\nsequi sint nihil reprehenderit dolor beatae ea dolores neque\nfugiat blanditiis voluptate porro vel nihil molestiae ut reiciendis\nqui aperiam non debitis possimus qui neque nisi nulla"
  },
  ... the list goes on
]
```


## POST

To send data over the wire using `curl` you can typically will:
1. include the `-H` header flag, followed by a definitiion of the content type which can be
   - `Content-Type: application/json` 
   - `Content-Type: application/x-www-form-urlencoded` 
   - `Content-Type: application/xml` 
2. include another `-H` header flag, followed by the type of content you want the server to accept:
   - `Accept: application/json`
   - `Accept: application/x-www-form-urlencoded`
   - `Accept: application/xml`
3. include the data or reference to the data you want to send. You use the data flag `-d` followed by the string representation of your data e.g.:
   - '{"name":"winnie", "favoriteFood":"honey"}' 
   - 'name=winnie&favoriteFood=honey' 
   - '<data><name>winnie</name><favoriteFood>honey</favoriteFood></data>' 

### POST: JSON

```sh
curl -X POST -H 'Content-Type: application/json' -H 'Accept: application/json' -d '{"userId":9999, "title":"I love plants", "body": "Here is a story about my love for plants..." }' https://jsonplaceholder.typicode.com/posts
```

You might also sometimes see the curl requests written out with a line break using the backslash `\` to separate out the commands for more clarity:

```sh
curl -X POST \
-H 'Content-Type: application/json' \
-H 'Accept: application/json'  \
-d '{"userId":9999, "title":"I love plants", "body": "Here is a story about my love for plants..." }' \
https://jsonplaceholder.typicode.com/posts
```

NOTE: there cannot be ANY spaces after a linebreak `\` character. If there are, it will break your command!

This will return:
```json
{
  "userId": 9999,
  "title": "I love plants",
  "body": "Here is a story about my love for plants...",
  "id": 101
}
```



### POST: URLencoded

```sh
curl -X POST -H 'Content-Type: application/x-www-form-urlencoded' -H 'Accept: application/x-www-form-urlencoded' -d 'userId=9999&title=I%20love%20plants&body=Here%20is%20a%20story%20about%20my%20love%20for%20plants...' https://jsonplaceholder.typicode.com/posts
```

You might also sometimes see the curl requests written out with a line break using the backslash `\` to separate out the commands for more clarity:

```sh
curl -X POST \
-H 'Content-Type: application/x-www-form-urlencoded' \
-H 'Accept: application/x-www-form-urlencoded' \
-d 'userId=9999&title=I%20love%20plants&body=Here%20is%20a%20story%20about%20my%20love%20for%20plants...' \
https://jsonplaceholder.typicode.com/posts
```

This will return:
```json
{
  "userId": "9999",
  "title": "I love plants",
  "body": "Here is a story about my love for plants...",
  "id": 101
}
```

### POST: JSON as a File reference on your computer

```sh
curl -X POST -H 'Content-Type: application/json' -H 'Accept: application/json' -d '@/Users/joeyklee/Desktop/myNewPost.json' https://jsonplaceholder.typicode.com/posts
```

You might also sometimes see the curl requests written out with a line break using the backslash `\` to separate out the commands for more clarity:

```sh
curl -X POST \
-H 'Content-Type: application/json' \
-H 'Accept: application/json' \
-d '@/Users/joeyklee/Desktop/myNewPost.json' \
https://jsonplaceholder.typicode.com/posts
```


## PUT

```sh
curl -X PUT 
```

## DELETE

```sh
curl -X DELETE
```



## References:
* https://devhints.io/curl
* https://cheatsheet.dennyzhang.com/cheatsheet-curl-a4
* https://gist.github.com/Kartones/5ae36f801f3d51ac1be0
* https://flaviocopes.com/http-curl/