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
