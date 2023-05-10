# DOM

The Document Object Model (DOM) is a programming interface for HTML and XML documents. It provides a structured representation of the document as a tree-like structure, where each element, attribute, and text node in the document is represented as a node in the tree. The DOM also provides a set of APIs for manipulating the document structure, content, and style using JavaScript.

In other words, the DOM is an object-oriented representation of the HTML or XML document that can be accessed and manipulated with JavaScript. The DOM tree consists of nodes that represent each element, attribute, and text content in the document. These nodes can be accessed and manipulated using JavaScript methods and properties, allowing developers to dynamically modify the content and behavior of a web page.

Some common tasks that can be performed with the DOM include:

- Adding, deleting, or modifying HTML elements and attributes
- Changing the styles of HTML elements
- Responding to user interactions, such as clicks and keystrokes
- Animating HTML elements
- Validating and submitting HTML forms

Overall, the DOM is a fundamental part of client-side web development, as it allows developers to create dynamic and interactive web pages using JavaScript.

## History

Browsers and the DOM have a closely intertwined history, as the development of the DOM is closely tied to the evolution of web browsers. Here is a brief overview of the history of browsers and the DOM:

- The first web browser, called WorldWideWeb, was developed by Tim Berners-Lee in 1990. It was a simple text-based browser that allowed users to view and navigate HTML documents.

- In 1993, Marc Andreessen and his team at the National Center for Supercomputing Applications (NCSA) created the Mosaic web browser, which introduced the concept of displaying images and graphical elements within HTML documents.

- In 1994, Andreessen left NCSA to form Netscape Communications Corporation, which released the first version of the Netscape Navigator web browser. Navigator became the dominant web browser in the mid-1990s and introduced many new features, including support for JavaScript.

- As web pages became more dynamic and interactive, the need for a standardized way to manipulate the content of a web page with JavaScript became apparent. In response, the World Wide Web Consortium (W3C) developed the Document Object Model (DOM) standard in the late 1990s.

- The first DOM standard, called Level 1, was released in 1998 and provided a basic set of APIs for manipulating HTML documents. Subsequent versions of the DOM standard, including Level 2 and Level 3, added more advanced features and support for XML documents.

- In the early 2000s, Microsoft introduced the Internet Explorer web browser, which became the dominant browser for several years. However, it had several proprietary features that were not fully compatible with the W3C standards, leading to inconsistencies and compatibility issues with other browsers.

- In 2004, the Mozilla Foundation released the Firefox web browser, which quickly gained popularity and helped to drive innovation in the browser market. Other browsers, such as Google Chrome and Apple Safari, also emerged in the following years.

- Today, modern web browsers provide robust support for the DOM standard, along with other web technologies such as CSS and HTML5. The DOM remains a critical component of client-side web development, as it allows developers to create dynamic and interactive web pages using JavaScript.

## Structure

The Document Object Model (DOM) is a programming interface for web documents that allows developers to access and manipulate the contents of a web page. The DOM represents the structure of an HTML or XML document as a tree-like structure, where each node in the tree corresponds to an element, attribute, or piece of content in the document.

The root of the DOM tree is called the "document object", which represents the entire document. From there, the DOM is organized into a hierarchy of nodes, with each node representing a specific element or attribute of the document. Some of the most common types of nodes in the DOM include:

1. Element Nodes: These represent the actual HTML elements on the page, such as `<div>`, `<p>`, `<h1>`, etc. Element nodes can have child nodes, such as other elements or text nodes.

2. Text Nodes: These represent the actual text content within an element node, such as the text inside a `<p>` tag.

3. Attribute Nodes: These represent the attributes of an HTML element, such as the "src" attribute of an `<img>` tag.

4. Comment Nodes: These represent comments within the HTML document, enclosed by `<!-- and -->`.

The relationship between nodes in the DOM is defined by the parent-child relationship. Each node has a parent node, except for the document object which is the root of the tree. Nodes can also have sibling nodes, which are other nodes that share the same parent.

One of the primary purposes of the DOM is to allow developers to access and manipulate the contents of a web page using JavaScript. By using the methods and properties provided by the DOM API, developers can traverse the DOM tree, modify the contents of individual nodes, and add or remove nodes from the tree. This makes it possible to create dynamic, interactive web pages that respond to user input and events.


## DOM manipulation

### createElement(), setAttribute(), appendChild()

In JavaScript, the `createElement` method is used to create an HTML element dynamically. This method is available on the `document` object in the browser and can be used to create any HTML element, such as `div`, `p`, `img`, `input`, etc.

The `createElement` method accepts a single argument, which is the tag name of the element to be created. For example, if you want to create a `div` element, you would call `document.createElement('div')`.

Once the element is created, you can manipulate its attributes and content using other DOM methods, such as `setAttribute`, `appendChild`, and `innerHTML`.

