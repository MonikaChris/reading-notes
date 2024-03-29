# Reading Notes

A collection of thoughts and questions about Code Fellows reading materials.

## Code 301 - Intermediate Software Development

## Prework

[301 Prework](https://codefellows.github.io/code-301-guide/curriculum/prework/)

### Prework Questions:
1. In the process of setting up my computer, I switched my Terminal shell to zsh from bash. What are pros and cons of bash vs. zsh?
2. For the arrow functions assignment, I was supposed to create an empty repository, clone it, download a single folder from a class repository, and then add it to my empty repository. I found a way to do this, but I'd like to know the correct way, since what I did seemed like a workaround.
3. For Chocolate Pizza, I mostly used flexbox. Is this the most efficient/concise way, or is there a better method for this particular layout? Grid seemed like it might be more verbose than flexbox in this case? If I had used grid, should the whole page be on one grid, or should I use subgrids? Also, what was the best way to position the printer icon? I used transform for this, but that might not be the best practice?

### Tips:
- To switch back and forth between zsh (current default) and bash shell, run the following commands in terminal:
  `exec bash`
  `exec zsh`
  
### Favorite Discoveries:
- How to style checkboxes for chocolate pizza using `appearance: none;`, CSS sibling selector, and `:checked`, as well as include ~~strikethrough~~ checkbox labels.


## Class 1: Intro to React and Components

### Why this topic matters:
React has a Component-Based Architecture. Other popular tools also use CBA’s due to certain advantages, like reusability and encapsulation of functionality. For this reason, it’s important to understand the design principles behind CBA’s.

### Component-Based Architecture Questions
1.	What is a “component”?

A component is a functional or logical unit of code that has an interface and well-defined functionality. It is “modular, portable, replaceable, and reusable” and encapsulates its functionality.
https://www.tutorialspoint.com/software_architecture_design/component_based_architecture.htm

2.	What are the characteristics of a component?

“Reusability, replaceable, not context specific, extensible, encapsulated, independent.”
https://www.tutorialspoint.com/software_architecture_design/component_based_architecture.htm

3.	What are the advantages of using component-based architecture?

- “Ease of development” since components can be switched out without affecting the rest of the system
- “Reusable”
- “Modification of technical complexity” – I believe the modular design and encapsulation of implementation aid in managing complexity
- “Reliability”
- “System maintenance and evolution” – due to ease of updates “without affecting the rest of the system”
- “Independent” – components can operate and be developed independently
https://www.tutorialspoint.com/software_architecture_design/component_based_architecture.htm


### Props in React Questions
1.	What is “props” short for?

Properties

2.	How are props used in React?

Props are objects that pass read-only data between components in one direction from parent to child

3.	What is the flow of props?

Unidirectional from parent to child components


# Reading Notes 2: React State and Props
State and Props are important for managing the flow of data in your application. Different types of data are handled by state vs. props, so it’s important to understand the different use cases.


## React Lifecycle

1. Based off the diagram, what happens first, the ‘render’ or the ‘componentDidMount’?

Render

2. What is the very first thing to happen in the lifecycle of React?

Mounting phase/constructor call. 
First the constructor is called (before the component is mounted). After that, the following steps occur in the Mounting phase: static getDerivedStateFromProps, then render, then componentDidMount, then UNSAFE_componentWillMount.

3. Put the following things in the order that they happen: componentDidMount, render, constructor, componentWillUnmount, React Updates:

- Constructor
- Render
- componentDidMount
- React Updates
- componentWillUnmount

4. What does componentDidMount do?
componentDidMount is invoked after a component is mounted and provides the opportunity to initiate a network request in order to load something or initialize the DOM. This is also where subscriptions should go.

## React State vs. Props

1. What types of things can you pass in the props?

Props are like arguments that you pass to a function.  They are data/information that you want to display inside a component without hard coding it.  Props can be data that specify the initialization of a component or something you want to render. 

2. What is the big difference between props and state?

Props are handled outside of a component, get updated outside of a component, and are passed into the component.
State is handled inside a component and gets updated inside the component. 

3. When do we re-render our application?

When the state of a component changes

4. What are some examples of things that we could store in state?
Anything that the component will be updating and re-rendering based on user input, for example, the current value of a counter, or user input into a form. 


## Things I want to know more about
1. I’m curious about how React can be integrated with non-React apps and how much of an app is typically built with React at a company like Facebook. I’m curious about when, how, and how often React gets used, and when it’s used in combination with other technologies (especially given that it seems to have a fairly unique design philosophy in terms of “separation of concerns” rather than “separation of technology”).


# Reading Notes 3: Passing Functions as Props

## React Docs – Lists and Keys

1. What does .map() return?

Map returns an array with values that result from applying a callback function to the array that called the map function.

2. If I want to loop through an array and display each value in JSX, how do I do that in React?

You can call the map function on an array, and pass in a callback function that places each value of the array inside curly braces.

3. Each list item needs a unique ____.

Key

4. What is the purpose of a key?

A key helps React keep track of any changes made to individual list items so that the element remains stable. 


## The Spread Operator

1. What is the spread operator?

It lets you pass elements of an array into a function as a list of arguments.
“In JavaScript, spread syntax refers to the use of an ellipsis of three dots (…) to expand an iterable object into the list of arguments.”
https://medium.com/coding-at-dawn/how-to-use-the-spread-operator-in-javascript-b9e4a8b06fab

2. List 4 things that the spread operator can do.

Broadly, the spread operator can do the following:
- Add items to an array
- Combine arrays or objects
- Pass in the elements of an array as arguments to a function

Examples of specific cases:
- Copy an array
- Concatenate arrays
- Populate a Math function with values from an array (e.g. Math.min())
- Convert a NodeList to an array


3. Give an example of using the spread operator to combine two arrays.

const array1 = [1, 2, 3];

const array2 = [4, 5, 6];

const comboArray = […array1, …array2];



4. Give an example of using the spread operator to add a new item to an array.

const array1 = [1, 2, 3];

const array2 = […array1, 4];


5. Give an example of using the spread operator to combine two objects into one.

const object1 = {favSnack: “tomatoes”};

const object2 = {favColor: “red”};

const favorites = {…object1, …object2};


## How to pass functions between components

1. In the video, what is the first step that the developer does to pass functions between components?

Creates a function where the state is that he plans to change

2. In your own words, what does the increment function do?

It takes in a name, and then loops through the component state, which contains several person objects, each with a name property and a count property. If the name on a person object matches the name passed into the function, it increments the count for that person object. The function then returns the altered array of person objects.

3. How can you pass a method from a parent component into a child component?

You can pass a function just as you would pass props – inside the parent's tag that creates the child component, include an attribute with the name of the function, and set it equal to {this.functionName}.

4. How does the child component invoke a method that was passed to it from a parent component?

Inside the child component, call the function defined in the parent component from the props (there is now a reference to this function stored in props), and pass in any arguments that the function needs, which can also be stored as props. For example: 
this.props.functionName(this.props.name);


## Reading 04: React and Forms

### React Docs - Forms

**1. What is a ‘Controlled Component’?**

Rather than having an HTML form element maintain its own state/value, a controlled component keeps track of the element’s value inside the React component state, which gets updated via setState(). So the React component manages the state of the form element, and controls the element based on user input.\
“A form element becomes ‘controlled’ if you set its value via a prop.”\
https://goshacmd.com/controlled-vs-uncontrolled-inputs-react/

**2. Should we wait to store the user’s responses from the form into state when they submit the form OR should we update the state with their responses as soon as they enter them? Why.**

The form should be continually updated as the user enters input, since this way the user input is passed directly to the component state, where it is maintained. This way the component is responsible for maintaining the state of the element. “With a controlled component, the input’s value is always driven by the React state.”
https://reactjs.org/docs/forms.html

**3. How do we target what the user is entering if we have an event handler on an input field?**

The form element should have a value attribute, which is set equal to {this.state.value}, and an onChange attribute, which takes in the event handler {this.handleChange}. onChange is triggered by a user making any input changes, so any user input will generate an event that gets passed into the handleChange function. So the handleChange function will receive any user input and update the component state accordingly. The value attribute gets its value from the component state, and so this process will ensure that any user input gets immediately stored in the component state, and this data will in turn be supplied to the form element via the value property of the component state.

### The Conditional (Ternary) Operator Explained

**1. Why would we use a ternary operator?**

Ternary operator format: 

condition ? value if true : value if false;

https://codeburst.io/javascript-the-conditional-ternary-operator-explained-cac7218beeff

The ternary operator offers a more concise way to write a single if/else statement where, based on a single condition, the program should return a particular value if the condition is true, and a different value if the condition is false. 
With the ternary operator, this situation can be handled in one line, and it’s easily readable.
Ternary operator expressions can also be nested to handle more complex cases, and again, the resulting expression is more concise.
To run multiple operations inside a ternary expression, use commas to separate expressions and optionally include parentheses for readability.

**2. Rewrite the following statement using a ternary statement:**

```
if(x===y) {
	console.log(true);
} 
else {
	console.log(false);
}
```
```
x===y ? console.log(true) : console.log(false);
```


## Reading 05: Putting it All Together

### Thinking in React

**1. What is the single responsibility principle and how does it apply to components?**

Each component should only handle one unit of functionality. It should do one thing. If a component grows to the point where it’s handling multiple tasks/responsibilities, from a design perspective, it would be better to split it up into multiple components, so that each component is only responsible for one action.

**2. What does it mean to build a ‘static’ version of your application?**

A static version renders the UI based on the data model, but has no interactivity. It is advisable to build a static version first and then add interactivity. The static version should be composed of reusable components and pass data around via props, but should not use state. State is only used for implementing interactivity because it manages changing data, which is not relevant for a static app.

**3. Once you have a static application, what do you need to add?**

Interactivity (and also state). Think about “the minimal set of mutable state that your app needs.”\
https://reactjs.org/docs/thinking-in-react.html

**4. What are the three questions you can ask to determine if something is state?**

- Does it get passed to the component via props? If so, then not state.
- Is it unchanging? If so, then not state.
- Is it computable based on other data inside the component? If so, then not state.

**5. How can you identify where state needs to live?**

Identify all the components that require a piece of state data and determine which of these components is above the others in the hierarchy – this is the common owner, and it should manage state. Alternatively, if necessary, choose a component above the common owner in the hierarchy to hold state. If there is no good candidate, create a new component whose sole purpose is to manage state for these other components.


### Higher-Order Functions

**1. What is a “higher-order function”?**

A higher-order function is a function that either takes another function(s) as arguments, or returns a function.

**2. Explore the greaterThan function as defined in the reading. In your own words, what is line 2 of this function doing?**
```
function greaterThan(n) {
	return m => m > n;
}
let greaterThan10 = greaterThan(10);
console.log(greaterThan10(11));
```

Line 2 returns a function that takes an input parameter m, and returns the truth value of the expression m > n, where n is a value that was passed into the higher-order parent function.

**3. Explain how either map or reduce operates, with regards to higher-order functions.**

An implementation of map() could take in an array and a transform function as parameters. Map is therefore a higher order function, since it takes another function as an argument. The map function iterates through the passed in array using a for…of loop. On each iteration, it applies its transform function to the current element and pushes the transformed element to a new array. After iterating through the full array, it returns the new array of transformed elements. This is an example of a higher-order function because of its use of the transform function that was passed in as an argument.


## Reading Notes 6

### An Introduction to Node.js on sitepoint.com

**1. What is node.js?**

“Node.js is an event-based, non-blocking, asynchronous I/O runtime that uses Google’s V8 JavaScript engine and libuv library.”
https://www.sitepoint.com/an-introduction-to-node-js/

**2. In your own words, what is Chrome’s V8 JavaScript Engine?**

Chrome’s V8 is a JavaScript engine, meaning it’s software that compiles JavaScript to machine code so that a computer can execute it, and it runs on Chromium-based web browsers, such as Brave, Opera, and Vivaldi. Chrome V8 is open source.

**3. What does it mean that node is a JavaScript runtime?**

Node does not execute in the browser – rather, extra functionality in the form of a file system API, an HTTP library, and other utilities were added to Chrome V8 in order for Node (a program) to execute JavaScript on your computer.

**4. What is npm?**

Npm is a package manager (comes bundled with Node).

**5. What version of node are you running on your machine?**

v18.6.0

**6. What version of npm are you running on your machine?**

8.13.2

**7. What command would you type to install a library/package called ‘jshint’?**

npm install -g jshint

**8. What is node used for?**

Frameworks like React and Angular require various packages in order to run properly, and npm and Node together create the right kind of development environment for using these tools. Node is able to run build tools that are “designed to automate the process of developing a modern JavaScript application.” These build tools are important in modern JavaScript development, and their uses include, “bundling your JavaScript files and dependencies into static assets, running tests, or automatic code linting and style checking.”
Node.js can also be used to run JavaScript on a server. 


### 6 Reasons for Pair Programming

**1. What are the 6 reasons for pair programming?**

- Greater efficiency
- Engaged collaboration
- Learning from fellow students
- Social skills
- Job interview readiness
- Work environment readiness

**2. In your experience, which of these reasons have you found most beneficial?**

I haven’t done pair programming, but getting the chance to is one of the reasons why I wanted to sign up for a bootcamp. I think it’s really valuable to learn from other people by watching their approach and seeing how their thinking might differ from yours. I think this is one of the best ways to broaden your understanding of a subject and find new and better strategies for problem solving.


**3. How does pair programming work?**

One partner is the driver and the other is the navigator. The driver does the actual typing of code and manages version control, while the navigator thinks about the high-level overview of the problem and talks through the algorithms and coding steps, checks for code errors, and potentially also looks up documentation in the process.


## Reading Notes 07

### "How I explained REST to my brother"

**1. Who is Roy Fielding?**

One of the creators of the HTTP specification and REST

**2. Why don’t the techniques that we use today work well when we need to be able to talk to all of the machines in the world?**

Because machines don’t have a “universal noun.” Instead, different languages and databases have different ways of referring to their resources. Additionally, under SOAP, verbs weren’t polymorphic.

**3. What is the HTTP protocol that Fielding and his friends created?**

It’s a standardized way of applying machine “verbs” to machine “nouns.” Crucially, different nouns can still have the same set of verbs applied to them, so they can be handled similarly.
“HTTP is actually a general purpose protocol for applying verbs to nouns.”\
https://gist.github.com/brookr/5977550

**4. What does a GET do?**

It retrieves information.

**5. What does a POST do?**

It adds information from one system to another system.

**6. What does PUT do?**

It replaces information in a particular system with different information.

**7. What does PATCH do?**

It partially updates information in a particular system.


## Reading Notes 08

https://docs.microsoft.com/en-us/azure/architecture/best-practices/api-design

**1. What does REST stand for?**

Representational State Transfer

**2. REST APIs are designed around a ____.**

Uniform interface and stateless request model. “REST is an architectural style for building distributed systems based on hypermedia.”
A true RESTful API uses HATEOAS.

**3. What is an identifier of a resource? Give an example.**

A URI, which is a unique identifier for a resource. It’s a unique way to refer to that resource.
Example from text: https//adventure-works.com/orders/1 

**4. What are the most common HTTP verbs?**

GET, POST, PUT, PATCH, DELETE

**5. What should the URIs be based on?**

Items should be grouped into collections and organized in a hierarchy 

**6. Give an example of a good URI.**

Example from text: A URI ending in /customers should direct to the collection of customers, and /customers/5 should direct to the customer with ID 5

**7. What does it mean to have a ‘chatty’ web API? Is this a good or a bad thing?**

A chatty API is one that makes a large number of small resources available, such that a client needs to make many requests to get all the info. This is bad because each web request adds to the server load. It is better to allow clients to request more related data resources in a single call so that clients can access all the API data that they need with fewer calls. However, this should be done carefully, since there is also overhead and latency in returning large quantities of data, so it’s better to avoid returning large amounts of data that the client doesn’t need.

**8. What status code does a successful GET request return?**

200 (or 204 when the request was successful but there is no content)

**9. What status code does an unsuccessful GET request return?**

404 (Not Found)

**10. What status code does a successful POST request return?**

201 if content is created, or 200 if a method was successful but no new resource was created. 204 is for a successful POST where there is no result to return.

**11. What status code does a successful DELETE request return?**

204



## Reading Notes 09

### Functional Programming Concepts


**1. What is functional programming?**

A programming paradigm based on mathematical functions and which avoids mutable data and changing state.

**2. What is a pure function and how do we know if something is a pure function?**

A pure function is deterministic, meaning it returns the same output if given the same input, and it “does not cause any observable side effects.”
We know a function is pure if it only uses parameters passed into the function, (since external global variables can change, resulting in different outputs for the same input parameters), does not read external files, and does not use randomly generated numbers. Additionally, it does not cause side effects like modifying a global object or anything passed by reference.

**3. What are the benefits of a pure function?**

If all functions in a program are pure, then they are well isolated and the program is more stable, predictable, consistent, easier to understand, and easier to update and maintain. The program is also easier to test, because parameter values will always be consistent.

**4. What is immutability?**

An immutable element is one whose state cannot be changed. If you want to make changes, you must create a new element.

**5. What is Referential transparency?**

Referential transparency arises from the combination of pure functions and immutable data. The result is that a function will consistently yield the same output for each input.


### Node JS

**1. What is a module?**

A logical unit of code that has a single piece of functionality in an application.

**2. What does the word ‘require’ do?**

`require()` is a function on the global object in Node.js (so can be used anywhere) and it is used to import modules . It takes a path as a string, and it returns code from another module, and so should be assigned to a variable to hold the returned values. 

**3. How do we bring another module into the file the we are working in?**

Include `require(‘/module-path’)` at the top of a file, and assign it to a variable. The module must also be available for export via `module.exports` inside the module. 

**4. What do we have to do to make a module available?**

Inside a particular module, you need to explicitly declare which functions should be made available for import elsewhere. This is done by including `module.exports` and setting this equal to any functions that should be available to modules that import it using the require function.



## Reading Notes 10

### Understanding the JavaScript Call Stack

https://www.freecodecamp.org/news/understanding-the-javascript-call-stack-861e41ae61d4

**1. What is a ‘call’?**

A call is an invocation of a function – the parameters and variables are pushed to the call stack in the form of a stack frame, which is an allocation in memory. The memory is cleared once the function returns and is popped off the stack.

**2. How many ‘calls’ can happen at once?**

There is a single call stack, so function execution happens one at a time from the top of the stack to the bottom.

**3. What does LIFO mean?**

Last in, first out

**4. Draw an example of a call stack and the functions that would need to be invoked to generate that call stack.**

 push &nbsp; pop\
 &nbsp; &nbsp; \\\/ &nbsp; &nbsp; &nbsp; \/\\\
`function3`\
`function2`\
`function1`

**5. What causes a Stack Overflow?**

When a recursive function call has no exit point, or more generally when the number of calls exceeds the maximum that the browser stack can hold.


### JavaScript Error Messages

https://codeburst.io/javascript-error-messages-debugging-d23f84f0ae7c

**1. What is a ‘reference error’?**

A reference error occurs when you try to use an undeclared variable.

**2. What is a ‘syntax error’?**

A syntax error results from invalidly written code. The code itself has a syntax error and can’t be parsed.

**3. What is a ‘range error’?**

A range error occurs when entries of an array are accessed that are outside the bounds of the array. More generally, it’s when an object has a length and you try to access something outside that length or give it an invalid length.

**4. What is a ‘type error’?**

A type error occurs when there are incompatibilities between variable/parameter types and the actions you’re trying to perform.

**5. What is a breakpoint?**

In a debugger, you can set a breakpoint on a line of code, and then when you run the code, it will pause at that point, and you’ll be able to inspect the values of the different variables at that point.

**6. What does the word ‘debugger’ do in your code?**

It shows you the history before reaching that breakpoint.


## Reading Notes 11

### NoSQL vs. SQL

https://www.thegeekstuff.com/2014/01/sql-vs-nosql-db/?utm_source=tuicool

**1. List 5 differences between SQL vs. NoSQL databases:**

- SQL databases are relational databases, NoSQL databases are non-relational or distributed databases
- SQL databases are table based, NoSQL databases are document based, key-value pairs, graph databases, or wide-column stores
- SQL databases have predefined schema, NoSQL databases have dynamic schema for unstructured data
- SQL databases are vertically scalable, NoSQL databases are horizontally scalable. Scaling vertically means increasing the server hardware capacity, whereas expanding horizontally means increasing the number of servers.
- SQL databases use structured query language, NoSQL databases have more variable syntax that act on collections of documents

**2. What kind of data is a good fit for a SQL database?**

SQL is the right choice for an environment with many complex queries, since NoSQL databases don’t have standard interfaces to handle complex queries, and NoSQL queries are less powerful than SQL queries.
SQL databases are also better for transaction-intensive applications, since they are more stable and have atomicity – SQL databases follow ACID design (Atomicity, Consistency, Isolation, Durability), whereas NoSQL databases employ CAP (Consistency, Availability, Partition tolerance).

**3. Give a real world example.**

Some SQL databases include: MySql, Oracle, Sqlite, Postgres, and MS-SQL

**4. What kind of data is a good fit for a NoSQL database?**

NoSQL is better for hierarchical data and for very large databases, since horizontal scaling is possible (can’t easily distribute SQL database across many more servers). 

**5. Give a real world example.**

Some NoSQL databases include: MongoDB, CouchDB, Redis 

**6. Which type of database is best for hierarchical data storage?**

NoSQL

**7. Which type of database is best for scalability?**

NoSQL is better for scalability overall.
SQL databases can be scaled vertically, whereas NoSQL databases are better for horizontal scaling.


### NoSQL vs. SQL Video

https://www.youtube.com/watch?v=ZS_kXvOeQ5Y

**1. What does SQL stand for?**

Structured Query Language

**2. What is a relational database?**

From the video: A relational database works with certain assumptions and supports the SQL language.
More specifically (from Wikipedia): A relational database uses a relational model of data, which is a way of structuring data based on first-order predicate logic. Data is represented as tuples and further grouped into relations, which are sets of tuples that all belong to a particular data domain, namely a kind of data.
From video: You might have a table that stores data about other tables, thereby linking/relating them. This is typical of relational databases. There can be one-to-one, one-to-many, and many-to-many relations.
In summary, “We store data distributed across multiple tables, which we then connect through relations, and the SQL language is capable of querying these relations.” Using SQL queries, you can retrieve data distributed across multiple tables, join it, and return it in one result. This is one of the main strengths of SQL, namely that you have “normalized, distributed data which you can merge together with SQL queries.”

**3. What type of structure does a relational database work with?**

Table 

**4. What is a ‘schema’?**

Schema refers to the rules that govern the structure/organization of the database. The schema specifies which data can go into a table by defining fields. The fields specify the type of data that the table can hold. All table entries have to adhere to the schema, so data to be entered into the table must be normalized, i.e., put in the proper format that fits into the table.
Note: typically work with multiple related tables.

**5. What is a NoSQL database?**

NoSQL databases don’t use tables, but instead use collections of documents. They don’t use schemas and there are no or very few relations between collections. Both horizontal and vertical scaling are possible (unlike SQL which can mostly be vertically scaled, and vertical scaling has limits). NoSQL has better performance for mass read and write operations, although write performance is not good if you have duplicated data distributed across multiple collections. It’s advisable to keep all data for a particular purpose in one collection that you query frequently.

**6. How does it work?**

Collections contain documents, which are analogous to table rows, except they look like JSON files, and they don’t all have to use the same schema. You can have various documents in one collection that each have different fields.

**7. What is inside of a Mongo database?**

Mongo is designed to store large amounts of data efficiently, something SQL databases can struggle with. It contains collections of documents, each of which can contain data in a variety of formats.

**8. Which is more flexible - SQL or MongoDB? and why.**

NoSQL is more flexible because it doesn’t use schemas, meaning it does not prescribe the data format. That means you can add any new data you want. In general, there are no relations in NoSQL, though you could set them up and query them manually if you wanted. So while you can relate collections, and this is done, NoSQL databases rely on these relations much less. Instead, all the information is stored in one place, namely in each collection. This makes querying more efficient.

**9. What is the disadvantage of a NoSQL database?**

Since data doesn’t follow particular schemas, there is inherent uncertainty about the format of the data contained in a NoSQL database and if it conforms to a format you might be using. You can also have duplicate data that needs to be updated in different parts of the database.


## Reading 12

### Status Codes Based on REST Methods

https://www.moesif.com/blog/technical/api-design/Which-HTTP-Status-Code-To-Use-For-Every-CRUD-App/

**1. In your own words, describe what each group of status code represents:**

100’s = informational codes about how the http request is being processed\
200’s = success codes indicating the request was properly received\
300’s = redirect codes indicating that the requested resource is not currently available at the specified location\
400’s = error codes indicating some kind of invalid request\
500’s = server error codes indicate that there is a problem with the request due to some error on the server side, although they can also result from a client-side error. It’s usually recommended to resend the request.

**2. What is a status code 202?**

This means an asynchronous request was successful, but since it’s async, the processing will be completed at a later time.

**3. What is a status code 308?**

This means “permanent redirect,” and provides the new location for a resource that has been permanently moved.

**4. What code would you use if an update didn’t return data to a client?**

204 – No Content

**5. What code would you use if a resource used to exist but no longer does?**

410 - Gone

**6. What is the ‘Forbidden’ status code?**

403 – in this case, the client does not need authorization but also does not have permission to access the resource.

### Build a REST API with Node.js, Express, & MongoDB

https://www.youtube.com/watch?v=fgTGADljAeg

**1. Why do we need to pull our MongoDB database string out of our server and put it into our .env?**

For deployment, mongoose will use this path to access the database, and this path should be kept hidden and not uploaded to GitHub.

**2. What is middleware?**

Middleware is software that runs when the server receives a request but before that request gets passed to routes.

**3. What does `app.use(express.json())` do?**

This allows the server to accept JSON in the body of a request instead of a post element, a get element, or something else.

**4. What does the` /:id` mean in a route?**

The colon signifies that ‘id’ is a parameter, and you can access the id parameter inside the express get method using request.params.id.

**5. What is the difference between `PUT` and `PATCH`?**

Patch updates only certain information depending on what the user passed in. Put updates all the info.

**6. How do you make a default value in a schema?**

Call `new mongoose.Schema()`, set it equal to a variable to hold that schema, and pass in a JavaScript object whose keys are the properties of the schema. The values should specify the data type of each property. But you can also assign objects as values, which include the data type (type is the key, the value is a data type), and can also hold other properties, such as a default. To set the default value, include a key of ‘default’ and assign it the default value.

**7. What does a `500` error status code mean?**

This means there was a server error.

**8. What is the difference between a status `200` and a status `201`?**

201 is more specific and means an object was successfully created. 200 just means the request was successful. You should always send status 201 for a successful post.


## Reading 13

### CRUD Basics

https://medium.com/geekculture/crud-operations-explained-2a44096e9c88

**1. Which HTTP method would you use to update a record through an API?**

Put

**2. Which REST methods require an ID parameter?**

Put and Delete


### Speed Coding: Building a CRUD API

https://www.youtube.com/watch?v=EzNcBhSv1Wo

**1. What’s the relationship between REST and CRUD?**

REST is a software architecture with specific design constraints that produce five key properties. The resulting REST application allows client and server to act independently, is stateless (meaning the server does not keep track of the client’s state), is cacheable, creates a uniform interface (meaning the client and server are able to interact in predefined and consistent ways), and the system is layered (meaning interactions between client and server stay the same even if layers of software exist between them).
Because of these design constraints, and because REST APIs on the web use the HTTP protocol, they make CRUD operations available. So the interface that a REST API provides is one that allows the client to perform create, read, update, and delete operations.\
https://nordicapis.com/crud-vs-rest-whats-the-difference/

**2. If you had to describe the process of creating a RESTful API in 5 steps, what would they be?**

- Make an object model that organizes resources that your REST API should make available to a client
- Set URI’s/endpoints for each resource
- Define representations for resource data
- Create CRUD methods that let clients interact with the data stored in the database – clients should be able to create, read, update, and delete data from the database.
- Implement other features like authorization and security\
https://restfulapi.net/rest-api-design-tutorial-with-example


## Reading 14
### Diversity & Inclusion in Tech

### Consider the history: That Time When Women Stopped Coding

https://www.npr.org/sections/money/2014/10/21/357629765/when-women-stopped-coding

**1. What occurred during the same time as the beginning of the decline of women in computer science?**

The advent of personal computers, and a trend of buying personal computers more often for boys than for girls.

**2. Why does it matter that males had been playing on computers growing up?**

Greater exposure and access to computers from a young age tends to make people more familiar with computers and more skilled at using them. This may advantage them relative to their peers in computer science classes, and if instructors are not mindful of differences in prior experience and access, they may make premature judgements about student aptitude and they may also fail to tailor their instruction to cater to different levels of preparation. As a result, people who might have a strong interest in computer science, and even exceptional talent for it, may nonetheless fail to discover and pursue this interest, and they may never get the chance to work in tech even though they have a lot to contribute.

### Why diversity matters to your tech company

https://www.usatoday.com/story/tech/columnist/2015/07/21/why-diversity-matters-your-tech-company/30419871/

**1. When are diversity efforts most successful?**

Diversity efforts are most successful when companies have well defined rationales for aiming to increase diversity, make a clear plan to guide their efforts, and put in place accountability measures to track progress.

**2. Why do diverse companies perform better?**

Studies show that diverse teams are more creative and innovative. More diverse companies also likely draw from a larger talent pool, because more people, including those from non-traditional backgrounds, are being brought in and given the opportunity to develop their talents and contribute.

**3. Give an example of how a diverse company can serve a diverse user base or vise-versa.**

The YouTube team that built their iOS app was almost exclusively right handed, and as a result, the final product did not cater to left-handed users and 5 to 10% of uploaded videos were upside down. It would make sense that a more diverse team can better accommodate a more diverse set of customers, since collectively, the team will be more aware of a broader set of challenges and experiences that diverse users face.


## Reading 15

### What is OAuth

https://www.csoonline.com/article/3216404/what-is-oauth-how-the-open-authorization-framework-works.html

**1. What is OAuth?**

OAuth is an open-standard authorization protocol (version 1.0)/framework (version 2.0) that enables a secure single sign-on (SSO) for users across multiple computers and across various websites. OAuth handles authorization, not authentication, and should be used together with a protection protocol like Transport Layer Security (TLS).
Important note on security:
“Coders and users should look to ensure that OAuth is running inside of TLS protection. Developers can implement code to enforce TLS use and users should be aware that TLS is being used whenever they are begin asked to input authentication credentials (just like they should anytime they are entering in credentials). Because of the lack of inherent security binding, it’s possible for a rogue website to phish a user’s legitimate credentials during the part of the process where the user is being required to authenticate themselves to the authorization provider.”

**2. Give an example of what using OAuth would look like.**

Through OAuth, a user can be given the option to log into a particular website by being logged into a different website. The latter website provides authentication to the former website.

**3. How does OAuth work? What are the steps that it takes to authenticate the user?**

When a user requires authorization to access a website resource, an OAuth-enabled site communicates with a second site that has already authenticated the user. The second site sends a one-time token and a one-time unique and secret identifier for the transaction. The receiving site passes the token and id to the client, which passes this to an authorization provider (not necessarily the second site, but could be). Once the user has been authenticated, they are given the option to approve the authorization transaction to access the second website. Once the user does this, they receive an approved access token, which they can use to access the first website. The first website gives the access token to the second website as proof of user authentication, and then the second website gives access to the first website on behalf of the user.

**4. What is OpenID?**

OpenID is similar to OAuth, but is focused on authentication rather than authorization. “OpenID is for humans logging into machines, OAuth is for machines logging into machines on behalf of humans.”  Following a 2014 update, OpenID became an authentication layer for OAuth, so the two technologies can work together.


### Authorization and Authentication flows

https://auth0.com/docs/get-started/authentication-and-authorization-flow

**1. What is the difference between authorization and authentication?**

Authentication involves verifying user identity. Authorization grants access to resources following authentication.

**2. What is Authorization Code Flow?**

It is a system for server-side applications that don’t make their source code public, and so it allows them to exchange an authorization code for a token. The token can be used to call an API and get user data.

**3. What is Authorization Code Flow with Proof Key for Code Exchange (PKCE)?**

The addition of PKCE provides extra security that is needed when public clients request access tokens. This is because the client cannot securely store its secret. With PKCE, the calling application creates a secret called the Code Verifier, as well as a transformed version of the secret called the Code Challenge. Only the Code Challenge gets sent over HTTPS to request an Authorization Code, and this is all that can be intercepted. But without the Code Verifier, which does not get sent, an intercepted Authorization code by itself cannot be exchanged for a token.

**4. What is Implicit Flow with Form Post?**

It is an alternative to Authorization Code Flow intended for clients that can’t securely store secrets. Instead, web app requests and tokens run through the frontend without any backend calls or secrets. This way, secrets don’t need to be secured or maintained.

**5. What is Client Credentials Flow?**

This is for M2M apps where the system authenticates and authorizes another app rather than a user. The application uses Auth0 to get an access token, which it can use to make API calls and request data.

**6. What is Device Authorization Flow?**

This is for input-constrained devices and allows users to click a link to authorize the device itself, thereby enabling a better use experience for these kinds of devices. The process uses Auth0 to get an access token.

**7. What is Resource Owner Password Flow?**

Not generally recommended and only for highly-trusted applications when redirect-based flows can’t be used. This is less secure because user credentials are stored in the backend before being exchanged for an access token. Auth0 validates user credential and responds with an access token, which the application uses to make API calls to get user data.


## Code 401 - Advanced Software Development

### Bash Command Line Tutorial

ryanstutorials.net

Command line is preferable to GUI for e.g., data manipulation and file management.


**The Command Line**

One possible workflow is to use 3 tabs, one for work, a second for bringing up data, a third for viewing Manual pages

Shortcut for opening terminal on Mac: `command` + `space`

In terminal, typically first type a command followed by arguments. The first argument is also called an option and is prefixed by a dash.

`echo` is a command to display messages.

`echo $SHELL` displays the shell you’re using.

Use up and down arrow keys to traverse command history and avoid retyping.


**Basic Navigation**

`pwd` – prints working (current) directory

`ls` – lists contents of current directory

`ls[options][location]`\
Can run `ls` with options, such as `-l` (long list), which displays info about file types, permissions, and more.\
Can run ls with `/etc` argument to list the directory’s contents

When referring to a file or directory, you are implicitly referring to either a relative or absolute file path to the file/directory.
The file system in Linux is hierarchical. At the top is the root directory denoted by `/`.

Absolute file path begin with `/`, whereas relative paths do not.

`~` - shortcut to home directory\
`.` - refers to current directory\
`..` - refers to the current parent directory

`cd[location]` – change directory - switches to specified directory\
Use tab completion when typing paths

**More About Files**

Recall that in Linux, everything is a file under the hood.\
Linux is an extensionless system – it looks inside a file to determine its type.

`file[path]` - displays file type

Linux is case sensitive – applies to file names and command line options.

Since spaces are used to separate arguments, when referring to a directory name that contains a space, use single quotes around the name.\
Alternatively use `\` to escape the space.\
Tab completion automatically escapes spaces.

Files beginning with a `.` are hidden.\
Use `-a` option with `ls` to see hidden files and directories.

**Manual Pages**

The manual pages document every command, what it does, and what arguments and options it accepts. Square brackets indicate that an argument is optional.

To open the manual pages, run `man <command to look up>`\
To exit manual pages, run `q` for quit.\
To do a keyword search, run `man -k <search term>`

To search within a manual page, press `/` followed by your search query, and hit enter. Cycle through multiple instances by typing `n`.

Long-hand command line options (word written out) begin with two dashes `--`, whereas shorthand options begin with one dash `-`.\
You can chain multiple shorthand flags after a single dash (in rare exceptions, an option requires an argument so needs to be typed separately).


**File Manipulation**

It’s import to create a directory structure that keeps data organized.

`mkdir[options]<Directory>` - creates directory

mkdir options:\
`-p` - makes parent directories as needed\
`-v` - outputs explanation of what command is doing

`rmdir[options]<Directory>` - deletes a directory - by default, directory must be empty – if not empty, use `-r` (for recursive) to delete the full contents – consider using `-i` (interactive) with `-r` - then you’ll be prompted about each file to delete and given the option to cancel

`rmdir` support `-p` and `-v` options

`touch[options]<filename>` - makes blank file if filename doesn’t exist – often used this way – but also modifies access and modification times on an existing file

`cp[options]<source><destination>` - copies a file

`cp` options:\
`-r` copies recursively, so use this to copy directories

`mv[options]<source><destination>` - moves files, and can move directories with the `-r` option – can also rename a file by specifying its current destination as the destination

`rm[options]<file>` - deletes a file

There is no ‘undo’ feature, so delete carefully


**Cheat Sheet**

https://ryanstutorials.net/linuxtutorial/cheatsheet.php


## SQL Bolt Tutorial

Completion Screenshots:

<img width="1155" alt="Screen Shot 2022-09-19 at 8 21 33 AM" src="https://user-images.githubusercontent.com/37053081/191127620-836632db-2841-4f40-9360-97be23bfff84.png">

<img width="1157" alt="Screen Shot 2022-09-19 at 8 35 50 AM" src="https://user-images.githubusercontent.com/37053081/191127650-54d1e8a2-d774-4ff3-969c-c1203518ef10.png">

<img width="1152" alt="Screen Shot 2022-09-19 at 8 55 43 AM" src="https://user-images.githubusercontent.com/37053081/191127671-ecc8c8a0-4320-4822-a9e3-fcc14b270916.png">

<img width="1155" alt="Screen Shot 2022-09-19 at 9 30 11 AM" src="https://user-images.githubusercontent.com/37053081/191127698-e427be24-5373-4fb9-83d6-53359d821d13.png">

<img width="1161" alt="Screen Shot 2022-09-19 at 9 39 20 AM" src="https://user-images.githubusercontent.com/37053081/191127732-5cf3c400-8041-4d82-a6fe-bf1247f67781.png">

<img width="1153" alt="Screen Shot 2022-09-19 at 1 53 01 PM" src="https://user-images.githubusercontent.com/37053081/191127762-bc26bd3f-d6ff-4dd0-9525-1ea106be9fc1.png">

<img width="1156" alt="Screen Shot 2022-09-19 at 2 17 35 PM" src="https://user-images.githubusercontent.com/37053081/191127791-3b92b26f-5479-43b7-b7f8-e2532a2f21df.png">

<img width="1159" alt="Screen Shot 2022-09-19 at 2 25 03 PM" src="https://user-images.githubusercontent.com/37053081/191127809-11dab460-00c6-4e1e-b902-fd4c94f2f032.png">

<img width="1162" alt="Screen Shot 2022-09-19 at 2 28 41 PM" src="https://user-images.githubusercontent.com/37053081/191127843-c2762561-3ac7-49b1-b8b2-8708a9848427.png">

<img width="1154" alt="Screen Shot 2022-09-19 at 2 43 55 PM" src="https://user-images.githubusercontent.com/37053081/191127862-6f796a6d-f74e-4a06-b846-36085157410f.png">

<img width="1158" alt="Screen Shot 2022-09-19 at 2 55 38 PM" src="https://user-images.githubusercontent.com/37053081/191127922-a6238d81-e9d5-4ec3-b26d-4af7464f0f1d.png">

<img width="1161" alt="Screen Shot 2022-09-19 at 2 58 07 PM" src="https://user-images.githubusercontent.com/37053081/191127949-f8afc87d-b98d-4435-92a1-79a896d834c1.png">


Summarize your understanding of relational databases and SQL:

https://sqlbolt.com/

**Lesson 1: SELECT Queries**

SQL (Structured Query Language) is a language that lets you query relational databases. Relational databases are composed of a collection of tables that share relationships. SQL can be used to query databases, but also to change their tables/schemas and create new ones.

“You can think of a table in SQL as a type of an entity (ie. Dogs), and each row in that table as a specific instance of that type (ie. A pug, a beagle, a different colored pug, etc). This means that the columns would then represent the common properties shared by all instances of that entity (ie. Color of fur, length of tail, etc).”

To make a basic query, use SELECT. Specify the data you want, where it’s located, and optionally how you want to transform the data you get back.

Select query for specific columns:\
`SELECT “column”, “another_column”, …`\
`FROM mytable;`

Select query for all columns:\
` SELECT * FROM mytable;`


**Lesson 2: Queries with Constraints (Part 1)**

Note: Capitalization of SQL keywords is a convention, not strictly required – but it distinguishes commands from column names.

For large datasets, it’s often necessary to filter results (also for speed). Use WHERE for this.
The WHERE clause “is applied to each row of data by checking specific column values to determine whether it should be included in the results or not.”

`SELECT column, another_column, …`\
`FROM mytable`\
`WHERE condition`\
    `AND/OR another_condition`\
    `AND/OR …;`

The following logical operators can be used in WHERE clauses:

=, !=, <, <=, >, >=, BETWEEN…AND… (specifies range of values, inclusive), NOT BETWEEN…AND…, IN (…) (Number exists in a list), NOT IN(…) 


**Lesson 3: Queries with Constraints (Part 2)**

“When writing WHERE clauses with columns containing text data, SQL supports a number of useful operators to do things like case-insensitive string comparison and wildcard pattern matching.”

Strings must be in quotes.

Use libraries like Apache Lucene or Sphinx for full-text searches.

`=` - case-sensitive string comparison\
`!=` or `<>` - case-sensitive exact string inequality comparison\
`LIKE` - case-insensitive exact string comparison\
`NOT LIKE` - case-insensitive exact string inequality comparison\
`%` - used with LIKE/NOT LIKE to match sequence of 0 or more characters\
`-` - used with LIKE/NOT LIKE to match 1 character\
`IN(…)` - string in a list\
`NOT IN (…)` - string not in a list


**Lesson 4: Filtering and Sorting Query Results**

Use DISTINCT to discard rows with duplicate column values (can be further refined with GROUP BY).

Select query with unique results:\
`SELECT DISTINCT column, another_column, …`\
`FROM mytable`\
`WHERE condition(s);`

Can get results in sorted order using ORDER BY based on a particular column.\
“When an ORDER BY clause is specified, each row is sorted alpha-numerically based on the specified column's value. In some databases, you can also specify a collation to better sort data containing international text.”

Select query with ordered results:\
`SELECT column, another_column, …`\
`FROM mytable`\
`WHERE condition(s)`\
`ORDER BY column ASC/DESC;`

Use LIMIT to limit number of results, and OFFSET to specify which rows:

Select query with limited rows:\
`SELECT column, another_column, …`\
`FROM mytable`\
`WHERE condition(s)`\
`ORDER BY column ASC/DESC`\
`LIMIT num_limit OFFSET num_offset;`


**Lesson 5:**

Review

**Lesson 6: Multi-table Queries with JOINs**

"Up to now, we've been working with a single table, but entity data in the real world is often broken down into pieces and stored across multiple orthogonal tables using a process known as normalization."\
Normalization reduces duplicate data and allows additions to different parts of the database, but the tradeoff is more complex queries, since you need to specify more precisely where to look.

When info about a particular entity is distributed across multiple tables, it needs a primary key to uniquely identify it.\
“One common primary key type is an auto-incrementing integer (because they are space efficient), but it can also be a string, hashed value, so long as it is unique.”

JOIN commands can combine rows from different tables according to the primary key. There are several JOIN commands.

“The INNER JOIN is a process that matches rows from the first table and the second table which have the same key (as defined by the ON constraint) to create a result row with the combined columns from both tables.”

By default, JOIN refers to INNER JOIN.

Select query with INNER JOIN on multiple tables:\
`SELECT column, another_table_column, …`\
`FROM mytable`\
`INNER JOIN another_table`\
`ON mytable.id = another_table.id`\
`WHERE condition(s)`\
`ORDER BY column, … ASC/DESC`\
`LIMIT num_limit OFFSET num_offset;`


**Lesson 13: Inserting Rows**

SQL schemas describe the structure of each table and the datatypes of each column. This consistency makes the database efficient.

INSERT adds new data.

Insert statement with values for all columns:\
`INSERT INTO mytable`\
`VALUES (value_or_expr, another_value_or_expr, …),`\
       `(value_or_expr_2, another_value_or_expr_2, …),`\
       `…;`

“In some cases, if you have incomplete data and the table contains columns that support default values, you can insert rows with only the columns of data you have by specifying them explicitly.”

Insert statement with specific columns:\
`INSERT INTO mytable`\
`(column, another_column, …)`\
`VALUES (value_or_expr, another_value_or_expr, …),`\
      `(value_or_expr_2, another_value_or_expr_2, …),`\
      `…;`

Inserting columns with default values makes them forward compatible, since no hard-coded INSERT statements will need to be updated.

You can use math and string operations on the values you insert:

Example Insert statement with expressions:\
`INSERT INTO boxoffice`\
`(movie_id, rating, sales_in_millions)`\
`VALUES (1, 9.9, 283742034 / 1000000);`


**Lesson 14: Updating Rows**
Any data you update must match column data type in schema.

Update statement with values:\
`UPDATE mytable`\
`SET column = value_or_expr,`\
`other_column = another_value_or_expr,`\
`…`\
`WHERE condition`;

Note: If you leave out the WHERE clause, the update will be applied to all rows, so be careful when updating.
“One helpful tip is to always write the constraint first and test it in a SELECT query to make sure you are updating the right rows, and only then writing the column/value pairs to update.”


**Lesson 15: Deleting Rows**

Delete statement with condition:\
`DELETE FROM mytable`\
`WHERE condition;`

If you leave out the WHERE clause, all rows will be deleted (you can clear the whole table this way). Like with UPDATE, test with SELECT before running DELETE.


**Lesson 16: Creating Tables**

For new entities/relationships, make a new table using CREATE TABLE.

Create table statement w/ optional table constraint and default value:\
`CREATE TABLE IF NOT EXISTS mytable (`\
`column DataType TableConstraint DEFAULT default_value,`\
`another_column DataType TableConstraint DEFAULT default_value,`\
`…`\
`);`

The table is defined by its schema, which defines the columns and associated datatypes. Table constraints and values are optional.

“If there already exists a table with the same name, the SQL implementation will usually throw an error, so to suppress the error and skip creating a table if one exists, you can use the IF NOT EXISTS clause.”

Some possible datatypes: 

INTEGER, BOOLEAN, FLOAT, DOUBLE, REAL, CHARACTER, VARCHAR, TEXT, DATE, DATETIME, BLOB

Table Constraints:

PRIMARY KEY – each value in column is unique, so can identify a row\
AUTOINCREMENT – automatically increments with insertions\
UNIQUE – column values must be unique, but doesn’t have to be a key\
NOT NULL – can’t be null\
CHECK – lets you run expressions to check validity of values\
FOREIGN KEY – checks that values correspond to values in another table\

Example Schema:\
`CREATE TABLE movies (`\
    `id INTEGER PRIMARY KEY,`\
    `title TEXT,`\
    `director TEXT,`\
    `year INTEGER,`\ 
    `length_minutes INTEGER`\
    `);`


**Lesson 17: Altering Tables**

ALTER TABLE lets you add, remove, or modify columns and table constraints.

When altering a column, you need to specify the datatype and any potential constraints and default values, which get applied to both existing and new rows.\
“In some databases like MySQL, you can even specify where to insert the new column using the FIRST or AFTER clauses, though this is not a standard feature.”

Altering table to add new column(s):\
`ALTER TABLE mytable`\
`ADD column DataType OptionalTableConstraint`\
`DEFAULT default_value;`

Altering table to remove column(s):\
`ALTER TABLE mytable`\
`DROP column_to_be_deleted;`

Note: SQLite doesn’t support DROP – instead need to create new table and migrate data.

Renaming Table:\
`ALTER TABLE mytable`\
`RENAME TO new_table_name;`

Each database implementation (e.g. MySQL, Postgres, SQLite, Microsoft SQL Server) supports different methods for altering tables, so check docs.


**Lesson 18: Dropping Tables**

Delete table and schema:\
`DROP TABLE IF EXISTS mytable;`

If this table depends on another table (e.g., with a FOREIGN KEY), need to first update or remove dependent tables.


## Prep Your Mindset

**Upgrade your technical skills with deliberate practice**

https://web.archive.org/web/20160616225417/http://www.happybearsoftware.com/upgrade-your-technical-skills-with-deliberate-practice

For continuous improvement, seek out “Deliberate Practice”:

Key characteristics of “Deliberate Practice”:

> Pushes you just outside your comfort zone\
> Repeated often\
> Feedback on results is continuously available\
> It's highly demanding mentally\
> It's difficult\
> It requires good goals

Recommendations for exercises that satisfy above criteria for intermediate/senior developers:

The Matasano Crypto Challenges
https://web.archive.org/web/20160620111206/http://cryptopals.com/ \
“They relentlessly pummel you with problems that require hard, focused thinking and fiddly solutions. The feedback is continual: your solutions either break crypto and produce the desired results or they don't.”

Rosalind
https://web.archive.org/web/20160607102654/http://rosalind.info/about/ \
“Specifically crafted challenges designed to help you learn a technical specialty (bioinformatics) by applying your existing skills to real world problems.”


**Carol Dweck on Growth Mindset**

https://www.ted.com/talks/carol_dweck_the_power_of_believing_that_you_can_improve?language=en

Understanding that abilities can be developed characterizes a growth mindset.

A way to engage this mindset is thinking “not yet” when encountering a setback, rather than viewing it as a permanent failure.
Praise process and effort in people who are learning.  This encourages better engagement and perseverance.
Growth mindset changes one’s relationship to effort and difficulty – these can be viewed positively when recognized as part of the learning process.
Encouraging growth mindset leads to better learning outcomes.

**Angela Lee Duckworth on Grit**

https://www.ted.com/talks/angela_lee_duckworth_grit_the_power_of_passion_and_perseverance

Motivation and psychology are crucial in learning.
Success in various contexts is determined more by grit than IQ.
Grit is passion and perseverance for long-term goals.
Grittier students are more likely to succeed – and grit is a better predictor of success than many conventional metrics.
Talent does not equal grit, and may even be inversely related. But growth mindset cultivates grit.


**Alain de Botton on Redefining Success**

https://www.ted.com/talks/alain_de_botton_a_kinder_gentler_philosophy_of_success

Thesis: While meritocracy is a laudable goal, we should recognize that it cannot be fully achieved, and believing that things are more meritocratic than they are results in unfair and negative judgements of people perceived as less successful. These views also cause people greater stress and anxiety, since they take perceived failures more personally and fear judgement. Visions of success should admit tradeoffs – you can’t do everything. Make sure ideas of success are truly your own.


## 401 Prework - Prep: Engineering Readings

**1. What’s the one thing I bring to this career (and a potential employer) that nobody else can?**

I’m highly coachable and curious, and I make every effort to communicate clearly and constantly improve. 

**2. What are 3 things I’ll start doing to “un-stick” myself whenever I get stuck on tough piece of code, logic, or feature?**

- Try to break the problem down into subproblems
- Cultivate curiosity about the problem, try to understand what’s going on, do research
- Use a debugger and step through the problem piece by piece


## 401 Prework - Data Structures and Algorithms

**1. What is 1 of the more important things you should consider when deciding which data structure is best suited to solve a particular problem?**

The efficiency of a data structure for a particular use case. Big O analysis can be used to determine the time and space complexity of different operations for a particular data structure, and depending on which operations are most important/common for a specific application, as well as the number of possible inputs, this is a good way to choose a data structure optimized for your use case.


**2. How can we ensure that we’ll avoid an infinite recursive call stack?**

Specify a base case, which stops the recursive calls. Unlike the recursive case, the base case does not make any additional recursive calls, and so the function terminates when it hits the base case.


# 401 Readings

## Class 1 Readings - Big O

**A beginner's guide to Big O Notation**

https://rob-bell.net/2009/06/a-beginners-guide-to-big-o-notation

“Big O specifically describes the worst-case scenario.”

O(1) – constant time – executes in same time/space regardless of input size

O(N) – linear time – grows proportionally to input size\
Example: a for loop that looks at every element of the input – note: since Big O describes the worst case, assumes the loop does not terminate early

O(N²) – grows proportionally to the square of the input size\
Example: a nested loop – note: each additional nested loop increments the exponent by one 

O(2^N) – exponential growth – in this case where the base is 2, the growth rate doubles for every additional input\
Example: recursive algorithm for calculating Fibonacci sequence

O(log N) – logarithmic time – growth curve levels off – doubling the size of the inputs increments the time by one unit, so this is very efficient for large data sets\
Example: binary search


## Class 2 Readings

**In Tests We Trust — TDD with Python** 

https://code.likeagirl.io/in-tests-we-trust-tdd-with-python-af69f47e6932

Test-Driven Development (TDD) is a strategy in which developers think and write in tests first.  Break down problems, and think about tests for functions, and what outputs should be returned for different inputs that might occur.

3-part TDD cycle: write a unit test and make it fail, write code to make the test pass, refactor code. This cycle should be used for each new feature. This aids software design and makes code more reliable.

Test names should be descriptive and considered part of documentation. Test name should be based on what is being tested, and test file name should be based on module name. The test folder should be separate from production code.

AAA: Arrange, Act, Assert is a structure for testing order, which corresponds to organizing the input, executing the test, and checking the output.

pytest is a python testing library.

**If name equals main**

https://www.geeksforgeeks.org/what-does-the-if-__name__-__main__-do/

The python interpreter defines some global environment variables when executing code. One such variable is `__name__`, which gets set to the value of  `__main__` if a source file is being run as the main program. But if a file is imported from another module and run, then `__name__` will get set to the module's name (not `__main__`).
You can then use the expression `if__name__==“__main__”` to only run code that should be run as a script, vs. code that is imported from a module.

**Recursion**

https://www.geeksforgeeks.org/introduction-to-recursion-data-structure-and-algorithm-tutorials/

Recursion is when a function calls itself, and it’s often used to break a problem into subproblems, and solve each of the smaller subproblems. A base case should be provided to eventually terminate the recursive calls. 

Recursion uses more memory than iteration because each function call is added to the call stack.

Direct recursion is when a function calls itself. Indirect recursion is when a function calls another function, which then results in another call to the original function.

Tail recursion is when the final statement of a function is recursive, and so after the recursive calls finish, the function terminates.

Any recursive program can be written iteratively and vice versa. For some problems that are inherently recursive (e.g., tree traversals), recursive code is easier to read and understand. But recursion is less efficient (both in space and time).


## Reading: Class 3: FileIO & Exceptions

**Read & Write Files in Python**

https://realpython.com/read-write-files-python/

Files typically contain a header (with metadata), data, and End of File (EOF) (a character indicating the end of the file)

A file path is required to access a file. Folders are separated by `/` on Unix and `\` on Windows.\
`..` goes up one directory, and you can chain these as well

Windows signals line endings with `\r\n` whereas Unix uses just `\n`. This can cause issues when processing a file created using a different OS.

Two most common character encodings: ASCII and Unicode\
Need to use correct character encoding when parsing a file

To work with a file, you first need to open it. Use the built-in `open()` method, which takes the file path (as a string) as a parameter.
You must always close a file when you’re done with it (otherwise can get unwanted behavior and resource leaks).

2 ways to close a file:

- Use a `try/finally` block:

```
reader = open(‘filepath.txt’)
try:
        #Code
finally:
        reader.close()
```

- Use a `with` statement:

```
with open(‘filepath.txt’) as reader:
        #Code
```

`with` automatically closes a file after completing the code block (even if there’s an error).  It is cleaner code and offers better error handling.

Second parameter for `open()` specifies the mode – e.g., ‘r’ for read, ‘w’ for write, ‘rb’ for read binary, ‘wb’ for write binary.

There are 3 kinds of file objects:
- Text files
- Buffered binary files
- Raw binary files

These are defined in the io module.

Text files are most common – `open()` will return a TextIOWrapper file object, which is the default file object returned by open.

A buffered binary file is for reading and writing binary files (use ‘rb’ and ‘wb’ modes). `open()` returns a BufferedReader or BufferedWriter file object.

Raw files are not commonly used and are a “low-level building-block for binary and text streams.” `open()` returns a FileIO file object.

Reading Files:

You can call various reading and writing methods on file objects.

Read methods:\
`.read(size=-1)`\
`.readline(size=-1)`\
`.readlines()` (returns file lines as a list)

Size of -1 reads whole thing (default).

Reading an entire file:

```
with open(‘filepath.txt’, ‘r’) as reader:
        #Read & print entire file
        print(reader.read())
```

A common pattern is to iterate over each line of a file and do something with it. Example:

```
with open (‘filepath.txt’, ‘r’) as reader:
        # Read and print the entire file line by line
        line = reader.readline()
        while line != ‘‘: # The Eof char is an empty string
                print(line, end=’‘)
                line = reader.readline()
```

Alternatively, can use `readlines()` (which returns all lines in a list) as follows:

```
with open (‘filepath.txt’, ‘r’) as reader:
        for line in reader.readlines():
                print(line, end=’’)
```

**Simplest approach (use this one) – just iterate over the file object itself:

```
with open(‘filepath.txt’, ‘r’) as reader:
        for line in reader:
                print(line, end=‘’)
```

The `end=‘’` argument to `print()` prevents addition of an extra newline character so that only the file contents is printed

Writing Files:

Write methods:\
`write(string)`\
`writelines(sequence)`

Note: writelines does not append line endings, you need to add these

Write example:

```
with open(‘filepath.txt’, ‘w’) as writer:
        for item in list:
                writer.write(item)
```

To add to an existing file, use append mode by passing ‘a’ as second parameter to `open()`.

`__file__` returns the file path relative to where the script was called. For the full system path, run `os.getcwd()`

Working with 2 files:\
When reading from one file and writing to another, can open both in a single `with` expression, and then perform read and write operations like so:

```
with open(‘filepath.txt’, ‘r’) as reader, open(‘filepath.txt’, ‘w’) as writer:
        text = reader.readlines()
        writer.writelines(text)
```

“There may come a time when you’ll need finer control of the file object by placing it inside a custom class. When you do this, the `with` statement can no longer be used unless you add a few magic methods:` __enter__` and `__exit__`. By adding these, you’ll have created what’s called a context manager.”

Custom class template:

```
class my_file_reader():
        def __init__(slef, file_path):
                self.__path = file_path
                self.__file_object = None

        def __enter__(self):
                self.__file_object = open(self.__path)
                return self

        def __exit__(self, type, val, tb):
                self.__file_object.close()
```

This custom class is a context manager and can be used like the open() method:

```
with my_file_reader(‘filepath.txt’) as reader:
        #code
```

(See article for more complex example with custom iterator)

There are many python modules for common file handling tasks – use them (see article for examples).

**Exceptions in Python**

https://realpython.com/python-exceptions/

An exception error is syntactically correct code that nonetheless causes an error. Python has built-in exceptions, and you can also create custom exceptions.

If a python program hits an unhandled error, it will terminate.

Use `raise Exception(‘text’)` to specify a custom condition for throwing an error

Alternatively, use `assert(<condition>), “Custom error message”`, which throws an AssertionError exception if the condition is false and prints the error message.

Raising an exception and throwing an AssertionError will both halt the program.

An alterantive for for error handling that does not halt the program is to use a `try:` and `except:` block. Python runs the try code, and if it fails, it runs the except code.

Handling exceptions prevents your program from crashing when it hits an error. If you want to specify what error occurred, you need to write code to handle specific error types. For example:

```
try:
    linux_interaction()
except AssertionError as error:
    print(error)
    print(‘linux_interaction() failed’)
```

Output:\
Function can only run on Linux systems.\
linux_interaction() failed

The first line of output is the AssertionError message (this was a custom error message).

See Python docs for built-in exceptions. For example, FileNotFoundError is a built-in exception. Example:

```
try:
    with open(‘file.log’) as file:
        read_data = file.read()
except FileNotFoundError as fnf_error:
    print(fnf_error)
```

You can call multiple functions in a try block, but the block will stop executing as soon as it encounters an error.

You can append an `else` block to a try/except block, which executes if there are no exceptions.

The else block can also contain another try/catch block.

`finally` block always runs after a try/catch or try/catch/else block, regardless of whether an exception occurred – this allows you to “clean up” afterwards.


## Readings Class 04: Classes/Objects/Recursion

**Classes and Objects**

https://www.learnpython.org/en/Classes_and_Objects

Define a class with the `class` keyword. Inside a class, you can declare variables and functions. To create a new instance of the class, call the class as you would a function, and assign the output to a variable. That variable now holds an instance of the class.

To access variables in the class, use the dot operator.  To call class methods, use the dot operator and call the function with parentheses.  Example:

```
class MyClass:
	variable = “value”
	
	def function(self):
		print(“This is a function in a class”)

my_object = MyClass()
my_object.variable
my_object.function()
```

`__init__()` is a special function that can be declared inside of a class and is used for setting variables. It gets called when the class is being initiated.

```
class MyClass:
	def __init__(self, number):
		self.number = number
```

**Thinking Recursively**

https://realpython.com/python-thinking-recursively/

Recursive functions call themselves until they reach a base case, and each call adds a function call to the call stack. So, “each recursive call has its own execution context.” As a result, there are two ways to maintain state inside recursive functions.
- “Thread the state through each recursive call so that the current state is part of the current call’s execution context.”
- Save state in a global variable

To implement the former, pass state to each function call as an argument.  To implement the latter, define a state variable outside of the recursive function (global scope).  The former is preferred.

“A data structure is recursive if it can be defined in terms of a smaller version of itself.” Examples: list, set, tree, dictionary.

Recursive data structures are easily implemented by recursive functions.

Recursive functions can be inefficient – to improve efficiency, implement caching to avoid re-calculating results.  One option is Python’s `@lru_cache` decorator.\
“Python doesn’t have support for tail-call elimination. As a result, you can cause a stack overflow if you end up using more stack frames than the default call stack depth.”

“Python’s mutable data structures don’t support structural sharing, so treating them like immutable data structures is going to negatively affect your space and garbage collection.”

**Pytest Fixtures and Coverage**

https://www.linuxjournal.com/content/python-testing-pytest-fixtures-and-coverage

Similar tests can be grouped together, and pytest handles them as “parameterized tests”.

When certain objects/data need to be available to all tests, use “fixtures”.  Define fixtures using the `@pytest.fixture` decorator.  This is a better option than defining global variables in your test file.

A fixture “provides your test with the appropriate object at the right time.”

“Fixtures are used differently from global variables.”

You can include fixtures as parameters to tests and access the fixture inside the test function. Don’t use parentheses when invoking a fixture, even though it is technically a function. And because it’s a function, it can perform calculations, and so has extra functionality compared to a global variable holding some data.

You can set a fixture’s scope, which affects when and how often it gets run. Setting the scope to `module` makes the fixture available to all tests but runs it only once. To set the scope parameter, pass it (and its value) as an argument to the fixture decorator.

Fixtures are a different design choice for testing compared to a “traditional setup/teardown system.” And yet, there is a setup/teardown aspect to fixtures – if a fixture uses `yield` instead of `return`, that signals to pytest that subsequent code is for teardown. Module scope prevents teardown until all test functions have run.

Percent coverage is a measure of how many paths through your functions were tested by a test suite. Note that 100% coverage does not guarantee bug-free code.

As a software project grows in complexity, it’s harder to tell by visual inspection alone if all code was tested. To address this, pytest has a package called pytest-cov, which you invoke with the `--cov` option. If you run just the `--cov` option, coverage reports will be generated for all libraries. To choose which programs should generate coverage reports, run `pytest –cov=my_program`, and specify to which directory the coverage report should be written.

The coverage report needs to be converted to human readable form. To convert to html, run `coverage html`. If you converted to html, to view the report, open the directory’s index.htm file in the browser.


## Reading 05: Explain Linked Lists

A linked list is a data structure. It holds values, and its format is very similar to a list/array. Each value is stored inside one compartment of the data structure. So you can think of a linked list as a series of boxes, each of which holds one value that you wish to store.

Recall that a regular list/array also has these “boxes” that store your values. But you also need a way to access a particular box, in order to retrieve the value stored there. How do you access a particular box? For a regular list, you use an index. Each box is associated with an index, and the indices are numbered from 0 up to the length of the list minus one. So to retrieve a value, you ask the list to return the value at an index location that you provide. In Python, that looks something like this: my_list[index]

A linked list works very similarly to a regular list, except you don’t use an integer index to access the box you want. Instead, you create each box that stores one of your values. And when you create that box, you also give it a reference to the next box in the series. So the boxes have an order. It’s as if you’re lining them up, one next to the other, and each box is pointing to the next box in the series:

[ ] -> [ ] -> [ ] -> [ ] -> [ ]

Notice that the two boxes on the ends are a bit different than the others. The first box doesn’t have an arrow pointing to it, and the last box doesn’t have an arrow pointing away from it.

The first box is called the head. This is the starting point in the linked list. And even though no other box points to it, this box has the same features as the other boxes. It contains a value, and it contains a reference to the next box. So we can create it the same way we would create any other box – with a value and a reference.

But the last box in the series is different. It doesn’t have an arrow pointing away from it. But we can still create this box with a value and a reference. We just set the reference to None. And this None reference is important, because it signals that we’ve reached the end of our list.

There’s some specific terminology associated with linked lists. Each box is referred to as a node. Recall that a node contains a value that we want to store, and a reference to the next node. The first node is the head, as we’ve seen. And the last node is the tail, and contains a None reference, signaling the end of the linked list.

How do we access a particular node to retrieve a value stored there? Since each node contains a reference to only one other node, we need to start at the head, and visit each node by following all of the references (arrows), until we get to the node we’re looking for. Moving through the list one value at a time is called traversing the linked list.

There are a few operations that we’ll want to be able to perform on a linked list, in order to make use of it in our applications. We’ll want to be able to traverse the linked list (move from one node to the next, from start to finish). We’ll also want to be able to add nodes to it, and delete nodes from it.

To traverse the list, start at the head, and while the current reference does not equal None, follow the reference to the next node. This algorithm allows you to visit each node and stop when you reach the end.

To add a node to the list, we first need to know where the addition should take place. Adding a new head to the list is easy, and can be done in constant time, since we always start by looking at the head of a linked list. Simply create a node whose reference points to the current head node. Note that the reference to the linked list itself (which points to the head node) will also need to be updated to point to the new node, which becomes the new head.

To add a node somewhere else, we first need to know where. We need to be a given a node that already exists in the linked list, and then we can traverse to the node right before it. We will be able to identify the node before the target node because its reference will point to the target node. Then we can create a new node whose reference is the same as the current node that points to the target node. The current node reference needs to then be updated to point to the newly created node.

So by simply reassigning references/pointers, it’s easy to add nodes. The downside is that the full list needs to be traversed up until the target node is found. This can take a long time if the target node is towards the end of a long linked list.

Deleting a node works similarly. Traverse to the node to be deleted and reassign pointers to exclude the node to be deleted.

This description was for a singly linked list. The references all flow in one direction, and so the linked list can only be traversed from start to end. In order to be able to travel in both directions, a doubly linked list can be created, where each node has pointers to both its neighbors. As a result, more memory is required, but the data structure can be traversed in both directions.


## Reading 06: Ten Thousand Game 1

**How to use the Random Module in Python**

https://www.pythonforbeginners.com/random/how-to-use-the-random-module-in-python

Python's Random module can be used to generate random numbers and has many useful methods.

`import random`

Methods:

`random.randint(start value, end value)` - outputs a random number between start and end value\
`random.random()` - outputs a random number between 0 and 1\
`random.choice([‘red’, ‘black’, ‘green’])` - outputs a random selection from items in custom list\
`random.shuffle(list)` - randomly shuffles elements of a list in place\
`random.randrange(start, stop, step)` - outputs a random number from specified range with step size

**What is Risk Analysis**

https://www.edureka.co/blog/risk-analysis-in-software-testing/

Risk analysis involves identifying and writing tests for the highest risk outcomes associated with a software application. Potential risks should be analyzed in advance and a testing plan should be developed. Risk should be categorized as high, medium, or low.

Risks can occur in the following areas:\
“Use of new hardware, use of new technology, use of new automation tool, the sequence of code, availability of test resources for the application.”

Some risks are unavoidable, e.g., defect leakage, client expectations.

Risk analysis extends beyond just software and considers business risks as well.

Risk assessment should consider the cause, effect, and likelihood of a particular risk.

3 steps for performing Risk Analysis:
- Identify risks
- Analyze impact
- Measure identified risks

**Test Coverage**

https://martinfowler.com/bliki/TestCoverage.html

High test coverage is important but not sufficient – quality of tests is important and can be overlooked if the focus is just on coverage and hitting certain coverage requirements.

Author argues that thoughtful testing tends to result in 80 to 90% coverage rather than 100% coverage – the latter is often the result of someone writing for coverage goals rather than thorough testing.

But coverage below 50% is also a bad sign.

You are testing sufficiently if the following are true:\
“You rarely get bugs that escape into production, and you are rarely hesitant to change some code for fear it will cause production bugs.”

It’s also possible to over test – you shouldn’t have redundant tests.

“If it seems like a simple change to code causes excessively long changes to tests, that's a sign that there's a problem with the tests. This may not be so much that you are testing too many things, but that you have duplication in your tests.”

Note that if tests themselves are slow but necessary, can move them to a later stage of the deployment pipeline, or run them only occasionally. This can help balance build time vs. test confidence.


## Reading 7: Python Scope

Scope rules determine the visibility of variables (where you can access them). Python scope is governed by the LEGB rule: Local, Enclosing, Global, Built-in.

Scope is used to avoid name collisions and unpredictable behavior. Broadly, there is global scope and local scope. Global variables can be accessed anywhere in the code, but this can make debugging and maintaining complex programs very difficult. Local scope narrows the context in which variables can be used.

When a variable name can be accessed, it is in scope, otherwise it is out of scope.

Python is dynamically-typed, so variables are accessible as soon as they are assigned. Functions and classes are accessible once the `def` and `class` keywords are used. Modules are accessible once imported.

The location of this assignment determines the scope.

Scope vs. Namespaces:

From Python documentation:\
“A namespace is a mapping from names to objects.”
“A scope is a textual region of a Python program where a namespace is directly accessible.”\
https://medium.com/swlh/mastering-python-namespaces-and-scopes-7eba67aa3094#:~:text=A%20namespace%20is%20a%20mapping,a%20namespace%20is%20directly%20accessible. 

Python scope is held in dictionaries called namespaces that map names to objects. These are stored in the special attribute `.__dict__`.

“.__dict__ is a special dictionary that Python uses to implement namespaces”

`.__dict__` attributes exist at different levels, e.g. at the module level. For example, to view the sys module `.__dict__` attribute, import the sys module and call `sys.__dict__.keys()` to see the namespace variables of the sys module – this represents the sys module’s scope.

When the Python interpreter encounters a variable name, it searches sequentially through the LEGB scopes to determine if the variable exists, and otherwise throws an error. The interpreter first searches the *local scope* (function scope) within the current function, then the *enclosing scope*, which exists for nested functions, then the *global scope*, which is at the module level, and finally the *built-in scope*, which is a special scope that exists when running a script or interactive session.

Calling a function creates a new local scope. When the function returns, its local scope is destroyed.

Trying to access a variable name whose scope was destroyed results in a NameError.

Local scope is why different functions can use the same names for variables without conflicts.

`.__code__` lets you examine the variables of a function.

Enclosing scope exists for nested functions. Variables in the outer function can be accessed by the inner function(s) and are called nonlocal names. But note, variables in the outer function must be declared before the inner function is called in order for the inner function to have access to them. Additionally, inner functions cannot reassign variables in the enclosing scope unless they are declared as nonlocal inside the inner function.

When running a program, the main script becomes the `__main__` module (holds program’s execution), and its namespace is the global scope. 

When you run a script, the file that is the entry point becomes `__main__`, and the global scope is the `__main__` module. You can run `dir()` to see the variable names in the current global scope.

There is only ever one global scope at a time.

You can declare global variables inside functions using the `global` keyword.

There’s an issue when trying to update a global variable from within a function. When you try to reassign the variable, it looks like a new variable declaration, and Python creates a local version of the variable that shadows the global variable. As a result, you can’t access and change the global variable. To overcome this, you can use the `global` keyword. But note that it is bad practice to modify global variables, and this should be avoided when possible.

“The built-in scope is a special Python scope that’s implemented as a standard library module named builtins in Python 3.x. All of Python’s built-in objects live in this module.”\
This scope contains more than 150 names.

If you accidentally rename a built-in, either restart your session or run `del <name>`.

Recap of default Python scope rules:
- You can reference global names locally, but can’t modify them locally.
- You can access local names only inside the local scope.
- You can access nonlocal names inside a nested function, but can’t modify them locally.

However, these can be modified using the `global` and `nonlocal` keywords in order to modify variables in a higher scope that you would not ordinarily be able to modify locally.

For example, to update a global counter variable from inside a function, use the following:
```
global counter
counter = counter + 1
```

Note: the use of `global` is considered bad practice. Here is a better way to update a global counter:
```
global_counter = 0
def update_counter(counter):
	return counter + 1

global_counter = update_counter(global_counter)
```

The `nonlocal` keyword works like the `global` keyword, but for inner functions modifying nonlocal variables. One difference is that while `global` can be used to create new global variables, `nonlocal` can only be used with variables that already exist.

Closures:

“Closures are a special use case of the enclosing Python scope. When you handle a nested function as data, the statements that make up that function are packaged together with the environment in which they execute. The resulting object is known as a closure. A closure is an inner or nested function that carries information about its enclosing scope, even though this scope has completed its execution.”

This kind of function is sometimes called a factory function or a closure factory since it “builds and returns closures (an inner function), rather than classes or instances.”

“Closures provide a way to retain state information between function calls. This can be useful when you want to write code based on the concept of lazy or delayed evaluation.”

Example of a closure to “retain state information between function calls” – essentially, a function is returning another function with certain parameters initialized:

```
def power_factory(exp):
	def power(base):
		return base ** exp
	return power

square = power_factory(2)
square(10)
# Outputs 100

cube = power_factory(3)
cube(10)
# Outputs 1000
```

In this example, `exp` is called a *free variable*. Free variables are not defined in the code block where they are used, and they are “the mechanism that closures use to retain state information between calls.”

Another use case for closures is continuous data collection – you can use a closure factory that keeps track of the previously entered data and then performs ongoing calculations as new data becomes available:

```
def mean():
	sample = []
	def _mean(number):
		sample.append(number)
		return sum(sample) / len(sample)
	return _mean
```

“The closure that you create in the above code remembers the state information of `sample` between calls of `current_mean`. This way, you can solve the problem in an elegant Pythonic way.” But note that if there’s too much data, memory can become an issue. In this example, you can address this by storing nonlocal variables in place of the full data sample (see text for code example).

More on Scopes and Closures:
https://realpython.com/courses/exploring-scopes-and-closures-in-python/

Closures can also be created using the built-in `functools` module. You can pass a function into the `functools partial` function, and it creates a closure function.

If you write several modules, you’ll need to import them into your __main__ module in order for their variables to be available in the global scope.

Unusual Python Scopes:\
There are some instances where scope doesn’t seem to follow the LEGB rule. These include comprehensions, exception blocks, and classes and instances.

Comprehension Variable Scope:
A list comprehension evaluates a loop expression inside of square brackets and outputs a list. There are also dictionary comprehensions. Variables inside a comprehension are destroyed after completion and can’t be accessed anymore. By contrast, a for loop retains the last index value processed by the loop, and it can still be accessed.

Exception Variable Scope:
An exception variable holds a reference to an exception raised by a try block. These variables are local to the except block and are destroyed when it completes. So if the try block creates an err variable, this can only be referenced inside the except block. There are workarounds if needed.

Class/Instance Variable Scope:
Defining a class creates a local scope. “Unlike functions, the class local scope isn’t created at call time, but at execution time.”

Inside the local scope of a class, you can access its attribute variables directly, but outside you need to use dot notation.

“Class attributes are specific to the class object, but you can access them from any instances of the class. It’s worth noting that class attributes are common to all instances of a class. If you modify a class attribute, then the changes will be visible in all instances of the class.”

When you call a class to create an instance, that instance has its own local scope.

“To create, update, or access any instance attribute from inside the class, you need to use self along with the dot notation… On the other hand, to update or access any instance attribute from outside the class, you need to create an instance and then use the dot notation.”

“Even though you can create instance attributes within any method in a class, it’s good practice to create and initialize them inside .__init__().”

You need to access instance variables through an instance, you can’t do it with the class name and dot operator.

When writing object oriented code in Python, when looking for variables, the interpreter will first check the instance local scope, and then the class local scope. If not found in the class scope, it will throw an AttributeError.

The need for using the dot operator with classes is because classes “don’t create an enclosing scope for methods.”

Defining an instance attribute will override a class attribute with the same name, but you can still access each with the appropriate caller followed by the dot operator. But note, it’s bad OOP practice for instance variables to shadow class variables if the two have different behaviors.

Built-in functions:
globals() – “returns a reference to the current global scope or namespace dictionary”
locals() – “updates and returns a dictionary that holds a copy of the current state of local Python scope or namespace”
vars() – “returns the .__dict__ attribute of a module, class, instances, or any other object which has a dictionary attribute”
dir() – without arguments, returns list of names in current scope; with argument, returns attribute names for passed in object

“An interesting example of how you can use globals() in your code would be to dynamically dispatch functions that live in the global scope.” E.g., to dynamically change function calls depending on which platform is running the program.


## Reading 8:

**List Comprehension**

https://www.pythonforbeginners.com/basics/list-comprehensions-in-python

List comprehension offer concise syntax for creating lists in Python:

Basic syntax:

`[<expression> for <element> in <iterable>]`

Extended syntax with optional condition/filter:

`[<expression> for <element> in <iterable> if <condition>]`


List comprehension generates a list by evaluating the provided expression for each element of a provided iterable, and stores the results in a list, which it returns. Optionally, a condition can be added to filter which elements from the iterable should be evaluated as part of the expression and stored in the output list.

List comprehension can be used in many situations.

List comprehension can be used to parse files:

```
file = open(‘text.txt’, ‘r’)
text = [line for line in file]
```

For added flexibility, the expression can even be a function that you write or a lambda expression.


## Reading 09

**Enriching Your Python Classes With Dunder (Magic, Special) Methods**

https://dbader.org/blog/python-dunder-methods

Predefined special methods in Python start and end with double underscores – these are dunder methods, aka magic methods.

Dunder methods are often used in classes to define methods whose functionality mirrors built-in functions.

Examples:\
`__len__` : emulates length function\
`__getitem__` : lets you use python slicing syntax `obj[start:stop]`\
`__init__` : constructor\
`__str__` : string representation of object for user (nicely formatted)\
`__repr__` : more important and formal string representation explaining how to make the object\
`self.__class__.__name__` : can be used to access class name (to avoid hardcoding)\
`__reversed__` : reverse iterator\
`__add__` : overrides + operator\
`__radd__` : reverse add (for adding object to built-in data types)\
`__call__` : makes object callable like functions

There are many comparison dunder methods.

`__enter__` and `__exit__` must be added to create a “context manager”, which allows the class to use the `with` statement.

The use of dunder methods is part of the “Python data model” which can be thought of as an API, since they provide access to “rich language features like sequences, iteration, operator overloading, attribute access, etc.”

Dunder methods can do the following:
- “Initialization of new objects
- Object representation
- Enable iteration
- Operator overloading (comparison)
- Operator overloading (addition)
- Method invocation
- Context manager support (with statement)”


**Tutorial: Basic Statistics in Python — Probability**

https://www.dataquest.io/blog/basic-statistics-in-python-probability/

The sample space is the set of all possible events. The probability of an event is the number of times it can occur divided by the sample space.

Python can be used to model/simulate data generation. “Given enough data, statistics enables us to calculate probabilities using real-world observations.”

Probability distributions represent probabilities for various events graphically. The normal distribution (bell curve) comes up in many contexts and is distinguished by its shape and symmetry.

The normal distribution is especially important because when repeatedly sampling from an unknown probability distribution, the sampled means trend towards being normally distributed around the true mean as the number of samples grows (Central Limit Theorem), even if the underlying distribution is not normal.

The three sigma rule (69-95-99 rule) describes how close to the mean observations fall in a normal distribution:
- 68% - one standard deviation
- 95% - two standard deviations
- 99.7% - three standard deviations

A Z-score specifies how many standard deviations an observation lies from the mean.

A Z-score is compared against a Z-table, which gives the cumulative probability up to that Z-score.

A standard normal distribution has a mean of 0 and standard deviation of 1.


## Reading 10

**Implementation: Stacks and Queues**

**Cheat Sheet:**

**Stacks:**\
LIFO (Last in, First Out)

Analogy: Stack of pancakes - when a new pancake is done, it gets placed on the top of the pile. When someone wants to eat a pancake, they take one from the top of the pile (aka stack). LIFO.

Operations: Add to top of stack (push), remove from top of stack (pop), check the value at the top of the stack (peek), Boolean method isEmpty checks if the stack is empty

References: One reference called “top” points to the first node in the stack – same as for a singly linked list, where the linked list variable points to the head node

Big O: Constant time O(1) for all of the above operations

Implementation: A stack can be implemented using a singly linked list as the underlying data structure


**Queues:**\
FIFO (First in, First Out)

Analogy: Standing in line – new customers go to the end of the line to wait their turn. The customer at the front of the line, who has been waiting the longest, gets helped by the next available cashier. FIFO.

Operations: Add to the back of the queue (enqueue), remove from the front of the queue (dequeue), check the value at the front of the queue (peek), Boolean method isEmpty checks if the queue is empty

References: Two references, one to the front of the queue (front), and one to the back of the queue (rear)

Big O: Constant time O(1) for all of the above operations

Implementation: A queue can be implemented using a singly linked list, but with a second external reference that points to the tail node, in addition to the reference that points to the head node.


## Reading 11

**Jupyter Lab**

https://jupyterlab.readthedocs.io/en/stable/getting_started/overview.html

Text editor – create a code console by right clicking the tab, and clicking “New Console for Editor”, and then selecting a kernel (e.g. Python3).

Terminals in Jupyter provide full support for system shells. 

Common formats – all popular image formats are supported as standalone files or in notebooks

Zoom In/Out: - =\
Rotate Left/Right: [ ]\
Reset: 0

Supports very large data files.

Jupyter Notebooks – let you work seamlessly with data and code together. 

Jupyter notebooks have “command mode” and “edit mode”. Notebooks start in command mode.

Notebooks are composed of cells. Use arrow keys to jump between cells.  Press enter to edit currently active cell.

Shortcut keys:

a – add a cell above\
b – add a cell below\
c – copy a cell\
v – paste\
x – cut\
dd – delete\
z – undo\
shift z – redo\
y – changes format to markdown\
m – changes format to markdown

Edit mode – press m to enter markdown.

The kernel specifies the coding language. Press `shift+ enter` to run cell. Number to the left of the cell signifies the execution order of that cell in the kernel. If you run the cell, the number will increment. Whole notebook runs on the same kernel. You can jump around to different cells and execute different cells flexibly. Their numbers will increment. To start clean, restart kernel – in command mode, enter `00`.

Click run menu to see options to run specific subsets of cells.

**Numpy Tutorial**

https://www.dataquest.io/blog/numpy-tutorial-python/

To work with data in numpy, first use a csv.reader object to read and store the data:

```
import csv
with open(‘filename.csv’, ‘r’) as f:
	data = list(csv.reader(f, delimiter = ‘;’))
```

In this example, the data is separated by semicolons, so specify this as the delimiter (delimiter default is a comma).

A list of lists is now stored in the data variable. Each inner list is a row from the ssv file.

Numpy is a library for storing/manipulating data as martices (2D arrays). The number of dimensions is called the rank, and each dimension is an axis. Rows are the first axis, and columns are the second axis.

To create a numpy array, use the `numpy.array` function. If you pass in a list of lists, numpy will automatically create a nympy array.

All elements in a numpy array must be the same type, so when working with numerical data, leave out the header row that contains the column names as string types. Use list slicing to omit header row. Specifying a dtype argument converts every element to the specified data type (e.g. converts any ints to floats).

```
import csv
with open(‘filename.csv’, ‘r’) as f:
	data = list(csv.reader(f, delimiter=‘;’))
import numpy as np
data = np.array(data[1:], dtype=np.float)
```

Now the data is stored in a numpy array as floats. To check the number or rows and columns, run `data.shape`, which returns (# of rows, # of columns).

`np.zeros((<# of rows>, <# of columns>))` - creates a numpy array of all 0’s (useful for initializing an array of a given size)
`np.random.rand((<# of rows>, <# of columns>))` - creates a numpy array of random numbers between 0 and 1 (useful for testing code)

You can also use numpy to read in csv (and other) files using `numpy.genfromtxt` function:

`data = np.genfromtxt(‘filename.csv’, delimiter=‘;’, skip_header=1)

Numpy automatically sets the data type for all the elements (Numpy is written in C and has its own data types, but these map to python data types).

Numpy arrays are indexed by their row and column (indices start at 0), and can be accessed with square brackets:

`data[<row>, <column>]`

To select a subset of a numpy array, use slice notation:

`data[<row start> : <row end>, <column start>, <column end>]`

If starting from 0, or going to the end along any axis, can use `:` in place of a start or end value. Examples:

```
# Access first three rows of column four
data[:3, 3]

# Access all elements in column four
data[:,3]
```
You can reassign values directly to numpy elements using these indices.

Numpy also supports vectors (1D arrays). Grabbing a single row or column from a 2D array returns a 1D array/vector. Individual elements of a vector can be accessed with one index.

Numpy supports higher dimensional arrays as well, which are stored as lists of lists of lists. Indexing and slicing work the same way – number of indices required matches the dimension, and this is how many nested lists there are.

`numpy.ndarray.astype` - converts data to different data type in a numpy array

Applying arithmetic operations to an array automatically performs that operation on every element individually – note that the array is not modified in place; a new array gets returned. But if you use the +=, *=, etc. operators, the array does get modified in place.

You can also add vectors, and then corresponding elements are added. Holds for other operations as well.

Broadcasting can be used to add an array and a vector if the vector’s dimension matches one of the array dimensions. E.g., if the vector is the same length as the array rows, then the vector will be added to each row of the array. Other operations are also supported by broadcasting.

Numpy Array Methods:\
`data[:, 5].sum()` - sums all elements of the provided part of the array – pass in axis argument to sum along rows or columns – axis=1 sums the rows, and axis=0 sums the columns (note this seems reversed from row/column numbering)

`numpy.ndarray.mean`
`numpy.ndarray.std`
`numpy.ndarray.min`
`numpy.ndarry.max`

These all work like the sum method.

You can also use comparison operators on numpy arrays – returns a Boolean array. Using this returned Boolean array, you can filter to produce a subset of the original array.

```
filter = data[:,10] > 7
data[filter][:3,:]
```

The top line selects rows where the value in one column is above a certain threshold. This filter then gets applied to the full data array and grabs just those rows from the array.

To filter by multiple conditions, place conditions in parentheses and join with &.

Reshaping arrays:

`np.transpose(data)`\
`data.ravel()` - turns array into 1D representation\
`data.reshape((<# of rows>, <# of columns>))`\
`np.vstack()` - vertically stacks multiple arrays\
`np.hstack()` - stacks columns (need to have same number of rows)\
`np.concatenate` - general version of hstack and vstack – specify axis along which to concatenate

Numpy Cheat Sheet:\
https://s3.amazonaws.com/dq-blog-files/numpy-cheat-sheet.pdf


## Reading 12: Pandas

https://pandas.pydata.org/pandas-docs/stable/user_guide/10min.html

https://pandas.pydata.org/pandas-docs/stable/user_guide/dsintro.html#dsintro

```
import numpy as np
import pandas as pd
```

A pandas series is a 1D labeled array, where “the axis labels are collectively referred to as the index.” To create a series, use the Series method and pass in data and the list of index labels:

`s = pd.Series(data, index=index)`

Default index is consecutive integers starting from 0.

Alternatively, you can pass a dictionary into the Series method, and the keys will be the indices and the values will be the data.

A pandas DataFrame is like a spreadsheet. It is a 2D labeled data structure.

Use the DataFrame() method and pass in data, and optionally, row and column index labels (data not matching the indices will be discarded).

Index parameter sets row indices, columns parameter sets column indices.

The pd.date_range() method outputs a list of dates. Pass in a starting date as a string, and the number of periods.

`dates = pd.date_range(“20130101”, periods=6)`

Can then use the list dates as the index for a pandas DataFrame:

`df = pd.DataFrame(np.random.randint(6,4), index=dates, columns=list(“ABCD”))`

Passing a dictionary into pd.DataFrame(), where the values are series, numpy arrays, lists, or something similar, results in a data frame where the keys are column labels and the values are data entries. The rows are given a default index of integers starting from 0.

DataFrame columns can have different types.

DataFrame.head() and DataFrame.tail() print the first five, and last five rows, respectively. Pass in an integer for a different number of rows.
To get the row and/or column labels, run `DataFrame.index` and `DataFrame.columns`.

`DataFrame.to_numpy` - “gives a NumPy representation of the underlying data.” (expensive when columns have different data types, since numpy will cast everything to an object)

`describe()` - outputs summary statistics\
`df.T` - transposes data\
`DataFrame.sort_index()` - sorts by an axis, has ascending parameter that’s True by default\
`DataFrame.sort_values()` - sorts by values – use parameter by= to sort by a column

Selecting:

Selecting a single column returns a series. E.g., `df[“A”]` equivalent to `df.A`

Slicing: `df[<starting row> : <ending row>]`\
Note: Can identify rows by integer index or label index

When selecting by label, can also use `DataFrame.loc()` or `DataFrame.at()`

E.g., grab all rows from two columns: `df.loc[:, [“A”, “B”]]`

E.g., grab a subset of rows from two columns: `df.loc[“20130102”:“20130104”, [“A”, “B”]]`

For selection by position, use `DataFrame.iloc()` or `DataFrame.at()`

E.g., `df.iloc[3]`

E.g., integer slicing: `df.iloc[3:5, 0:2]`

E.g., pass in lists: `df.iloc[[1, 2, 4], [0, 2]]`

Boolean Indexing:

Can use conditionals to select parts of a data frame.

Select based on values in one column: `df[df[“A”] > 0]`

Select based on condition in entire data frame (note – will fill in NaN values): `df[df > 0]`

Can use `isin()` for filtering

Setting:

“Setting a new column automatically aligns the data by the indexes.”\
You can create a series and then assign it as a new column in the data frame:

```
s1 = pdSeries([1,2,3,4,5,6], index = pd.date_range(“20130102”, periods=6))
df[“F”] = s1
```

`df.at` - set value by label\
`df.iat` - set value by position\
`df.loc` - set by assigning a numpy array

Can also use conditionals in setting:

```
df2 = df.copy()
df2[df2 > 0] = -df2
```

`df.reindex(index=, columns=)` - “Reindexing allows you to change/add/delete the index on a specified axis. This returns a copy of the data.”

`DataFrame.dropna()` - drops NaN values\
`DataFrame.fillna(value=)` - fills in missing values\
`DataFrame.isna()` - returns Boolean mask for NaN values

Operations exclude missing data and will broadcast when necessary.

`DataFrame.apply()` - applies a custom function to the data frame

`value_counts()` - returns data counts

Series come with string operations.

`concat()` - concatenates series and/or data frames\
`merge()` - allows SQL-style join types along specific columns

`df.groupby` - groups data so another function can be applied. E.g.:

`df.groupby(“A”)[[“C”, “D”]].sum()`

“Grouping by multiple columns forms a hierarchical index.”

For multi-indexed data:

`stack()` - compresses a level in the DataFrame’s columns\
`unstack()` - expands a level in the DataFrame’s columns

`pivot_table()` - “pivots a DataFrame specifying the `values`, `index`, and `columns`”

Time series:

`resample()` - converts units of time series data\
`tz_localize()` - localizes time series data to a time zone\
`tz_convert()` - converts time zone aware series to a different time zone\
`to_timestamp` and `to_period` - convert between representations to allow certain operations

Categorical Data:

`astype` - converts data type\
`rename_categories` - renames categories\
`set_categories` - reorder categories

Note – sorting (`sort_values`) by category references categorical order not lexical order

Plotting:

`import matplotlib.pyplot as plt`

`plt.close(“all”)` -  closes a figure window

If not in Jupyter Notebook, use `plt.show()` to show plot. In Jupyter Notebook, can just run `plot()` off the data frame.

`plt.legend()` - adds a legend


CSV files:

`DataFrame.to_csv()` - write to csv file\
`DataFrame.read_csv()` - read from csv file\
`DataFrame.to_excel(“filename.xlsx”, sheet_name=“Sheet1”)` - writes to excel file\
`DataFrame.read_excel(“filename.xlsl”, “Sheet1”, index_col=None, na_values=[“NA”])` – reads from excel file


## Reading 13

**How to Run Linear Regression in Python**

https://www.crayondata.com/how-to-run-linear-regression-in-python-scikit-learn/

Import statements:

```
%matplotlib inline
import numpy as np
import pandas as pd
import scipy.stats as stats
import matplotlib.pyplot as plt
import sklearn
```

Importing a dataset from scikit learn:

```
from sklearn.datasets import load_<name>
data = load_<name>
```

`data` is a dictionary, so call `data.keys()` to see what can be accessed.

`data.DESCR` describes the dataset

If there’s a data key, can use this to put the data in a pandas DataFrame.

`df = pd.DataFrame(data.data)`

Set the columns to the feature names:

`df.columns = data.feature_names`

Use scikit learn to run linear regression.

`from sklearn.linear_model import LinearRegression`

Drop the target column from the data frame and store this in an X variable. A Y variable can hold the target column.

`X = df.drop(‘target’, axis = 1)`

Create a LinearRegression object:

`lm = LinearRegression()`

Fit the model:

`lm.fit(X, data.target)`

You can now get the intercept and coefficients with `lm.intercept_` and `lm.coef_`

Make a data frame containing features and regression coefficients:

`pd.DataFrame(zip(X.columns, lm.coef_), columns = [‘features’, ‘estimatedCoefficients’])

Make a scatter plot comparing one of the features and the target column:

```
plt.scatter(df.feature1, df.target)
plt.xlabel(‘x-axis label’)
plt.ylabel(‘y-axis label’)
plt.title(‘title’)
plt.show()
```

Predict values:

`lm.predict(X)`

Plot predicted vs. actual values:

`plt.scatter(df.target, lm.predict(X))`

Calculate mean squared error:

`np.mean((df.target – lm.predict(X))**2)`

In practice, use scikit learn’s train-test-split functionality to train part of your data and test on the other part:

`X_train, X_test, Y_train, Y_test = sklearn.model_selection.train_test_split(X, df.target, test_size=0.33, random_state=5)`

Then run linear regression:

```
lm = LinearRegression()
lm.fit(X_train, Y_train)
pred_train = lm.predict(X_train)
pred_test = lm.predict(X_test)
```

Calculate MSE:

`np.mean((Y_train – lm.predict(X_train))**2)`

`np.mean((Y_test – lm.predict(X_test))**2)`

Plot residuals:

```
plt.scatter(lm.predict(X_train), lm.predict(X_train) – Y_train, c=‘b’, s=‘40’, alpha=0.5)
plt.scatter(lm.predict(X_test), lm.predict(X_test) – Y_test, c=‘g’, s=‘40’)
plt.hlines(y=0, xmin=0, xmax=50)
```


## Reading 14

**Matplotlib Tutorial**

https://github.com/rougier/matplotlib-tutorial

Matlplotlib is a 2D graphics library

IPython is an enhanced interactive Python shell 

Plotting sin and cos:

```
X = np.linspace(-np.pi, np.pi, 256, endpoint=True)
C, S = np.cos(X), np.sin(X)

plt.figure(figsize=(10,6), dpi=80)
plt.plot(X, C, color="blue", linewidth=2.5, linestyle="-")
plt.plot(X, S, color="red",  linewidth=2.5, linestyle="-")
```

Change graph axes:

```
plt.xlim(X.min()*1.1, X.max()*1.1)
plt.ylim(C.min()*1.1, C.max()*1.1)
```

Change ticks:

```
plt.xticks( [-np.pi, -np.pi/2, 0, np.pi/2, np.pi])
plt.yticks([-1, 0, +1])
```

Label ticks (this uses latex for properly rendering pi and pi over 2 labels):

```
plt.xticks([-np.pi, -np.pi/2, 0, np.pi/2, np.pi],
       [r'$-\pi$', r'$-\pi/2$', r'$0$', r'$+\pi/2$', r'$+\pi$'])

plt.yticks([-1, 0, +1],
       [r'$-1$', r'$0$', r'$+1$'])
```

This plot has spines, which are borders with tick marks surrounding the graph. To remove the border and instead plot conventional axes with four quadrants, run:

```
ax = plt.gca()
ax.spines['right'].set_color('none')
ax.spines['top'].set_color('none')
ax.xaxis.set_ticks_position('bottom')
ax.spines['bottom'].set_position(('data',0))
ax.yaxis.set_ticks_position('left')
ax.spines['left'].set_position(('data',0))
```

To add a legend, add labels to each plot and a call to legend method:

```
plt.plot(X, C, color="blue", linewidth=2.5, linestyle="-", label="cosine")
plt.plot(X, S, color="red",  linewidth=2.5, linestyle="-", label="sine")

plt.legend(loc='upper left', frameon=False)
```

Annotating a figure – this draws two dotted lines and annotates with an arrow and text:

```
t = 2*np.pi/3
plt.plot([t,t],[0,np.cos(t)], color ='blue', linewidth=1.5, linestyle="--")
plt.scatter([t,],[np.cos(t),], 50, color ='blue')

plt.annotate(r'$\sin(\frac{2\pi}{3})=\frac{\sqrt{3}}{2}$',
             xy=(t, np.sin(t)), xycoords='data',
             xytext=(+10, +30), textcoords='offset points', fontsize=16,
             arrowprops=dict(arrowstyle="->", connectionstyle="arc3,rad=.2"))

plt.plot([t,t],[0,np.sin(t)], color ='red', linewidth=1.5, linestyle="--")
plt.scatter([t,],[np.sin(t),], 50, color ='red')

plt.annotate(r'$\cos(\frac{2\pi}{3})=-\frac{1}{2}$',
             xy=(t, np.cos(t)), xycoords='data',
             xytext=(-90, -50), textcoords='offset points', fontsize=16,
             arrowprops=dict(arrowstyle="->", connectionstyle="arc3,rad=.2"))
```

Make tick labels bigger and put on top of semi-transparent box for visibility when graph intersects:

```
for label in ax.get_xticklabels() + ax.get_yticklabels():
    label.set_fontsize(16)
    label.set_bbox(dict(facecolor='white', edgecolor='None', alpha=0.65 ))
```

Explicitly creating figures and axes (and subplots) gives more control. The figure refers to the entire window, and axes can be placed within it. Subplot generates a grid within the figure.

Calling plot calls gca(), which gets the current axes and then calls gcf(), which gets the current figure. If there is no figure, figure() gets called to create one.

Figures are numbered from 1 (not 0).

Figure parameters include num, figsize, dpi, facecolor, edgecolor, frameon

For `subplot`, specify the number of rows and columns. `gridspec` is more powerful.

To configure ticks, use the appropriate locator from the class matplotlibl.ticker.Locator.

Can add animation by declaring a FuncAnimation object that specifies figure to update, update function, and delay between frames.

In order to render an IPython animation in Jupyter notebook, need to make an html video:

```
from IPython.display import HTML
HTML(animation.to_html5_video())
```

For plotting on a map of the Earth, can use cartopy project.

See link for additional tutorials. See matplotlib gallery.


## Reading 15

**Binary Tree, Binary Search Tree, K-ary Tree**

Traversing a tree: Depth First (uses stack) vs. Breadth First (uses queue)

Depth First Traversal (3 kinds):\
https://www.baeldung.com/cs/depth-first-traversal-methods#:~:text=In%20this%20tutorial%2C%20we'll,will%20be%20easier%20to%20trace.

Pre-order: Starts at root, goes left until it can’t any longer, then goes right until it can’t any longer. Repeat, always starting from a parent node.\
**Order: NLR – Node, Left, Right**

In-order: Always tries to traverse the left subtree first. When there are no more left children, go up a level to the parent, then traverse this node’s right subtree. Repeat this process, always traveling up a level after all left child nodes have been visited.\
**Order: LNR – Left, Node, Right**

Post-order: Follow left nodes all the way to the leftmost leaf, then visit sibling nodes to the right, then travel up a level to the parent node. Repeat, always traveling all the way down the leftmost path first. Then traverse siblings. Then go back up to the parent node.\
**Order: LRN – Left, Right, Node**


Breadth First Traversal:

Traverse full width of one level at a time.

Depth First Stack vs. Breadth First Queue:

- Depth First (pre-order): Start at the root node and output its value. If the root node has a left child, recursively call the function on that node (this adds a function call to the call stack). Otherwise, if the node has a right child, recursively call the function on that node (this also adds a function to the call stack). The unwinding of the call stack results in visiting the nodes in the depth-first pre-order, and each visited node value gets returned as output.

- Breadth First: Start at the root node. Enqueue the visited node. Dequeue the front node (which is the root node). Enqueue the left and right children of this node. Dequeue the first node and enqueue its child elements. Keep repeating this process of dequeuing the first node and enqueuing its children until all nodes have been visited and removed from the queue.

Binary vs. K-arry Trees:

Binary nodes can have up to two child nodes. K-ary trees can have any number of child nodes. K is the max number of child nodes. Breadth-first traversal is used for k-ary trees (enqueue all child nodes of any visited node).

Binary Tree Big O:

Inserting/searching for a node – Time: O(n), Space: O(w)

Max binary tree width: 2^(h-1)\
Binary tree height: log n

Binary Search Tree:\
Binary tree in sorted order – smaller values fall to the left of a node, larger values fall to the right of a node.

Search time is O(h) which is O(log n) because only need to search one node per level. Space complexity is O(1).


## Reading 16

https://www.ibm.com/cloud/learn/serverless

Serverless is “a cloud computing application development and execution model that enables developers to build and run application code without provisioning or managing servers or backend infrastructure.”

This lets developers focus on the front-end of their application. This application code gets deployed to containers, which are managed by a cloud service provider. The cloud provider handles all routine infrastructure management and maintenance, including security.

Payment is based exclusively on actual execution time and resources – serverless can “scale to zero” when program execution stops, so developers don’t get billed for idle time.

Serverless refers to the developer’s perspective of not having to manage a server. All major cloud service providers offer a serverless platform.

“Together **serverless computing**, **microservices** and **containers** form a triumvirate of technologies typically considered to be at the core of cloud-native application development.”

Serverless is based on the FaaS model (function-as-a-service), which is a cloud computing service that allows developers to run code or containers in response to events and requests without having to manage a backend or any infrastructure required to actually run the code.

But serverless has features beyond FaaS, including serverless databases and storage that scale linearly with demand, event streaming and messaging, and API gateways (proxies for web actions).

Compared to PaaS (platform-as-a-service), containers, and virtual machines, serverless has less provisioning time, lower administrative burden, no maintenance, auto-scaling all the way down to zero, no capacity planning requirement, statelessness, high availability and disaster recovery, and resource and billing efficiency.

Kubernetes requires cloud provider-specific software to run serverless apps. Knative is an open source serverless framework for Kubernetes “that enables any container to run as a serverless workload on any cloud platform that runs Kubernetes.” Knative handles network routing, event triggers, and autoscaling for serverless apps.

Serverless Pros:

- higher developer productivity
- pay for execution only/cost effective
- Support many languages
- Streamlines development cycle and DevOps
- Provide visibility into system and usage

Serverless Cons:

- Too much latency for certain apps
- Higher costs for stable/predictable workload
- Can make monitoring and debugging more difficult
- Vendor lock-in – potentially difficult to migrate to new cloud provider
	

## Reading 17

**Web Scrape with Python in 4 minutes**

https://towardsdatascience.com/how-to-web-scrape-with-python-in-4-minutes-bc49186a8460

```
import requests
import urllib.request
import time
from bs4 import BeautifulSoup
```

Use the requests library to access a webpage you want to scrape as follows:

```
url = 'http://web.mta.info/developers/turnstile.html'
response = requests.get(url)
```

An output of `Response[200]` means the request was successful.

Use BeautifulSoup library to parse the html on the webpage:

```
soup = BeautifulSoup(response.text, “html.parser”)
```

Inspect the website to determine the html tags that enclose the data that you’re trying scrape. Use the BeautifulSoup findAll method, and pass in the enclosing html tag as a string:

```
soup.findAll(‘a’)
```

This code returns every <a> tag.  To extract the link from every <a> tag, run:

```
one_a_tag = soup.findAll(‘a’)[<index number>]
link = one_a_tag[‘href’]
```

Note that the stored link may be a relative file path, and so you may need to pre-pend the rest of the file path. Then use the urllib.request library to download the full file path. request.urlretrieve takes two parameters, the file url and the filename.

```
download_url = ‘http://baseurl’ + link
urllib.request.urlretrieve(download_url, ‘filename’)
```

Include a time delay to avoid making too many requests too quickly and getting blocked:

```
time.sleep(1)
```

To download all files from a page, use a loop. Complete code:

```
import requests
import urlib.request
import time
from bs4 import BeautifulSoup

url = ‘http://web.mta.info/developers/turnstile.html’
response = requests.get(url)
soup = BeautifulSoup(response.test, “html.parser”)

line_count = 1
for one_a_tag in soup.findAll(‘a’):
	if line_count >= 36:
		link = one_a_tag[‘href’]
		download_url = ‘http://web.mta.info/developers/’ + link
		urllib.request.urlretrieve(download_url, ‘./’ + link[link.find(‘/turnstile_’)+1:])
		time.sleep(1)
	line_count += 1
```

	
**What is Web Scraping?**

https://en.wikipedia.org/wiki/Web_scraping

Web scraping involves fetching a webpage, i.e., downloading it, and extracting information from it. Generally a web crawler is used to fetch many webpages, and code automates the collection of specific data from these pages.

Since “most web pages are designed for human end-users and not for ease of automated used… specialized tools and software have been developed to facilitate the scraping of web pages.”

Many websites/pages don’t want to be scraped and employ mechanisms to prevent this. Some of these mechanisms can be circumvented by using e.g., DOM parsing, computer vision, and NLP to have a bot behave like a human user and evade detection.

“Websites can declare if crawling is allowed or not in the robots.txt file and allow partial access, limit the crawl rate, specify the optimal time to crawl and more.”

To prevent crawling, websites can “Load database data straight into the HTML DOM via AJAX, and use DOM methods to display it, forcing crawlers to either reproduce those AJAX requests or use browser rendering (e.g. a headless browser).”


**How to Scrape Websites Without Getting Blocked**

https://www.scrapehero.com/how-to-prevent-getting-blacklisted-while-scraping/

“If a crawler performs multiple requests per second and downloads large files, an under-powered server would have a hard time keeping up with requests from multiple crawlers.” Therefore, it’s important to follow web scraping best practices.

Follow robots.txt site guidelines (usually located in root directory of a website - /robots.txt)\
`User-agent: *` and `Disallow:/` mean the website doesn’t want to be scraped. But sites still typically allow bots since they want to be indexed by Google.

Giveaways that you’re a bot:
- scraping too fast
- following the same pattern
- too many requests from same IP address
- “Not identifying as a popular browser. You can do this by specifying a ‘User-Agent’.”
- Identifying as an old browser

When web scraping, do it slowly and be considerate of the websites.

“Use auto throttling mechanisms which will automatically throttle the crawling speed based on the load on both the spider and the website that you are crawling. Adjust the spider to an optimum crawling speed after a few trial runs. Do this periodically because the environment does change over time.”

Introduce some randomness into your crawling.

Make request through proxies and rotate them to avoid getting your IP address blocked. Methods for changing your outgoing IP address:
- TOR
- VPNs
- Free Proxies
- Shared Proxies
- Private Proxies
- Data Center Proxies
- Residential Proxies

“Rotate User Agents and corresponding HTTP request headers between requests.” Most web scrapers to do not have a default User Agent, so add this.

Pretending to be a Google bot:\
https://developers.google.com/search/docs/crawling-indexing/googlebot?visit_id=638052657042362063-913194330&rd=1

Adding a User Agent is often sufficient, but if you still get blocked, add more headers, such as:

- Accept
- Accept-Language
- Referer
- DNT
- Upgrade-Insecure-Requests
- Cache-Control

“Do not send cookies unless your scraper depends on Cookies for functionality.”

To determine values to fill in for these headers, inspect your web traffic using Chrome dev tools, or e.g., MitmProxy or Wireshark. You can use a curl command to copy values. You can then use a tool (https://curl.trillworks.com) to convert this to Python.

Create multiple browser and header combinations and rotate them.

If this approach still doesn’t work, use a headless browser like Puppeteer, Pyppeteer, Selenium, or Playwright.

Anti-scraping tools are constantly improving. Detection can include browser side fingerprinting, checking for automation tools like Selenium, Puppeteer, and Playwright, bot signatures, and non-standard browser features.

Some workaround tools to improve headless browsers:
- Puppeteer Extra – Puppeteer Stealth Plugin
- Patching Selenium/Phantom JS (https://stackoverflow.com/questions/33225947/can-a-website-detect-when-you-are-using-selenium-with-chromedriver)
- Fingerprint Rotation (https://www.microsoft.com/en-us/research/publication/privaricator-deceiving-fingerprinters-with-little-white-lies/)

Tutorials:\
https://www.scrapehero.com/tutorial-web-scraping-hotel-prices-using-selenium-and-python/
https://www.scrapehero.com/how-to-build-a-web-scraper-using-puppeteer-and-node-js/

Beware of honey pots, which are traps for hackers. This can include links that are invisible to users but not to web scrapers – so make sure any links are visible (no nofollow tag, or CSS display:none, or link same color as background). Note, this is not widely used.

Some websites change their layouts to avoid scraping.

Generally you should avoid scraping a website that requires a login.

If you need to scrape a Captcha website, use a Captcha service.

Signs you have been blocked:
- CAPTCHA pages
- Content delivery delays
- Frequent 404, 301, 50x, or other HTTP errors


## Reading 18

**Encryption, Decryption & Hacking**

https://www.khanacademy.org/computing/computers-and-internet/xcae6f4a7ff015e7d:online-data-security/xcae6f4a7ff015e7d:data-encryption-techniques/a/encryption-decryption-and-code-cracking

A Caesar Cipher is a substitution cipher – each letter of a message is replaced by the corresponding letter when the alphabet is shifted by some fixed number. A lookup table can be constructed showing the shifted alphabet under the regular alphabet, and this allows easy encryption and decryption, provided the shift index is known.

There are three common techniques for cracking ciphers: frequency analysis, known plaintext, and brute force. 

Frequency analysis examines the most frequently occurring characters in an encoded message and attempts to match these with the most frequently occurring letters in the language.

Known plaintext takes advantage of when part of the message may be known or partially known, such as if the first part of a message always begins with similar information (e.g., encrypted German messages in WWII began with a weather forecast). This can make the rest of the message easier to decode.

Brute force involves trying all possibilities – for example, trying every substitution cipher (all possible shift values)

Encryption – encode data using a secret key\
Decryption – decode data using a secret key\
Code cracking – decoding data without the secret key


**Caesar Cipher**

https://en.wikipedia.org/wiki/Caesar_cipher

The Caesar Cipher, aka the shift cipher “is one of the simplest and most widely know encryption techniques.” Each letter in a message is encoded using a shifted alphabet.

The Caesar cipher can be the first step in more complex encodings, such as the Vigenère cipher, which uses multiple Caesar ciphers according to a keyword.

Since Caesar ciphers are easy to decode, they are not secure.

A Caesar cipher can be encoded and decoded using a table consisting of two alphabets, with one shifted the appropriate amount. Equivalently, a Caesar cipher can be implemented using modular arithmetic. Letters are encoded as integers, and then the following equations encode and decode a message:

Encode: E(x) = (x+n) mod 26\
Decode: D(x) = (x-n) mod 26

The Caesar cipher is a monoalphabetic substitution – the same shift amount is used for each letter of a message. Polyalphabetic substitutions shift different letters different amounts (e.g. Vigenère cipher).

“The Vigenère cipher uses a Caesar cipher with a different shift at each position in the text; the value of the shift is defined using a repeating keyword. If the keyword is as long as the message, is chosen at random, never becomes known to anyone else, and is never reused, this is the one-time pad cipher, proven unbreakable. The conditions are so difficult they are, in practical effect, never achieved.”


## Reading 19

**Regular Expressions**

https://www.datacamp.com/tutorial/python-regular-expression-tutorial

`import re`

Methods:

`re.match(pattern, sequence)`\
`re.search(pattern, sequenece)`\
`re.search(pattern, sequenece).group()`

^ Matches start of the string\
$ Matches end of string\
[a-zA-Z0-9] Matches any letters or numbers\
\ Indicates escape character\
\w Matches any single letter, digit, or underscore\
\W Matches any character not part of \w\
\s Matches a single whitespace character (space, newline, tab, return)\
\S Matches any character not part of \s\
\d Matches decimal digit 0-9\
\D Matches any character that is not a decimal digit\
\t Matches tab\
\n Matches newline\
\r Matches return\
\A Matches only at the start of the string and across multiple lines\
\Z Matches only at the end of the string\
\b Matches only the beginning or end of the word

Repititions:

+ Preceding character appears once or more\
* Preceding character appears zero or more\
? Preceding character appears exactly zero or one time

{x} Repeat exactly x times\
{x,} Repeat at least x times\
{x, y} Repeat at least x times, no more than y times


**Shutil**

https://pymotw.com/3/shutil/

```
import glob
import shutil
```

Used for high level file operations

"`copyfile()` copies the contents of the source to the destination and raises IOError if it does not have permission to write to the destination file."

Three functions for working with directory trees:

`copytree()`\
`rmtree()`\
`move()`

Finding Files

"`which()` function scans a search path looking for a named file"

Archives

"Python’s standard library includes many modules for managing archive files such as tarfile and zipfile."

`make_archive()` creates a new archive file

File System Space

"`disk_usage()` returns a tuple with the total space, the amount currently being used, and the amount remaining free."


## Reading 26

**Getting started with Django**

https://www.djangoproject.com/start/

**Intro to Django:**

**Object-Relational Mapper:** 

- You can define data models in Python for storing data in a database
- Every model is a Python class and a subclass of django.db.models.Model
- Django provides “an automatically-generated database-access API”
- When defining a model, fields are specified as class attributes (each attribute maps to a database column)

Example:

```
from django.db import models

class Person(models.Model):
	first_name = models.CharField(max_length=30)
	last_name=models.CharField(max_length=30)
```

- After defining a model, tell Django to use the model by going to file settings and adding the name of the file containing the model to the INSTALLED_APPS setting
- After adding a file to INSTALLED_APPS, run `manage.py migrate`
- Optional: first run `manage.py makemigrations`

“Django offers ways to define the three most common types of database relationships: many-to-one, many-to-many and one-to-one.”

“To define a many-to-one relationship, use `django.db.models.ForeignKey`”\
“To define a many-to-many relationship, use `ManyToManyField`”\
“To define a one-to-one relationship, use `OneToOneField`”

“The most important attribute of a model is the Manager. It’s the interface through which database query operations are provided to Django models and is used to retrieve the instances from the database. If no custom Manager is defined, the default name is objects. Managers are only accessible via model classes, not the model instances.”

“Define custom methods on a model to add custom “row-level” functionality to your objects. Whereas Manager methods are intended to do “table-wide” things, model methods should act on a particular model instance.”

“The model instance reference has a complete list of methods automatically given to each model. You can override most of these – see overriding predefined model methods, below – but there are a couple that you’ll almost always want to define: `__str__()`, `get_absolute_url()`”

You’ll also often want to change `save()` and `delete()`


**URLs and Views:**

“To design URLs for an application, you create a Python module called a URLconf. Like a table of contents for your app, it contains a simple mapping between URL patterns and your views.”

URLs are used when a user makes a request. Django checks the URLconf module to find a match for the requested URL and then imports and calls the corresponding view (a Python function or class-based view). The view gets passed an instances of HttpRequest.


**Templates:**

Django supports a template language that is flexible and extensible, in order to dynamically generate HTML.

“Django defines a standard API for loading and rendering templates regardless of the backend.”


**Forms:**

“Django provides a powerful form library that handles rendering forms as HTML, validating user-submitted data, and converting that data to native Python types. Django also provides a way to generate forms from your existing models and use those forms to create and update data.”

Use Django’s Form class to build forms:

```
from django import forms

class myForm(forms.Form):
```

**Authentication:**

Django provides secure authentication. Users can safely log in and out.

However, “The authentication system in Django aims to be very generic and doesn’t provide some features commonly found in web authentication systems. Solutions for some of these common problems have been implemented in third-party packages:

- Password strength checking
- Throttling of login attempts
- Authentication against third-parties (OAuth, for example)
- Object-level permissions”


**Admin:**

“One of the most powerful parts of Django is its automatic admin interface.” This interface reads model metadata and provides hooks for customization.

“The admin is enabled in the default project template used by `startproject`”

Any model that can be edited by the admin interface needs to be registered with the admin.

There is also a decorator for registering models: `@admin.register(Author)`


**Internationalization:**

All or part of an application can be translated and dates, times, numbers, and time zones can be set for particular countries/locations.

**Security:**

Django protects against “Clickjacking, cross-site scripting, CSRF, SQL injection, and remote code execution.”


**How Django Works Behind the Scenes**

https://wsvincent.com/how-django-works-behind-the-scenes/

Django is a widely used open source Python-based web framework. Django is maintained and extended by the Django Software Foundation (DSF). It has a combination of paid contractors (Django Fellows) and volunteers. The DSF is run by a Board of Directors. “There is a separate organizational structure for the technical team.”

“Django code is led by a core team of volunteers, two paid Django Fellows, and a larger group of contributors.”

“One of the best ways to become more involved in Django is to attend an annual conference and meet all the contributors in person. Currently there are DjangoCons in the US, Europe, Australia, and Africa in 2020 for the first time."


### Reading 27

**Using Models**

https://developer.mozilla.org/en-US/docs/Learn/Server-side/Django/Models

Django models are defined using Python in order to pre-structure data for entry in a database. The choice of models is independent of the database – simply choose a database, write model structure(s), and Django handles the integration.

It is advisable to define separate models for different programming objects. This allows for sensible grouping of data/information. But other aspects of a website can also be represented by models, for example, a drop down list – this avoids hard coding available choices in the website code.

Relationships between models must also be defined, and Django allows three types of relationships: one to one, one to many, and many to many.

Conventionally, models are defined in a models.py file and “implemented as subclasses of `django.db.model.Model`.”

Models include fields, metadata, and methods.

**Fields:**

Models can have any number of fields, which each represent a data column in a database table.

“The field types are assigned using specific classes, which determine the type of record that is used to store the data in the database, along with validation criteria to be used when values are received from an HTML form (i.e. what constitutes a valid value). The field types can also take arguments that further specify how the field is stored or can be used.”

A field name can be used in queries and templates to reference that field. A label can be specified to expand the field name (verbose_name argument) to be more human readable. Fields have types, which are similar to programming data types, but more varied and specific.

**Metadata:**

Metadata for a model can be specified inside a Meta class.

“One of the most useful features of this metadata is to control the default ordering of records returned when you query the model type. You do this by specifying the match order in a list of field names to the ordering attribute.”

Metadata also allows controlling access permissions.

**Methods:**

At least the `__str__()` method should be declared in every model class, which returns a human readable string representing a model object.

`get_absolute_url()` is another common and useful method “which returns a URL for displaying individual model records on the website (if you define this method then Django will automatically add a "View on Site" button to the model's record editing screens in the Admin site).”

Model classes can be used to create, update, and delete records, and also run queries.

To create a record, define an instance of a model and call `save()`:

```
record = MyModel(my_field_name=“Instance1”)
record.save()
```

Fields in the record can be accessed using the dot operator. Anytime the record is updated, `record.save()` must be called afterwards.

Search for records using the model `objects` attribute.

To get all records of a model, run `objects.all()`, and then use Django’s `filter()` method with parameters to filter results.

“In some cases, you'll need to filter on a field that defines a one-to-many relationship to another model (e.g. a ForeignKey). In this case, you can "index" to fields within the related model with additional double underscores. So for example to filter for books with a specific genre pattern, you will have to index to the name through the genre field.”

“There is a lot more you can do with queries, including backwards searches from related models, chaining filters, returning a smaller set of values, etc.”

**Django Admin**

https://developer.mozilla.org/en-US/docs/Learn/Server-side/Django/Admin_site

Django’s admin application allows you to test your models. You need to register your models with the admin application. Then it’s possible to create a new superuser, log into the site, and create instances of models for testing.

To register a model, go to the admin.py file and add the following code: `admin.site.register(<Model_Name>)`

To create a superuser that has permission to access all parts of the site, inside the directory that houses manage.py, run: `python3 manage.py createsuperuser` and provide a login name and strong password when prompted. Then restart the development server and go to the /admin endpoint of the site. There will be an interface for viewing/editing all models and associated records.


## Reading 28

**Django Forms**

https://developer.mozilla.org/en-US/docs/Learn/Server-side/Django/Forms

“Forms are also a relatively secure way of sharing data with the server, as they allow us to send data in POST requests with cross-site request forgery protection.”

An HTML form is defined inside of `<form>…</form>` tags and contains one or more input tags of type submit, e.g. `<input type=“submit” value=“OK”>`

When Django handles forms, “the view gets a request, performs any actions required including reading data from the models, then generates and returns an HTML page (from a template, into which we pass a context containing the data to be displayed). What makes things more complicated is that the server also needs to be able to process data provided by the user, and redisplay the page if there are any errors.”

Django form steps:

1. Display default form (not filled out yet, though can have pre-populated fields) – at this stage, the form is “unbound,” meaning it doesn’t have any user-associated data

2. Take data from a submit request and bind it to form

3. Clean and validate data

4. Redisplay form if any entered data was invalid

5. Once all data is valid, perform actions

6. After actions finish, redirect user to another page


Django has a Form class that can generate HTML and clean and validate data.

In Django, making a form with the Form class is similar to creating a model, since data types and validation must be enforced.

Form data gets stored in an application’s application directory inside the forms.py file. New form classes extend `forms.Form`. Form classes look similar to models and include field names that are assigned data types (data types are also similar to model data types). Additionally, there are many arguments that most fields can take (see link for list).

Django also helps with validation. “The easiest way to validate a single field is to override the method `clean_<fieldname>()` for the field you want to check.”

Default cleaning of data can be performed by `self.cleaned_data[‘<field>’]`

A view renders the default form and then re-renders it as necessary – so the view needs to know how many times it’s been called (in case of a re-render).

“For forms that use a POST request to submit information to the server, the most common pattern is for the view to test against the POST request type (if request.method == 'POST':) to identify form validation requests and GET (using an else condition) to identify the initial form creation request. If you want to submit your data using a GET request, then a typical approach for identifying whether this is the first or subsequent view invocation is to read the form data (e.g. to read a hidden value in the form).”

See link for standard code example.

Us the `pk` argument to pass in a primary key and the `get_object_or_404()` method to get an instance of a model object. Check if it’s a POST request – if not, create the default form and use the `render()` method and pass in a template and context to display it. If it is a POST request, create a form object and bind the data, which can then be validated. If the data is not valid, render() gets called with error messages. Finally, once the form is handled, the view redirects to another page.

Access to a form view can be restricted to logged in users. Use `@login_required` and `@permission_required` decorators.

Create the HTML form as a template. “The `{% csrf_token %}` added just inside the form tags is part of Django's cross-site forgery protection.”

`{% csrf_token %}` should be added to every Django template that uses POST.

Use the `{{ form }}` template variable with relevant methods to render the form.

“It is also possible to have complete control over the rendering of each part of the form, by indexing its properties using dot notation.”

“However, if you just need a form to map the fields of a single model then your model will already define most of the information that you need in your form: fields, labels, help text and so on. Rather than recreating the model definitions in your form, it is easier to use the ModelForm helper class to create the form from your model. This ModelForm can then be used within your views in exactly the same way as an ordinary Form.”

Add the `Meta` class to create a form this way (see example code). This class can be used to override model fields that should be changed for the form.

“Django abstracts much of this "boilerplate" for you, by creating generic editing views for creating, editing, and deleting views based on models. Not only do these handle the "view" behavior, but they automatically create the form class (a ModelForm) for you from the model.”

The FormView class is an intermediate option between coding the full form vs. using generic editing views.

The generic editing views can be used to implement create, edit, and delete functionality. Write view classes that extend `CreateView`, `UpdateView`, and `DeleteView`, respectively.

“For the "create" and "update" cases you also need to specify the fields to display in the form (using the same syntax as for ModelForm).”


## Reading 29

**Django Custom User Model**

https://learndjango.com/tutorials/django-custom-user-model

Django has a built-in user model for authentication, though it’s recommended to use custom user models instead for greater flexibility.

Note that the official Django example for a custom user is not what most experts recommend.

Create a Django project but don’t run migrate until after creating the custom user model.

Two options for classes to extend: `AbstractUser` and `AbstractBaseUser`

`AbstractBaseUser` is much more work, so use `AbstractUser`.

4 steps for creating custom user model:

- update `django_project/settings.py`
- create a new `CustomUser` model
- create new `UserCreation` and `UserChangeForm`
- update the admin

In settings.py, set `AUTH_USER_MODEL` to `<app_name>.CustomUser`

Add a new to models.py:

```
class CustomUser(AbstractUser):
```

Create a forms.py file in the application:

```
from django import forms
from django.contrib.auth.forms import UserCreationForm, UserChangeForm

from .models import CustomUser

class CustomUserCreationForm(UserCreationForm):

    class Meta:
        model = CustomUser
        fields = ("username", "email")

class CustomUserChangeForm(UserChangeForm):

    class Meta:
        model = CustomUser
        fields = ("username", "email")
```

Update admin.py:

```
from django.contrib import admin
from django.contrib.auth.admin import UserAdmin

from .forms import CustomUserCreationForm, CustomUserChangeForm
from .models import CustomUser

class CustomUserAdmin(UserAdmin):
    add_form = CustomUserCreationForm
    form = CustomUserChangeForm
    model = CustomUser
    list_display = ["email", "username",]

admin.site.register(CustomUser, CustomUserAdmin)
```

Then run `makemigrations` and `migrate` to create a database that uses the custom user model.

Create a superuser to test.

In order to create a homepage with log in and log out links, add the following to TEMPLATES in settings.py:

`"DIRS": [BASE_DIR / "templates"],`

In the same file, set redirect links:

```
LOGIN_REDIRECT_URL = "home"
LOGOUT_REDIRECT_URL = "home"
```

Create a templates folder, and inside it, create a registration folder. Inside, create a signup.html file.

Create these four templates:

```
(.venv) % touch templates/registration/login.html
(.venv) % touch templates/registration/signup.html
(.venv) % touch templates/base.html
(.venv) % touch templates/home.html
```

Templates:

```
<!-- templates/home.html -->
{% extends "base.html" %}

{% block title %}Home{% endblock %}

{% block content %}
{% if user.is_authenticated %}
  Hi {{ user.username }}!
  <p><a href="{% url 'logout' %}">Log Out</a></p>
{% else %}
  <p>You are not logged in</p>
  <a href="{% url 'login' %}">Log In</a> |
  <a href="{% url 'signup' %}">Sign Up</a>
{% endif %}
{% endblock %}
```

```
<!-- templates/registration/login.html -->
{% extends "base.html" %}

{% block title %}Log In{% endblock %}

{% block content %}
<h2>Log In</h2>
<form method="post">
  {% csrf_token %}
  {{ form.as_p }}
  <button type="submit">Log In</button>
</form>
{% endblock %}
```

```
<!-- templates/registration/signup.html -->
{% extends "base.html" %}

{% block title %}Sign Up{% endblock %}

{% block content %}
<h2>Sign Up</h2>
<form method="post">
  {% csrf_token %}
  {{ form.as_p }}
  <button type="submit">Sign Up</button>
</form>
{% endblock %}
```

Inside urls.py:

```
urlpatterns = [
    path("", TemplateView.as_view(template_name="home.html"), name="home"),
    path("admin/", admin.site.urls),
    path("accounts/", include("accounts.urls")),
    path("accounts/", include("django.contrib.auth.urls")),
]
```

Create a urls.py folder in the application and add:

```
from django.urls import path
from .views import SignUpView

urlpatterns = [
    path("signup/", SignUpView.as_view(), name="signup"),
]
```

Include the following in views.py:

```
from django.urls import reverse_lazy
from django.views.generic.edit import CreateView

from .forms import CustomUserCreationForm

class SignUpView(CreateView):
    form_class = CustomUserCreationForm
    success_url = reverse_lazy("login")
    template_name = "registration/signup.html"
```

Once the custom user model is set up, you can add extra fields anytime (see Django docs).

DjangoX includes a custom user model by default.

Django for beginners: https://djangoforbeginners.com/


**DjangoX**

https://github.com/wsvincent/djangox

“DjangoX can be installed via Pip, Pipenv, or Docker.” See link for installs.

Docker with PostgreSQL can be used (update DATABASES in settings.py), and update INTERNAL_IPS.

Add environment variables (environs recommended)

Add gunicorn as production web server

Update EMAIL_BACKEND and connect to mail provider

Can make admin more secure (see link)


**Abstract User, User Profile and Signals in Django**

https://www.youtube.com/watch?v=EudKs1HPUfE

Adding extra fields to a user model:

For new project, simple – just define a user class derived from AbstractUser class and update AUTH_USER_MODEL in settings file
You should always do this first when starting a Django project

Then can run manage.py migrate

After running migrate, you need to take different steps to extend the user model. You need to add a new model in your app – add one-to-one relationship, create post_save signal, load signal into app.



## Reading 30

**Hash Table Cheat Sheet**

https://codefellows.github.io/common_curriculum/data_structures_and_algorithms/Code_401/class-30/resources/Hashtables.html

https://www.hackerearth.com/practice/data-structures/hash-tables/basics-of-hash-tables/tutorial/

**Overview:**

- key/value pair input
- hash table – initialize array of empty linked lists
- apply hash function to key
- modulo result using array length
- store key/value pair at end of the linked list located at that index
- time complexity would be O(1) without collisions, but O(n) if every hash collides

**Methods:**

get() – get value associate with provided key\
set() – assign key/value pair to hash table\
hash() – return index for given input\
has() – check hash() index, if key is there return True, else False\
keys() – return array of stored keys

**Hash Functions:**

Different hashing functions can be used. Hash function goals:

- Easy to compute
- Uniform distribution of outputs

Example: For string keys, take each Unicode character value, multiply by its index in the string, and sum these values. This is the hash function. Then modulo by the array length to find the index value.

**Handling Collisions:**

- Easiest way is for each bucket to be initialized as an empty linked list. When adding a new key/value pair, go to the array index provided by the hash computation. If the linked list head is None, add key/value pair. Otherwise, traverse linked list at given index to the end, then add key value pair. (Both key and value must be stored for retrieval, in case multiple key/value pairs are stored in same bucket).

- Alternatives: Linear probing, quadratic probing (a probe sequence is specified for next indices to check in case the one provided by the hash function is occupied)


## Reading 31

**Beginner’s Guide to Docker**

https://wsvincent.com/beginners-guide-to-docker/

Docker containers isolate and run applications, making them highly portable. Production environments can be emulated locally.

“Docker is really just Linux containers which are a type of virtualization.”

Virtual machines are “complete copies of a computer system from the operating system on up.”

The downsides of virtual machines are size and speed, so Linux containers are a lightweight alternative, since they use the existing operating system.

Docker is essentially an implementation of Linux containers.

Python programmers use virtual environments to isolate Python applications, but “virtual environments can only isolate Python packages. They still rely on a global, system-level installation of Python.” So the version of Python that the application points to exists outside the virtual environment. Additionally, production databases and other services can’t be run inside a virtual environment, so Docker is a more flexible option.

Images and containers are two key concepts in Docker. “An image is a snapshot in time of what a project contains. A container is a running instance of the image.”

There are official Docker images, but to create a custom one, use a `Dockerfile`. Use `docker-compose.yml` to run containers.

“There are a large number of official images available on Docker Hub for common software like different flavors of Linux, programming languages, and so on.”

Creating an Image for Python:

- create a local directory
- Define the image with a Dockerfile (this is similar to Pipenv or requirements.txt files, since it lists all the requirements needed to build the image)
- On Mac, use `touch Dockerfile` to create a new Dockerfile
- Add the following line:
```
# Dockerfile
FROM python:3.7-alpine
```
(FROM imports a base image and must be the first command since Dockerfiles are read top to bottom – alpine is minimum needed to run Python)

- Run `docker image build .`
- After build completes, a hash id for the image will be provided

To confirm the new image was built, run `docker image ls` to list all Docker images

Images consist of layers. Base layer is usually a flavor of Linux (e.g. alpine). Each image is immutable for consistency. Also, “Docker caches the steps in a Dockerfile to speed up subsequent builds.” This is why order matters in a Dockerfile and changing code should go at the end.

Containers:

Dockerfiles are a list of image instructions and docker-compose.yml is a list of container instructions.

To dockerize a Django project, create a Dockerfile, which will replace the local development environment.

```
touch Dockerfile
touch docker-compose.yml
```

The following Dockerfile commands each create a new layer: `RUN`, `COPY`, `ADD`

Example Dockerfile:

```
# Dockerfile

# Python version
FROM python:3.7-alpine

# Set environment variables
ENV PYTHONDONTWRITEBYTECODE 1
ENV PYTHONUNBUFFERED 1

# Set work directory
WORKDIR /code

# Install dependencies
COPY Pipfile Pipfile.lock /code/
RUN pip install pipenv && pipenv install --system

# Copy project
COPY . /code/
```

The first environment variable PYTHONDONTWRITEBYTECODE removes .pyc files from the container for optimization. The second env variable PYTHONBUFFERED buffers output so that it looks right inside of Docker.

`WORKDIR/code` sets the default directory inside Docker so that you can run a command like `python3 manage.py runserver` without specifying the directory.

“The Pipfile contains information on our software packages so we copy that over, too. (Technically we could use COPY Pipfile . and because of the WORKDIR setting it would still go in the /code folder!)”

Next the file installs Pipenv – the `--system` tag ensures the packages are available throughout the container instead of in a virtual environment (Note: the Docker container is a virtual environment).

Example `docker-compose.yml`:

```
# docker-compose.yml
version: '3.7'

services:
  web:
    build: .
    command: python /code/manage.py runserver 0.0.0.0:8000
    volumes:
      - .:/code
    ports:
      - 8000:8000
```

This sets up a service to run in the container – multiple services can be run inside a single container. One use case would be adding a database (currently this is just a web service).

This tells Docker to build the current directory, run `runserver` on startup, which arts the Django server, sync `volumes` to the local directory, and “expose port 8000 which is Django’s default so the container will expose it, too.”

Now to both build the image and run the container, can just run one command: `up –build`

The Django project will now run in the container.

Containers run an instance of an image and `docker-compose.yml` controls how to run the container – can link the local filesystem to the container via `volumes`. Adding databases is more complicated.


**Django for APIs - Library Website**

https://djangoforapis.com/library-website-and-api/

“Django REST Framework works alongside the Django web framework to create web APIs. We cannot build a web API with only Django Rest Framework. It always must be added to a project after Django itself has been installed and configured.”

“The most important takeaway is that Django creates websites containing webpages, while Django REST Framework creates web APIs which are a collection of URL endpoints containing available HTTP verbs that return JSON.”


## Reading 32

**DRF Permissions**

https://www.django-rest-framework.org/api-guide/permissions/

Authentication, throttling, and permissions together determine access to resources.

Permission checks are run at the start of a view, typically using authentication info in `request.user` and `request.auth`.

“Permissions are used to grant or deny access for different classes of users to different parts of the API.”

The simplest REST framework permission is the `IsAuthenticated` class

`IsAuthenticatedOrReadOnly` allows access to authenticated users, and read-only access to unauthenticated users, so less strict.

“Permissions in REST framework are always defined as a list of permission classes.”

The permissions list gets checked before running the main body of a view.

HTTP 403 Forbidden response – request was authenticated but permission was denied, or the request was not authenticated and the highest priority authentication class does not use `WWW-Authenticate` headers\
HTTP 401 Unauthorized response – request was not authenticated, and highest priority authentication class uses `WWW-Authenticate` headers

REST framework supports object-level permissions, which determine whether a user can access an object (usually a model instance).

“Object level permissions are run by REST framework's generic views when `.get_object()` is called.”

In order to implement object level permissions on custom views (or when overriding `get_object` method), call `.check_object_permissions(request, obj)` on the view.

```
def get_object(self):
    obj = get_object_or_404(self.get_queryset(), pk=self.kwargs["pk"])
    self.check_object_permissions(self.request, obj)
    return obj
```
Only the `DjangoObjectPermissions` class checks object permissions, so when using other permission classes to check object permissions, they must be subclassed.

“For performance reasons the generic views will not automatically apply object level permissions to each instance in a queryset when returning a list of objects.”

The queryset should also be filtered when using object level permissions.

Object level permissions are not applied when creating objects – “In order to restrict object creation you need to implement the permission check either in your Serializer class or override the perform_create() method of your ViewSet class.”

Default permission can be set globally:

```
REST_FRAMEWORK = {
    'DEFAULT_PERMISSION_CLASSES': [
        'rest_framework.permissions.IsAuthenticated',
    ]
}
```

Alternatively, can set per-view authentication using `APIView` class or `@api_view` decorator.

Three methods for case-by-case access restriction: `queryset`/`get_queryset()`, `permission_classes`/`get_permissions()`, `serializer_class`/`get_serializer()`


## Reading 33

**JSON Web Tokens**

https://jwt.io/introduction/

JSON Web Token (JWT) is an open standard for securely transferring data as a JSON object. It is secure because the data is digitally signed, allowing it to be verified. Signing happens with a secret or a public/private key, though they can also be encrypted.

Signed tokens are for verification, encryption is for information hiding.

JWT’s can be used for authorization – once a user is logged in, each request will include a JWT.

A JWT has 3 parts: Header, Payload, Signature and takes the form `xxxxx.yyyyy.zzzzz`

Header:

The header usually has 2 parts: type of token (JWT), and signing algorithm (e.g., HMAC SHA256 or RSA)

Payload:

The payload contains the claim, which usually provides info about the user. There are 3 types of claims: registered, public, private. Do not put secure info in the header or payload – it can be read by anyone.

Signature:

The signature is collectively the encoded header, encoded payload, a secret, and the algorithm specified in the header, which is all signed.

The final JWT is three Base64-URL strings separated by dots which can be used in HTML and HTTP environments and are more compact than XML-base standards.

jwt.io/#debugger-io lets you generate, decode, and verify JWT’s.

When a user logs in, a JWT gets returned. For security, tokens should not be stored longer than required and should not be stored in the browser.

“Whenever the user wants to access a protected route or resource, the user agent should send the JWT, typically in the Authorization header using the Bearer schema.”

“This can be, in certain cases, a stateless authorization mechanism. The server's protected routes will check for a valid JWT in the Authorization header, and if it's present, the user will be allowed to access protected resources. If the JWT contains the necessary data, the need to query the database for certain operations may be reduced, though this may not always be the case.”

JWT tokens sent through HTTP headers should be kept small or some servers won’t accept them.

“If you are trying to embed too much information in a JWT token, like by including all the user's permissions, you may need an alternative solution, like Auth0 Fine-Grained Authorization.”

“If the token is sent in the Authorization header, Cross-Origin Resource Sharing (CORS) won't be an issue as it doesn't use cookies.”

Info in signed tokens can be read by others but not changed, so this should not contain secret info.


**DRF JWT Authentication**

https://simpleisbetterthancomplex.com/tutorial/2018/12/19/how-to-use-jwt-authentication-with-django-rest-framework.html

JWT is “is an authentication strategy used by client/server applications where the client is a Web application using JavaScript and some frontend framework like Angular, React or VueJS.”

A JWT is an authorization token that should be included in all requests. A JWT is granted when a username and password are provided, and an access token and refresh token are returned. The access token lasts about 5 minutes, the refresh token about 24 hours (both are customizable).

JWT: header.payload.signature

Example Header:

```
{
  "typ": "JWT",
  "alg": "HS256"
}
```

Example Payload:

```
{
  "token_type": "access",
  "exp": 1543828431,
  "jti": "7f5997b7150d46579dc2b49167097e7b",
  "user_id": 1
}
```

The signature is created using header base64, payload base63, and the application’s secret key. This is why the secret key should be kept secret. With every request, the signature is verified, and if any information in the header or payload was changed by the client, the signature will register as invalid.

For implementation, use the `djangorestframework_simplejwt library.

`pip install djangorestframework_simplejwt`

See tutorial for configuring settings.

Go to /api/token/ endpoint (only accepts POST requests) to authenticate and obtain a token.

The response body is two tokens, an access token and a refresh token.

Store both client side, usually in localStorage.

To access protected backend views (API endpoints that require authentication), include the access token in all header requests.

After an access token expires, make a POST request to the /api/token/refresh/ endpoint. A new access token is returned (the refresh token is still valid for a while). When the refresh token eventually expires, a new authentication needs to be performed.


**Django Runserver Is Not Your Production Server**

https://vsupalov.com/django-runserver-in-production/

Do not use the Django server in a production setting – it is not secure and has not been test for performance. Instead use a production stack which includes a dedicated web server, such as Nginx, and an application server, such as Gunicorn (uses WSGI specification).

A Django app does not run like a server – instead, the application server calls a function inside the uwsgi.py file. This function gets a Python object as a request, it calls the Django code, and generates a response object which gets passed to the WSGI server, which translates it into an HTTP response for the web server.


## Reading 34

**Django Settings Best Practices**

https://djangostars.com/blog/configuring-django-settings-best-practices/

Django Issues:

- Different settings for different environments
- Sensitive data (e.g. SECRET_KEY)
- Human error when sharing settings
- Logic rather than key/value pairs in settings.py

Different Approaches:

“There is no built-in universal way to configure Django settings without hardcoding them.” But there are approaches and recommendations.

One approach is to put all environment-specific settings in a `settings_local.py` file, which is in the .gitignore. The drawback is that some Django environment settings can be lost since not on GitHub. Inculde a `settings_local.example` file in GitHub to share default Django configurations.

An extension of this approach is to create a separate settings file for each environment – allows you to keep all configurations on GitHub. Make a `settings` package with this file structure:

settings
- __init__.py
- base.py
- ci.py
- local.py
- staging.py
- production.py
- qa.py

Include an additional parameter when running: `python manage.py runserver –settings=settings.local`

To deal with sensitive data, can use environment variables.

12 Factors for how to build distributed web-apps:

1. Codebase
2. Dependencies
3. Config
4. Backing services
5. Build, release, run
6. Processes
7. Port binding
8. Concurrency
9. Disposability
10. Dev/prod parity
11. Logs
12. Admin processes

Recommended to store configuration in the environment in order to have strict separation of config from code.

“Instead of splitting settings by environments, you can split them by the source: Django, third- party apps (Celery, DRF, etc.), and your custom settings.”

Naming rules:

- Use meaningful settings names
- Use project name prefix for custom settings
- Comment settings

Django Settings Best Practices:

- “Keep settings in environment variables”
- “Write default values for production configuration (excluding secret keys and tokens)”
- “Don’t hardcode sensitive settings, and don’t put them in Version Control System”
- “Split settings into groups: Django, third-party, project”
- “Follow naming conventions for custom (project) settings”

“Using the environment variables approach, you can easily switch from a monolith to microservice architecture, wrap your project in Docker containers, and deploy it in any VPS or Cloud hosting platform such as: Amazon, Google Cloud, or your own Kubernetes cluster.”

**SSH Tutorial**

https://www.hostinger.com/tutorials/ssh-tutorial-how-does-ssh-work

SSH (Secure Shell Protocol) offers a secure method for remote access.

“SSH, or Secure Shell Protocol, is a remote administration protocol that allows users to access, control, and modify their remote servers over the internet.”

“Any Linux or macOS user can SSH into their remote server directly from the terminal window. Windows users can take advantage of SSH clients like Putty.  You can execute shell commands in the same manner as you would if you were physically operating the remote computer.”

SSH uses 3 encryption technologies: Symmetric, Asymmetric, Hashing

Symmetric Encryption (aka shared key/secret) – a secret key is used for both encryption and decryption by both the client and the host. A key exchange algorithm is used that does not require the key to be transmitted between the client and host. A secret token is generated for each SSH session before client authentication – then all packets are encrypted with the private key.

Asymmetric Encryption – uses separate keys for encryption and decryption (a public and private key)

One-Way Hashing – these functions are never meant to be decrypted – if a client has the correct input, they can hash it and determine that its value is correct. “SSH uses hashes to verify authenticity of messages.”

SSH uses a client-server model and operates on TCP port 22 by default.

For SSH connection, the client initiates a TCP handshake with the server, creating a secured symmetric connection and verifying identity of the server. Client provides authentication credentials. Then both parties use the Diffie-Hellman Key Exchange algorithm to create a symmetric key.



## Reading 35

**Graphs Cheat Sheet**

Parts:

- Vertex/Node
- Edge – connects vertices
- Neighbors – a vertex’s adjacent vertices
- Degree of a vertex – number of edges

Types:

Directed Graph/Digraph – every edge is directed\
Undirected graph – edges are bidirectional\
Complete – all vertices are connected to all other vertices\
Connected – there is a path of edges to every vertex\
Disconnected – there can be standalone vertices or islands of vertices\
Acyclic – no cycles\
Cyclic – has cycles where a path can loop back on itself\
DAG – Directed Acyclic Graph, can be represented as a tree\
Sparse graph – few connections\
Dense graph – many connections\
Weighted graph – edges have associated weights\

Representations:

Adjacency Matrix – matrix with vertices listed along rows and columns, 1’s denote edges, 0’s denote no edges

Adjacency List (multiple representations):  
- array of linked lists – each entry is a vertex, the linked list nodes are its neighbors
- hashmap – key is a node, value is an array of its neighbors\
Note: if it is a weighted graph, store the weights (vertex, weight)

Breadth First Traversal

 - define a function that takes a starting node
- declare an empty queue
- declare an empty set to keep track of visited nodes
- enqueue the starting node
- while there are nodes in the queue, dequeue the first node, add it to visited, enqueue each unvisited neighbor

Depth First Traversal

- define a function that takes a starting node
- declare an empty stack
- declare an empty set to keep track of visited nodes
- push starting node to stack
- while there are nodes in the stack, pop the first node, add it to visited, puch each unvisited neighbor

## Reading 36

**Whiteboarding Advice**

https://hackernoon.com/the-best-whiteboard-interview-advice-i-ever-received-3ebbfa72e4a

Advice for whiteboards: Communicate

– restate the question and confirm you fully understand what they’re asking for
- ask about edge cases, ask if there are any test cases that the function should pass (interviewer might be expecting this)
- write pseudocode (allowed to ask interviewer if it makes sense)
- write the code and ask if it looks good (you should usually be able to ask interviewer for syntax or method names)
- if you get stuck, you can say so and see if a hint might be available
- talking to hr before interview, can ask if there will be a coding interview and what you should prepare – they may tell you style of questions and other info

**7 Tips for Software Interviews:**

https://medium.com/@steve_45636/6-tips-to-ace-a-whiteboard-programming-interview-f06c1b378bc6

1. Take a few minutes – you can tell the interviewer you’re going to silently think for a few minutes, and then start talking

2. Write down the solution steps

3. Write pseudocode first

4. Don’t sweat the small stuff – if you forget something small (e.g. method name), you can say you would look it up

5. Be humble and respectful

6. Come prepared – recommended: Cracking the Coding Interview 

7. Review your work if there’s time – check for algorithmic efficiency and correctness


## Reading 37

**ES6 Syntax and Feature Overview**

https://www.taniarascia.com/es6-syntax-and-feature-overview/

“ECMAScript 2015, also known as ES6, introduced many changes to JavaScript. Here is an overview of some of the most common features and syntactical differences, with comparisons to ES5 where applicable.”

Variables:

`var` has function scope, hoisting and can be re-declared, `let` and `const` have block scope and cannot be hoisted or redeclared.

Arrow Functions:

“Arrow functions do not have their own `this`, do not have prototypes, cannot be used for constructors, and should not be used as object methods.”

Template Literals:

Backticks surround strings, and put variables inside curly braces

Multi-line Strings:

With template literals, strings can span multiple lines without being concatenated.

Implicit Returns:

Specifically in arrow functions without a block function body

Key/Property Shorthand:

When declaring an object literal, if the value has the same name as the property, no longer need to write `a: a,` can just write `a,`

Method Definition Shorthand:

`function` keyword no longer needed for assigning methods to an object

Destructuring:

Destructuring introduced

More Concise Array Iteration:

`for (let i of arr) {}`

Default Parameters:

Functions can be initialized with default parameters 

Spread Syntax:

Introduction of spread operator to expan an array – can also be used in function arguments

Classes/Constructor Functions:

“ES6 introduces the class syntax on top of the prototype-based constructor function.”

Inheritance:

`extends` keyword creates a subclass

Modules – Export/Import:

“Modules can be created to export and import code between files.”

Promises/Callbacks:

Introduction of promises in place of chaining callbacks


**React**

https://reactjs.org/docs/hello-world.html

Most basic React example:

```
const root = ReactDOM.createRoot(document.getElementById('root'));
root.render(<h1>Hello, world!</h1>);
```

JSX is a syntax extension to JavaScript that looks like a template language but can do JavaScript logic, and it’s recommended for use with React to describe what the UI should look like.

JSX produces what are called React elements, which can be rendered to the DOM.

Note: JSX is not required. “Each JSX element is just syntactic sugar for calling React.createElement(component, props, ...children). So, anything you can do with JSX can also be done with just plain JavaScript.”

“React embraces the fact that rendering logic is inherently coupled with other UI logic: how events are handled, how the state changes over time, and how the data is prepared for display.
Instead of artificially separating technologies by putting markup and logic in separate files, React separates concerns with loosely coupled units called “components” that contain both.”

JSX prevents injection attacks so it’s safe to embed user input in JSX.

“Babel compiles JSX down to React.createElement() calls.”

`React.createElement()` does some basic error checking and then creates an object with a tag type, props, className, and children. These objects are React elements, and React uses them to build and update the DOM.

Elements are the smallest React building block and describe what should appear on screen.

“Unlike browser DOM elements, React elements are plain objects, and are cheap to create.”

(Note: don’t confuse React elements with React components – components are made of elements)

`<div id=“root”></div>` is a root DOM node, and everything inside it will be managed by React DOM (there can be one or multiple root DOM nodes in an application).

Rendering a React Element:

- Get the DOM element with id of ‘root’ using `document.getElementById`
- Pass this DOM element into ReactDOM.createRoot() and store result in a variable `root` (`createRoot` creates a root to display React components inside a browser DOM node)
- Pass React elements to root.render() to render them

```
const root = ReactDOM.createRoot(
  document.getElementById('root')
);
const element = <h1>Hello, world</h1>;
root.render(element);
```

“React elements are immutable. Once you create an element, you can’t change its children or attributes. An element is like a single frame in a movie: it represents the UI at a certain point in time.”

Most React apps only need to call `root.render()` once since code is encapsulated as stateful components.

“React DOM compares the element and its children to the previous one, and only applies the DOM updates necessary to bring the DOM to the desired state.”

“Conceptually, components are like JavaScript functions. They accept arbitrary inputs (called “props”) and return React elements describing what should appear on the screen.”

The simplest way to define a component is using a JavaScript function that accepts a single props argument and returns a React element. ES6 classes can also be used to define components.

While React elements can represent DOM tags, they can also represent user-defined components, in which case JSX attributes and children are passed to the component as a props object.

A component may never modify its own props – a rule in React is that “components must act like pure functions with respect to their props.”

Instead, “state allows React components to change their output over time.”

Use a constructor to hold state in React class components, and pass props to the constructor.

```
constructor(props) {
	super(props);
	this.state = {};
}
```

For applications with many components, lifecycle methods are used to destroy components when no longer needed in order to free up resources.

State should not be modified directly, instead use `setState()`.

Events are handled similarly in React but with some different syntax.

**Tailwind**

Advantage over regular CSS inline styles – utilities provide a design system, responsive design, and access to hover, focus, and other states.

For maintainability, components and partials can be extracted.

**Next.js**

Next.js is a React Framework that helps with production and optimizations. Next.js lets you decide if you want to render parts of your application client-side or server-side, and it gives a lot of flexibility and scalability and better performance.



## Reading 38

**React - Conditional Rendering**

https://reactjs.org/docs/conditional-rendering.html

You can create React components and conditionally render them when appropriate.

Conditional rendering can be done with `if` statements, or for shorter syntax, use inline conditions in JSX. To do this, place JS expressions in curly braces - e.g., use the && operator.

```
{unreadMessages.length > 0 &&
<h2>
	you have {unreadMessages.length} unread messages.
</h2>
}
```

Alternatively, inline conditional rendering can be done using a ternary operator.

```
<div>
The user is <b>{isLoggedIn ? ‘Currently’ : ‘not’}</b> logged in.
</div>
```

```
<div>
      {isLoggedIn
        ? <LogoutButton onClick={this.handleLogoutClick} />
        : <LoginButton onClick={this.handleLoginClick} />
      }
    </div>
```

**Lists and Keys**

Using the map() function, you can convert arrays into <li> elements. You should always include a key for each list item, which is a string that lets react identify the element and track any changes. Data IDs are often used as keys (indices are not recommended as keys).

“Keys only make sense in the context of the surrounding array.
For example, if you extract a ListItem component, you should keep the key on the <ListItem /> elements in the array rather than on the <li> element in the ListItem itself.”

Keys don’t need to be globally unique.


**Forms**

“HTML form elements work a bit differently from other DOM elements in React, because form elements naturally keep some internal state.”

While the default HTML form submission behavior works, it usually makes sense to have a JS handler function that submits the form and can access the user input data - the standard way to do this in React is using “controlled components.”

HTML form element maintain their own state, but in React, use state. To make a controlled component, attach an onChange listener to a form element. The handler function updates the component state to whatever the user input. Then place an onSubmit handler function on the encompassing form element which gets data out of state.

See docs for usage of specific tags.

“When you need to handle multiple controlled input elements, you can add a name attribute to each element and let the handler function choose what to do based on the value of event.target.name.”

ES6 computed property name syntax can be used to update the state key for a specific input name.

**Lifting State**

When multiple components need to share the same state, it’s recommended to lift state to the closest common ancestor.

When a lower component needs to change the shared state, it’s usually recommended to make it a controlled component (similar to forms). The lower component accepts a value prop and a function prop from the higher component. The lower can then call this.props.handler to update state in the higher component.

“There should be a single “source of truth” for any data that changes in a React application. Usually, the state is first added to the component that needs it for rendering. Then, if other components also need it, you can lift it up to their closest common ancestor. Instead of trying to sync the state between different components, you should rely on the top-down data flow.”


**Composition vs. Inheritance**

Composition is preferred to inheritance.  Together with props, components obviate the need for inheritance.

The special `children` prop passes child elements directly as output.

When one component is considered a special case of another component, rather than use inheritance, use composition “where a more “specific” component renders a more “generic” one and configures it with props.”


**Thinking in React**

Use the single responsibility principle when deciding what should be a component.

Once components are mocked, determine their hierarchy. 

It’s recommended to first build the app that takes in the data model and renders the UI but does not have interactivity (so a static app).

Apps can be built top-down or bottom-up (the former is usually preferred for simple apps and the latter for complex apps).

The component at the top of the hierarchy takes the data model as a prop.

The two types of model data are props and state.

To make the UI interactive, need to be able to change data, which requires using state. In order to be DRY, determine minimum number of mutable states.

To determine if data should be in state, ask these three questions:

1. Is it passed via props? Then not state.
2. Is it unchanging? Then not state.
3. Can it be computed? Then not state.

Next identify which component(s) should hold state.


## Reading 39

**Next.js**

https://nextjs.org/learn/basics/create-nextjs-app

Next.js is a React Framework that solves a number of problems:

- bundling and transforming code
- production optimizations (e.g., code splitting)
- option to statically pre-render some pages
- server-side and client-side rendering
- server-side code

Next.js development server has Fast Refresh, so no refresh needed following changes.

Next.js has an integrated file routing system for navigating between pages.

“In Next.js, a page is a React Component exported from a file in the pages directory. Pages are associated with a route based on their file name.”

When you create a js file in the pages directory, the path to the file becomes the URL path.

To link between pages use the Link component next/link. <Link> does client-side navigation and accepts props.

“Client-side navigation means that the page transition happens using JavaScript, which is faster than the default navigation done by the browser.”

“Next.js automatically optimizes your application for the best performance by code splitting, client-side navigation, and prefetching (in production).”

Next.js supports CSS and Sass.

Next.js serves static assets under the public directory.

Use next/image for optimized images.

“In addition to metadata, scripts that need to load and execute as soon as possible are usually added within the <head> of a page… using a regular HTML <script> element.”

2 CSS files – global.css and Home.module.css.

CSS modules allow for locally scoping CSS.

CSS modules are intended for component-level styles. For global CSS use the global CSS file.


**React Context**

https://www.freecodecamp.org/news/react-context-for-beginners/

Context allows sharing of state without props. Helps avoid props drilling.

4 steps for using React Context

```
1. Create context using the createContext method.
2. Take your created context and wrap the context provider around your component tree.
3. Put any value you like on your context provider using the value prop.
4. Read that value within any component by using the context consumer.
```

“Another way of consuming context became available in React 16.8 with the arrival of React hooks. We can now consume context with the useContext hook.”


## Reading 41

**Next.js – Dynamic Routes**

https://nextjs.org/learn/basics/dynamic-routes

You need dynamic routes when a URL depends on the page data.

“Next.js allows you to statically generate pages with paths that depend on external data. This enables dynamic URLs in Next.js.”

Pages contained inside `[]` are dynamic routes. Example: `pages/posts/[id].js`

Example:

Write a `getStaticPaths` function that uses `getAllPostIds()` to store ids, which are paths.

Next fetch data that’s needed to render a post with a specific id. Write a `getStaticProps` function that uses `getPostData()` to get data and return it as props.

To render markdown, use `remark` library.

“Like `getStaticProps`, `getStaticPaths` can fetch data from any data source. In our example, `getAllPostIds` (which is used by `getStaticPaths`) may fetch from an external API endpoint.”

`getStaticPaths` runs on every request during development but at build time in production.

“Dynamic routes can be extended to catch all paths by adding three dots (...) inside the brackets.”


**Next.js – Deployment**

https://nextjs.org/learn/basics/deploying-nextjs-app

“Vercel is a serverless platform for static and hybrid applications built to integrate with your headless content, commerce, or database.”

Install Vercel for GitHub. Import your repo to Vercel. Deploy and get deployment URLs.


## Reading 42

**Dunder Methods**

https://dbader.org/blog/python-dunder-methods

Dunder methods (aka magic methods) in Python start an end with double underscores and allow you to write code that emulates the behavior of built in functionality.

This functionality is part of the Python data model and “lets developers tap into rich language features like sequences, iteration, operator overloading, attribute access, etc.”

`dir()` shows implemented dunder methods.

Examples

`__len__` - define for your data structure to call python’s `len()` method and return an appropriate result

`__getitem__` - use slicing syntax [stat:stop] – can also be used to allow iteration by a for loop

`__init__` - object constructor

`__repr__` - string representation of object

`__str__` - string representation of object (formatted for humans)

`__reversed__` - iterate in reversed order

`__eq__`, `__lt__`, `__gt__`, etc. – comparison methods

`__add__` - add objects

`__call__` - makes object callable

Context Manager:

“A context manager is a simple “protocol” (or interface) that your object needs to follow so it can be used with the `with` statement. Basically all you need to do is add __enter__ and __exit__ methods to an object if you want it to function as a context manager.”


**Iterators**

https://dbader.org/blog/python-iterators

“Objects that support the __iter__ and __next__ dunder methods automatically work with for-in loops.”

To create an iterable class, include a __iter__ and a __next__ method that returns a value from a source. Use an exception to signal the end of the iterable.

```
class BoundedRepeater:
    def __init__(self, value, max_repeats):
        self.value = value
        self.max_repeats = max_repeats
        self.count = 0

    def __iter__(self):
        return self

    def __next__(self):
        if self.count >= self.max_repeats:
            raise StopIteration
        self.count += 1
        return self.value
```

“Python iterators normally can’t be “reset”—once they’re exhausted they’re supposed to raise StopIteration every time next() is called on them. To iterate anew you’ll need to request a fresh iterator object with the iter() function.”


**Generators**

https://dbader.org/blog/python-generators

Generators are a shorter way to create iterables – instead of a return statement, use the `yield` keyword.

Calling a generator function creates the generator object. Call `next()` on the generator function.

“Whereas a return statement disposes of a function’s local state, a yield statement suspends the function and retains its local state.”
To resume execution, call `next()` on the generator object.

“You’ll find that for most types of iterators, writing a generator function will be easier and more readable than defining a long-winded class-based iterator.”

“Generators stop generating values as soon as control flow returns from the generator function by any means other than a yield statement. This means you no longer have to worry about raising StopIteration at all!”



## Reading 43

**Ethics in Tech**

**“The Code I’m Still Ashamed Of”**

https://www.freecodecamp.org/news/the-code-im-still-ashamed-of-e4c021dff55e

The author Bill Sourour describes an application that he built for a pharmaceutical company which marketed a drug to teenage girls. But the application did not disclose that it was an advertisement, and it presented itself as a quiz that appeared to make tailored recommendations based on user inputs – even though, no matter what, the app ultimately recommended the drug. Bill Sourour initially did not question the client specs and coded the website as intended. Only later did he find out that a side effect of the drug was depression, and it may have been implicated in suicides of teenage girls. I can understand how he initially overlooked the potential negative consequences of his work, though this example highlights the importance of paying careful attention to what one produces as a software developer and for what purposes. Developers can and should turn down client requests that involve these kinds of deceitful practices, which can have tragic consequences.

**“The Ethical Dilemmas of Self-Driving Cars”**

https://www.theglobeandmail.com/globe-drive/culture/technology/the-ethical-dilemmas-of-self-drivingcars/article37803470/

While self-driving cars have the potential to drastically reduce traffic fatalities, they introduce some new ethical dilemmas as well, notably some real-life trolley problems. For example, if a child is suddenly in the path of a car with too little time to break, a choice arises between saving the child at increased risk to the passenger, or vice versa. And the car must make that choice. Some have argued that the car should be designed to protect its passengers, but this may be too simplistic a solution, since potentially many more people outside the car could be harmed if the car only ever protects its occupants at all costs. People have attempted to set standards for these types of situations – Germany issued guidelines stating that “self-driving cars should always attempt to minimize human death and shouldn't discriminate between individuals based on age, gender or any other factor. Human lives should also always be given priority over animals or property.” But the debate is ongoing, and decisions on these questions could also affect the rate of adoption of self-driving cars if buyers fear giving up control to save their own lives.


## Reading 44

**Open Source**

**First Timers Only**

https://www.firsttimersonly.com/

There are many resources to guide first-time open source contributions – see link for more resources.

**GitHub’s Guide to Open Source**

https://github.com/open-source

Links to guides on how to contribute to open source, how to start an open source project, how to get users and track metrics, etc.

**What Motivates a Developer to Contribute to Open-Source Software?**

https://clearcode.cc/blog/why-developers-contribute-open-source-software/

It can be surprising how much unpaid time some developers spend contributing to open source projects, but there are very good reasons for contributing, including opening doors to paid opportunities. Some benefits:

- Improved coding skills – not only do you get practice, but you can get feedback from more experienced developers

- Recognition for good work opens up opportunities

- Improved job prospects – a developer’s Github is often more important than their resume during a job search

- Improve software that you like to use

List of Beginner Friendly Projects:

https://github.com/search?q=label%3Agood-first-issue+archived%3Afalse

Call for Code

https://callforcode.org/

This is a global platform for pairing developers with open source projects that address social and humanitarian issues.
