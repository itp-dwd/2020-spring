# Reactive UIs and UI Components with JavaScript

## Reactive UIs

In ICM, we learned **object-oriented programming**—we encapsulated data and actions (functions) into objects, also known as `class`es. They looked something like this:
```js
// assuming this code uses p5.js
class Bubble {
  constructor() {
    this.x = random(0, width);
    this.y = random(0, height);
    this.size = random(5, 20);
  }

  show() {
    fill(0, 255, 255);
    ellipse(this.x, this.y, this.size);
  }

  update() {
    this.y = this.y + 1;
  }
}

let bubble = new Bubble();
```
This code contains:
1. A **data structure**:
   ```js
   const data = {
     x: Number,
     y: Number,
     size: Number
   };
   ```
2. **functions** that initialize and update the data structure:
   ```js
   constructor() {
     this.x = random(0, width);
     this.y = random(0, height);
     this.size = random(5, 20);
   }

   update() {
     this.y = this.y + 1;
   }    
   ```
3. **functions** that translate the data structure into visual elements:
   ```js
   update() {
     this.y = this.y + 1;
   }
   ```

When creating dynamic websites using HTML, CSS, and JS, we also want to do to the same things! Except we're going to use a different design pattern, called **functional programming**. I'm going to show you how it works, and then talk about why we're switching. 

## Functional programming: An applied approach

If you search "functional programming" on the Internet, you'll see terms like **pure function** or **immutable data** come up. Don't worry about what these mean yet. Using functional programming to create dynamic web interfaces solves problems that you likely haven't encountered, so I don't want to bore you with these details. Let's just look at how it works.

Let's say we were making a website to explore the characters in Harry Potter. We want to have a radio button selector to select the house, so we could see only the characters in "Gryffindor" or "Slytherin". What are all of the steps in putting this together?
1. Construct URL for Harry Potter API, use house as query string parameter
2. Make API request and load data as JSON
3. Translate JSON to HTML
4. Add event handlers to do steps 1-3 when the user selects a different house

Since we've already done (1) and (2) in the previous API section, let's focus on (3) and (4). We know that the data we're getting back is a list of characters, so we want to put them in some `<ul>`'s and `<li>`'s. We want to use JS to generate HTML that looks like this:
```html
<ul>
  <li>
    <p><span>Name: </span> Katie Bell</p>
    <p><span>Species: </span> Human</p>
  </li>
  <li>
    <p><span>Name: </span> Cuthbert Binns</p>
    <p><span>Species: </span> Ghost</p>
  </li>
  <li>
    <p><span>Name: </span> Sirius Black</p>
    <p><span>Species: </span> Human</p>
  </li>
  <!-- ... and so on -->
</ul>
```

When we're using JS to create HTML, we're not going to manually create all of the DOM elements, though technically this would work:
```js
  // "data" contains the array of characters
  let listContainer = document.createElement("ul");
  document.body.appendChild(listContainer);
  for (let i = 0; i < data.length; i += 1) {
    const listItem = document.createElement("li");
    listItem.textContent = data[i].name;
    listContainer.appendChild(listItem);
  }
```
Creating HTML this way is hard to read, and pretty long. It's also unclear what the HTML structure is. There's a better way! What we can do is create an HTML string, as though we were writing the HTML in a text editor, and then set the `innerHTML` of a DOM element to that string. The browser will then render that HTML string to the DOM.

Let's start with just creating one `<li>` string:
```js
function CharacterItem(character) {
  return `<li>
          <p>${character.name}</p>
         </li>`;
}
```
So now, we've written a function that takes a character (as JSON) as an argument and returns HTML. To create the list, we could do the following:
```js
  function CharacterList(characters) {
    let listItems = '';
    characters.forEach(character => {
      const li = CharacterItem(character);
      listItems += li;
    });
    return `<ul>
              ${listItems}
           </ul>`;
  }
```
`forEach` is a JavaScript array function. It's like a `for` loop but better! Spend some time getting comfortable: [JavaScript array functions](../guides/javascript-frontend-guide.md#javascript-array-methods).

If we want, we can make this code a little shorter using `map`:
```js
  function CharacterList(characters) {
    return `<ul>
              ${characters.map(CharacterItem).join('')}
           </ul>`;
  }
```

Then, when we are ready to actually render the HTML, we can write the following code:
```js
  // assuming there's a <div> with the id "list-container"
  const listContainer = document.getElementById("list-container");
  // data is the response from the Potter API
  const list = CharacterList(data);
  listContainer.innerHTML(list);
```

The functions `CharacterList` and `CharacterItem` can be referred to as **components**, which is a term commonly used in front end web development. 

#### Unidirectional Data Flow

We're going to get a little abstract for a moment. When we use functional programming to create interfaces, we're using a concept called unidirectional data flow. 

![Unidirectional data flow diagram, state -> view -> actions](https://flaviocopes.com/react-unidirectional-data-flow/view-actions-state.png)

There are three components here:
* **state**: This is your data, sometimes called the **store**. In our case, this is simply JS Objects, holding API response data, or interface state, i.e. if a dropdown menu is open
* **view**: This is the HTML created as a function of the state. When the state changes, the view changes.
* **actions**: These are functions, triggered by the view, which make changes to the state.

When you construct your application like this, there is one **source of truth**—the state. When a user interacts with your website, and triggers an event, e.g. they press a button and you want something to change, that event should call a **function** that makes an update to the **state**. Then, the change in state will regenerate the HTML strings. 

### Organizing your JavaScript

When using p5.js, we used a file called `sketch.js` to be our "main" file, the first place we'd look to get an overview of how the code works. From there, you might have some separate files that contained different classes or collections of functions, maybe one called `bubble.js`, `level.js`, and so on. 

When using JS without p5.js, we want to add the same kind of organization. Your folder structure should look something like this:

```
index.html
views/
  about.html
  other-page.html
styles/
  main.css
  about.css
js/
  main.js
  navigation.js
```