Here's an example that creates a `div` element, sets its `id` and `class` attributes, and adds some text content to it:

```javascript
// Create a new div element
const myDiv = document.createElement('div');

// Set the id and class attributes
myDiv.setAttribute('id', 'myDiv');
myDiv.setAttribute('class', 'my-class');

// Add some text content
myDiv.innerHTML = 'Hello, world!';

// Add the div to the body of the document
document.body.appendChild(myDiv);
```

This code creates a new `div` element, sets its `id` and `class` attributes, adds some text content to it, and then appends it to the `body` of the document. The end result is a new `div` element with the text "Hello, world!" inside it.

Another example. To display a message on a web page, you can create a new `p` element and then add it to the `body` of the document:

```javascript
const message = "Hello World!";
const para = document.createElement("p");
para.innerText = message;
document.body.appendChild(para);
```

### selecting DOM elements

In JavaScript, there are several ways to select parts of the Document Object Model (DOM), which is the hierarchical representation of an HTML or XML document. Here are some of the most commonly used methods:

1. getElementById: This method takes a string parameter, which is the ID attribute of the element to be selected, and returns the element object that has the specified ID.

Example: 

```html
<div id="myDiv">Hello World!</div>
```

```javascript
const myDiv = document.getElementById("myDiv");
```

2. getElementsByClassName: This method takes a string parameter, which is the class name of the element(s) to be selected, and returns a collection of element objects that have the specified class name.

Example:

```html
<div class="myClass">Hello World!</div>
<div class="myClass">Goodbye World!</div>
```

```javascript
const myClasses = document.getElementsByClassName("myClass");
```

3. getElementsByTagName: This method takes a string parameter, which is the tag name of the element(s) to be selected, and returns a collection of element objects that have the specified tag name.

Example:

```html
<p>Hello World!</p>
<p>Goodbye World!</p>
```

```javascript
const myParagraphs = document.getElementsByTagName("p");
```

4. querySelector: This method takes a string parameter, which is a CSS selector, and returns the first matching element object.

Example:

```html
<div id="myDiv">
  <p class="myClass">Hello World!</p>
</div>
```

```javascript
const myParagraph = document.querySelector("#myDiv .myClass");
```

5. querySelectorAll: This method takes a string parameter, which is a CSS selector, and returns a collection of all matching element objects.

Example:

```html
<div id="myDiv">
  <p class="myClass">Hello World!</p>
  <p class="myClass">Goodbye World!</p>
</div>
```

```javascript
const myParagraphs = document.querySelectorAll("#myDiv .myClass");
```

These are just a few of the many ways to select parts of the DOM in JavaScript. The method you choose depends on the structure of your HTML, the complexity of your selection criteria, and your personal preference.


Here's an example of creating a table dynamically using ES6 JavaScript to display data:

HTML code:
```html
<table id="data-table">
  <thead>
    <tr>
      <th>Name</th>
      <th>Age</th>
      <th>Location</th>
    </tr>
  </thead>
  <tbody>
  </tbody>
</table>
```

JavaScript code:
```javascript
// Data to be displayed
const data = [
  { name: 'John', age: 25, location: 'New York' },
  { name: 'Jane', age: 30, location: 'Los Angeles' },
  { name: 'Mark', age: 35, location: 'Chicago' },
  { name: 'Emily', age: 40, location: 'San Francisco' }
];

// Function to create table rows
const createTableRow = (rowData) => {
  const row = document.createElement('tr');
  const nameCell = document.createElement('td');
  const ageCell = document.createElement('td');
  const locationCell = document.createElement('td');

  nameCell.textContent = rowData.name;
  ageCell.textContent = rowData.age;
  locationCell.textContent = rowData.location;

  row.appendChild(nameCell);
  row.appendChild(ageCell);
  row.appendChild(locationCell);

  return row;
};

// Function to add data to table
const addDataToTable = (data) => {
  const tableBody = document.querySelector('#data-table tbody');

  data.forEach((rowData) => {
    const row = createTableRow(rowData);
    tableBody.appendChild(row);
  });
};

// Call function to add data to table
addDataToTable(data);
```

In this example, we first define the data to be displayed in the table. We then create a `createTableRow` function that takes in a row of data and returns a `tr` element containing the appropriate `td` elements populated with the data. We then define an `addDataToTable` function that takes in the data array, loops over it, and appends each row to the table body.

Finally, we call the `addDataToTable` function with the `data` array to display the data in the table on the HTML page.


### innerHTML

`innerHTML` is a property of the `Element` interface in the DOM (Document Object Model) API that represents the HTML content inside an element. When this property is set, the content of the element is replaced with the new HTML content passed as a string.

`innerHTML` has been available in the DOM API since early versions of JavaScript and has been widely used to dynamically modify the content of web pages. It is a powerful and convenient way to add, remove or modify content on the fly without having to use low-level DOM manipulation methods.

