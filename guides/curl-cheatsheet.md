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

## General notes on POST, PUT, and Delete

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

In Addition, for any request that needs authentication, you can add your authorization as a header flag `-H` :
  - `Authorization: Basic username:password`
  - `Authorization: Token yourAuthToken`

OR you can use the `-u` flag followed by your username`. When you send your request, you will be prompted for your password. This isn't the best way to handle things since it will force you to type your password in each time which is not good practice for testing. This might look something like:

If `joeyklee` is my username...
* Step 1:
  ```sh
  curl -X POST \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json' \
  -u joeyklee \
  -d '{"title":"Hello world"}' https://jsonplaceholder.typicode.com/posts
  ```
* STEP 2: type in your password
  ```sh
  Enter host password for user 'joeyklee':
  ```
* Step 3: the server will send back the results:
  ```json
  {
    "title": "Hello world",
    "id": 101
  }
  ```

For the POST, PUT, and DELETE examples here, you will not need to authenticate, HOWEVER, most times when interacting with an API that allows you to create, update, or delete data will require you to authenticate using and API key, token, or username/password (though usually username/password is insecure!).

## POST

The POST data to your API and database, you can use the `-X` flag specifying the `POST` method.

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

In a more typical situation in which this POST request were to require authenticaiton, and our `token` was `abc123`, our `curl` request would look something like:

```sh
curl -X POST \
-H 'Content-Type: application/json' \
-H 'Accept: application/json'  \
-H 'Authorization: Token abc123' \
-d '{"userId":9999, "title":"I love plants", "body": "Here is a story about my love for plants..." }' \
https://jsonplaceholder.typicode.com/posts
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

### PUT: JSON

The mechanics of the `PUT` request are almost identical to the POST request parameters except that instead of `-X POST`, you will be using `-x PUT` AND you the URL will be pointed to the specific item you want to update. 

Remember, the `PUT` requests are used to update an existing document in your database. 

For these examples, let's update the post with the `id:1` and change the `title` and `body`:

```sh
curl -X PUT -H 'Content-Type: application/json' -H 'Accept: application/json' -d '{"userId":9999,"title":"Hello World", "body":"I love New York"}' https://jsonplaceholder.typicode.com/posts/1
```

Or written with linebreaks:
```sh
curl -X PUT \
-H 'Content-Type: application/json' \
-H 'Accept: application/json' \
-d '{"userId":9999, "title":"Hello World", "body":"I love New York"}' \
https://jsonplaceholder.typicode.com/posts/1
```

This will return:
```json
{
  "userId": 9999,
  "title": "Hello World",
  "body": "I love New York",
  "id": 1
}
```



## DELETE

Like the `PUT` request, a delete request will usually specify which document id you want to delete. In this case, if you wanted to delete the post with `id:1`, you could do:

```sh
curl -X DELETE https://jsonplaceholder.typicode.com/posts/1
```

 NOTE: different APIs will return different messages when something is deleted. In this case you will get back an empty json object:

```json
{}
```

Again, in a more typical situation in which this DELETE request were to require authenticaiton, and our `token` was `abc123`, our `curl` request would look something like:
```sh
curl -X DELETE \
-H 'Authorization: Token abc123' \
https://jsonplaceholder.typicode.com/posts/1
```


## References:
* https://devhints.io/curl
* https://cheatsheet.dennyzhang.com/cheatsheet-curl-a4
* https://gist.github.com/Kartones/5ae36f801f3d51ac1be0
* https://flaviocopes.com/http-curl/