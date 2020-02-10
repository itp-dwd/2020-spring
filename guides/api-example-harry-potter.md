#### An Example API request from JavaScript

Let's practice working with APIs using the [Harry Potter API](https://www.potterapi.com/). To integrate using this API into your application, there's a few steps:

0. Look through the API documentation and figure out if it has the capabilities you are looking for. In this case, I've decided we're using the Harry Potter API so I've done that work for us.
1. Make an account and request an API key. If the API authentication uses API keys, you'll probably have to register with an email/password, and then they will give you an API key.
2. Let's say, for example, we're trying to get all of the characters in Gryffindor house. We need to look at the documentation and construct the full URL:
   1. We need to use the `/characters` endpoint: GET `/characters`
   2. Add a query string parameter, `house=Gryffindor`, bringing the url to GET `/characters?house=Gryffindor`
   3. Add the api key: GET `/characters?house=Gryffindor&key=API_KEY`
   4. Prepend with the base URL: GET `https://www.potterapi.com/v1/characters?house=Gryffindor&key=API_KEY`
3. Test that the URL works. A GET request is the same as entering a URL into your browser window, except that rather than getting a web page back we just get JSON:
  ![Potter API Response JSON](../assets/potter_api_response.png)
  **Note**: I have a Chrome extension that "prettifies" the JSON, for you it may look like a blob of text.
4. Use the Fetch API to make the API request from JS:
  ```js
  const API_KEY = "API_KEY";
  const baseUrl = "https://www.potterapi.com/v1";
  const URL = `${baseUrl}/characters?house=Gryffindor&key=${API_KEY}`;
  fetch(URL).then((response) => {
    return response.json();
  }).then((data) => {
    console.log(data);
  });
  ```
  Notice that this code uses a few newer JavaScript features:
  * [Template Strings](../guides/javascript-frontend-guide.md#template-strings)
  * [Arrow Functions](../guides/javascript-frontend-guide.md#arrow-functions)
  * [Promises](../guides/javascript-frontend-guide.md#callbacks-promises-and-asyncawait)

  We could also using async/await to make the code even shorter:
  ```js
  const API_KEY = "API_KEY";
  const baseUrl = "https://www.potterapi.com/v1";
  const URL = `${baseUrl}/characters?house=Gryffindor&key=${API_KEY}`;
  const response = await fetch(URL);
  const data = response.json();
  ```

`data` now holds the JSON from the API we wanted to get. We could do anything we want with it! Create HTML elements, make a data visualization, or even sonify it.