One of the advantages of `innerHTML` is that it allows developers to quickly and easily generate HTML content dynamically, without having to write complex code to create and manipulate DOM elements. For example, it can be used to create and update lists, tables, forms, or any other type of content that can be expressed in HTML.

However, `innerHTML` also has some disadvantages that should be considered when using it. One of the main concerns is security, as it can be used to inject malicious code into a web page, especially when used with user-generated content. Additionally, `innerHTML` can be slower than other DOM manipulation methods, especially when dealing with large amounts of content.

When `innerHTML` is set, the existing content of the element is replaced with the new HTML code. For example:

```html
<div id="myDiv"></div>
```

```javascript
const myDiv = document.getElementById('myDiv');
myDiv.innerHTML = '<h1>Hello, world!</h1>';
```

The above code sets the `innerHTML` property of the `myDiv` element to a string containing an `h1` tag with the text "Hello, world!". The resulting HTML on the page will be:

```html
<div id="myDiv"><h1>Hello, world!</h1></div>
```

`createElement` and `appendChild`, on the other hand, allow you to create and add new DOM elements to the page **without replacing the existing content**. `createElement` is used to create a new element, which can then be appended to an existing element using `appendChild`. For example:

```html
<div id="myDiv"></div>
```

```javascript
const myDiv = document.getElementById('myDiv');
const heading = document.createElement('h1');
heading.textContent = 'Hello, world!';
myDiv.appendChild(heading);
```

The above code creates a new `h1` element, sets its text content to "Hello, world!", and then appends it to the `myDiv` element. The resulting HTML on the page will be:

```html
<div id="myDiv"><h1>Hello, world!</h1></div>
```

`createElement` and `appendChild` are often used together in JavaScript to dynamically create and add complex HTML content to a page. While `innerHTML` can be convenient for adding simple content to a page, using `createElement` and `appendChild` can give you more fine-grained control over the structure of your page's HTML. Additionally, using `createElement` and `appendChild` can be more performant than setting `innerHTML`, especially when working with large amounts of HTML content.

Here's an example of using `innerHTML` to dynamically create and update a table in HTML:

HTML:

```html
<table id="myTable">
  <thead>
    <tr>
      <th>ID</th>
      <th>Name</th>
      <th>Email</th>
    </tr>
  </thead>
  <tbody>
  </tbody>
</table>
```

JavaScript:

```javascript
// Sample data
const data = [
  { id: 1, name: 'John Doe', email: 'john.doe@example.com' },
  { id: 2, name: 'Jane Smith', email: 'jane.smith@example.com' },
  { id: 3, name: 'Bob Johnson', email: 'bob.johnson@example.com' }
];

// Get the table and tbody elements
const table = document.getElementById('myTable');
const tbody = table.querySelector('tbody');

// Function to render the table rows
function renderRows(data) {
  let html = '';

  // Loop through the data and create HTML rows
  data.forEach(item => {
    html += `<tr>
      <td>${item.id}</td>
      <td>${item.name}</td>
      <td>${item.email}</td>
    </tr>`;
  });

  // Set the HTML of the tbody element
  tbody.innerHTML = html;
}

// Call the function to initially render the rows
renderRows(data);

// Example of updating the table with new data
const newData = [
  { id: 4, name: 'Alice Johnson', email: 'alice.johnson@example.com' },
  { id: 5, name: 'Tom Smith', email: 'tom.smith@example.com' }
];

renderRows(newData);
```

In this example, we first define an HTML table with an empty tbody element. In JavaScript, we get a reference to the table and tbody elements using `getElementById` and `querySelector`, respectively.

We then define a function called `renderRows` that takes an array of data and loops through it to create HTML rows using template literals. Finally, the function sets the `innerHTML` of the tbody element to the HTML string.

To initially render the table rows, we call the `renderRows` function with the `data` array. To update the table with new data, we simply call the function again with the `newData` array. The `innerHTML` property is then automatically updated with the new HTML, replacing the old table rows with the new ones.


## Handling events

In ES6, you can handle DOM events using the `addEventListener()` method. This method allows you to register an event listener on a DOM element, which listens for a particular event and executes a specified function when the event is triggered.

Here is an example of using `addEventListener()` to handle a click event on a button:

```javascript
const button = document.querySelector('#myButton');

button.addEventListener('click', () => {
  console.log('Button clicked');
});
```

In the example above, the `querySelector()` method is used to select the button element with an ID of "myButton". Then, the `addEventListener()` method is used to register a click event listener on the button. When the button is clicked, the arrow function is executed and the message "Button clicked" is logged to the console.

You can also use `removeEventListener()` to remove an event listener from a DOM element. This method takes two arguments: the type of event to remove and the function that was registered as the event listener.

