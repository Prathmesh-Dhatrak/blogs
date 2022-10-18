# Understanding JS concepts: Part 2

### So this is a series of blogs in which I try to explain different types of Frontend Development concepts.

So In each part, We will cover 5 Js concepts. <br>
**Note**:- *I am creating these blogs to understand myself and write about these different and important concepts in detail*. <br>
So to start we will see some of the basic Js concepts.<br>
### 1. JavaScript data types.
In JavaScript, there are three primary data types, two composite data types, and two special data types.<br>
- **Primary Data Types** -: String, Number, Boolean 
- **Composite Data Types**-: Object, Array 
- **Special Data Types**-: Null, Undefined

### 2. Difference between Null and Undefined.
All the other Data types can be understood by their name just the difference between Null and Undefined is complicated.
- So Undefined means the Variable used in the code doesn’t exist or the Variable is not assigned to any value or the Property doesn’t exist.
- ‘Null’ is a keyword in JavaScript that signifies ‘no value’ or the nonexistence of any value. If you wish to shred a variable of its assigned value, you can simply assign ‘null’ to it.

### 3. Types of errors in JavaScript.
There are three types of errors:
- **Load time errors**:- Errors that come up when loading a web page Like improper syntax errors are known as Load time errors and it generates the errors dynamically.
- **Run time errors**:- Errors that come due to misuse of the command inside the HTML language.
- **Logical Errors**:- These are errors that occur due to the wrong logic performed on a function.

### 4. Event Flow in JavaScript.
There are three distinct phases an event goes through:
- Capture
- Target
- Bubble

Events (such as ‘click’ events, for example) are registered not only by the target element where they originate but by all of that element’s parents all the way up to the global element (i.e. the Window/Browser).
An Event occurs (a ‘click’, for example) and the click event is registered (this means noted and recognized by the browser). <br>
The registered click event then goes from the Window Object down through the child elements and is registered on each during a ‘Capture Phase’ (`<html>` –> `<body>` –> `<div>` –> `<form>` –> `<button>`, for example) to find the Target Element (i.e to find what element was clicked).  <br>
Once the click event has registered on the Target (‘Target Phase’), it then bubbles back up the DOM Tree (‘Event Bubbling Phase’) and is registered on all parent elements up through the Window Object triggering any Event Listeners or Handlers in the process.

### 5. `use strict` in JavaScript.
`use strict` is a way to voluntarily enforce stricter parsing and error handling on your JavaScript code at runtime.
Code errors that would otherwise have been ignored or would have failed silently will now generate errors or throw exceptions. In general, it is a good practice.
Key benefits of strict mode
- Makes debugging easier
- Prevents accidental globals
- Prohibits the use of the same property names twice.
- Throws error on invalid usage of delete

That's it from my side. I hope this was helpful!
let's connect on [Github](https://github.com/Prathmesh-Dhatrak) or [LinkedIn](https://www.linkedin.com/in/prathmesh-dhatrak).

