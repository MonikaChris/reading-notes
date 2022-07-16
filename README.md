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

# Why this topic matters:
React is a Component-Based Architecture. Other popular tools also use CBA’s due to certain advantages, like reusability and encapsulation of functionality. For this reason, it’s important to understand the design principles behind CBA’s.

# Component-Based Architecture Questions
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

# Props in React Questions
1.	What is “props” short for?
Properties

2.	How are props used in React?
Props are objects that pass read-only data between components in one direction from parent to child

3.	What is the flow of props?
Unidirectional from parent to child components