```javascript
const button = document.querySelector('#myButton');
const handleClick = () => {
  console.log('Button clicked');
};

button.addEventListener('click', handleClick);

// Remove the event listener
button.removeEventListener('click', handleClick);
```

In the example above, the `removeEventListener()` method is used to remove the `handleClick()` function as the event listener for the click event on the button element.

`addEventListener` is a method used to attach an event listener to a DOM element. The first parameter of this method is the event type that the listener should listen for. There are many different event types that can be listened for using `addEventListener`. Here are some commonly used ones:

1. `"click"`: Fired when the user clicks the element.
2. `"mouseenter"`: Fired when the mouse enters the element.
3. `"mouseleave"`: Fired when the mouse leaves the element.
4. `"submit"`: Fired when a form is submitted.
5. `"keydown"`: Fired when a key on the keyboard is pressed down.
6. `"keyup"`: Fired when a key on the keyboard is released.
7. `"load"`: Fired when the element (e.g. an image) has finished loading.
8. `"error"`: Fired when an error occurs while loading the element.

There are many other event types that can be used with `addEventListener`. The full list can be found in the MDN Web Docs.


Here's another example:

HTML:
```
<input type="text" id="input" placeholder="Type something...">
<div id="output"></div>
```

JavaScript:
```
const input = document.getElementById('input');
const output = document.getElementById('output');

input.addEventListener('input', () => {
  output.textContent = input.value;
});
```

In this example, we get references to the input and output elements using `document.getElementById`. Then we add an event listener to the input element using `addEventListener`. The event listener listens for the "input" event and updates the content of the output element with the value of the input element using `input.value`. The `textContent` property is used to set the text content of the output element.

With this code, whenever the user types something into the input element, the content of the output element will be updated in real time.


Here's another example modifying DOM node atribbutes:

HTML:
```html
<button id="myButton">Click me!</button>
<p id="myParagraph">This is a paragraph.</p>
```

JavaScript:
```javascript
const myButton = document.getElementById('myButton');
const myParagraph = document.getElementById('myParagraph');

myButton.addEventListener('click', function() {
  myParagraph.setAttribute('style', 'color: red; font-weight: bold;');
});
```

In this example, we have a button with an id of "myButton" and a paragraph with an id of "myParagraph". When the button is clicked, we use the `addEventListener` method to attach a click event handler function to the button. Inside the event handler function, we use the `setAttribute` method to modify the style attribute of the paragraph element, changing the text color to red and the font weight to bold. This changes the appearance of the paragraph text when the button is clicked.

Here is an example of handling a submit event on a login form with simple validations using ES6:

HTML:

```html
<form id="login-form">
  <label for="username">Username:</label>
  <input type="text" id="username" name="username" required>
  <br>
  <label for="password">Password:</label>
  <input type="password" id="password" name="password" required>
  <br>
  <input type="submit" value="Login">
</form>
<p id="error-msg"></p>
```

JavaScript:

```javascript
const loginForm = document.getElementById('login-form');
const errorMsg = document.getElementById('error-msg');

loginForm.addEventListener('submit', (event) => {
  event.preventDefault(); // Prevent form from submitting
  const username = event.target.username.value;
  const password = event.target.password.value;

  // Validate input
  if (!username || !password) {
    errorMsg.textContent = 'Please enter both username and password';
    return;
  }

  // Make API request to authenticate user
  authenticateUser(username, password)
    .then(() => {
      // Redirect user to home page upon successful authentication
      window.location.href = 'home.html';
    })
    .catch(() => {
      // Display error message if authentication fails
      errorMsg.textContent = 'Invalid username or password';
    });
});

function authenticateUser(username, password) {
  // Make API request to authenticate user
  // Return a Promise that resolves if authentication is successful,
  // and rejects if authentication fails
  return new Promise((resolve, reject) => {
    setTimeout(() => {
      if (username === 'johndoe' && password === 'password123') {
        resolve();
      } else {
        reject();
      }
    }, 1000); // Simulate API request delay
  });
}
```

In this example, we first get references to the login form and the error message element using `document.getElementById()`. We then add a submit event listener to the form using `addEventListener()`.

When the form is submitted, we prevent the default form submission behavior using `event.preventDefault()`, and extract the values of the username and password fields using `event.target.username.value` and `event.target.password.value`.

We then validate the input by checking if both fields are non-empty. If either field is empty, we display an error message in the `errorMsg` element using `textContent`.

If both fields are non-empty, we make an API request to authenticate the user using the `authenticateUser()` function, which returns a Promise. If the authentication is successful, we redirect the user to the home page using `window.location.href`. If the authentication fails, we display an error message in the `errorMsg` element.

In this example, we also simulate a delay in the API request using `setTimeout()` to demonstrate the use of Promises.




