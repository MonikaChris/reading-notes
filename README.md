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
