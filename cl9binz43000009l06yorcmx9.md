# Understanding JS concepts: Part 1

### So this is a series of blogs I'm starting regarding Frontend Development concepts.
In each part, I will try to explain 5 Js concepts or common javascript questions.
I am creating these blogs to understand and write about the concepts in detail. <br />
So to start we will see some of the basic Js concepts.
<br/>

### 1. Javascript<br/>
JavaScript is a high-level programming language that is dynamic, untyped, and interpreted. 
Along with HTML and CSS, it is one of the three essential technologies for developing Web applications;<br> 
It is used by the majority of websites and is supported by all modern web browsers without the use of plug-ins or other extensions. <br/>
There are three ways to add JavaScript commands to your Web Pages: 
- Embedding code
- Inline code
- External file

### 2. Javascript Objects <br/>
Object-oriented programming is supported by JavaScript. Objects are used to arrange variables, Web pages, forms, text boxes, images, and buttons are all treated as objects on the screen.<br>
Every object has its own properties and methods. Properties define the characteristics of an object. Examples: color, length, name, height, width. 
<br> Methods are the actions that the object can perform or that can be performed on the object. Examples: alert, confirm, write, open, close.
![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1665931255150/IhHjVuSdZ.png align="center")

### 3. Javascript Events <br/>
The objects on a Web page are organized in a hierarchy. All objects have properties and methods. In addition, some objects also have "events". Events are things that happen, usually user actions, that are associated with an object. The "event handler" is a command that is used to specify actions in response to an event.
<br>Common events are:

- onLoad - occurs when a page loads in a browser
- onUnload - occurs just before the user exits a page
- onMouseOver - occurs when you point to an object
- onSubmit - occurs when you submit a form
- onClick - occurs when an object is clicked <br>

JavaScript interacts with HTML via events that occur when the user or browser manipulates a page. An event occurs when the page loads. When a user clicks a button, that is also an event.<br> Other events include pressing any key, closing a window, resizing a window, and so on.<br>
Developers can use these events to execute JavaScript-coded responses, such as closing buttons, displaying messages to users, validating data, and virtually any other type of response imaginable.<br> The Document Object Model (DOM) Level 3 includes events, and each HTML element contains a set of events that can be triggered by JavaScript code.

### 4. Javascript  programming paradigms <br>
JavaScript is a multi-paradigm language, supporting procedural programming along with Object-Oriented Programming and functional programming. <br>
Functional programming produces programs by composing mathematical functions and avoids shared state & mutable data. <br>
Functional programming is an essential concept in JavaScript (one of the two pillars of JavaScript). Several common functional utilities were added to JavaScript in ES5. JavaScript supports OOP (second pillar) with prototypal inheritance.

### 5. Diff between classical inheritance and prototypal inheritance <br>
Unlike most other languages, JavaScript’s object system is based on prototypes, not classes. 
<br>
**Class Inheritance**: instances inherit from classes (like a blueprint - a description of the class), and create sub-class relationships hierarchy. Instances are typically instantiated via constructor functions with the ```new``` keyword. Class inheritance may or may not use the class keyword from ES6. <br>
**Prototypal Inheritance**: instances inherit directly from other objects. Instances are typically instantiated via factory functions or ```Object.create()```. Instances may be composed of many different objects, allowing for easy selective inheritance.

That's it from my side. I hope this was helpful!
let's connect on [Github](https://github.com/Prathmesh-Dhatrak) or [LinkedIn](https://www.linkedin.com/in/prathmesh-dhatrak).



