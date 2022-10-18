# Getting Started with TypeScript

## What is TypeScript?
Microsoft developed the well-known open-source language known as TypeScript. A superset of JavaScript gives the language type safety and static typing. Because TypeScript compiles to JavaScript, it can be used in any JavaScript-enabled environment, including the browser, Node and Deno.

Due to the fact that JavaScript is an interpreted language, occasionally you may have errors in your code that are not apparent until you run it. But because TypeScript is a statically typed language, errors can be caught at compile time rather than during runtime. This means that TypeScript can be used to create safer and simpler-to-debug code.

## Why TypeScript?
The aforementioned advantages make TypeScript a well-liked language for usage in contemporary development. These are a few of these advantages:

- **Compile-time errors**: You can save time and effort by using TypeScript, which can detect mistakes at build time rather than at runtime.
- **Strong typing**: Whenever you pass the function a type that isn't compatible with it, TypeScript will give you an error because it is statically typed.
- **Object-oriented improvements**: JavaScript lacks native object-oriented features, whereas TypeScript provides them.
- **Tooling and ecosystem**: Excellent tooling and support for TypeScript improve the developer experience.
- **Organization**: Because of namespaces, modules, and better OOP, TypeScript is a fantastic language for arranging your code.

## Installing TypeScript
To install TypeScript, you first need to install Node and NPM. If you need help with this, you can follow our [how-to install Node guide](https://docs.npmjs.com/downloading-and-installing-node-js-and-npm).

Once you have Node and NPM installed, you can install TypeScript with the following command:

```
npm install -g typescript
``` 
Alternatively, you can use Yarn to install TypeScript:

```
yarn global add typescript
``` 
We want to install it globally, so we can use it in any app we create.

Check to see if TypeScript is installed by running the following command:

```
tsc -v
``` 
If you see a version number in your terminal, you've installed TypeScript successfully.

## Using TypeScript
We can use TypeScript now that it has been installed. Make an app.ts file in your root directory. We can begin writing some TypeScript in this section.
Let's keep it simple and write a function that takes a number and returns the square of that number:

```
const square = (x: number): number => x * x;
``` 
To test that it is working, let's call the function and print the result:

```
const square = (x: number): number => x * x;
const result = square(5);
console.log(result);
``` 
Great, now that we've written our first TypeScript code, we can move on to compiling it.

## Compiling TypeScript into JavaScript
To compile our TypeScript code, we can use the TypeScript compiler. To do so, use the tsc command and pass it the name of the file we want to compile.

```
tsc app.ts
``` 
After the file is compiled, you should see an app.js file in the root directory.

```
var square = function (x) { return x * x; };
var result = square(5);
console.log(result);
``` 
Since app.js is just a regular JavaScript file, we can run it in the browser or Node.

Let's run it in Node: 
```
node app.js
``` 
You should see the output: 
```
25
``` 
The TypeScript compiler has successfully taken our TypeScript in app.ts and compiled it into valid JavaScript in our app.js.

## TypeScript Type Safety
As mentioned earlier, TypeScript is a strictly-typed language, which means that it can catch errors at compile time, rather than at runtime.

Let's look at our function one more time:

```
const square = (x: number): number => x * x;
``` 
Notice how we have to specify the type of the parameter x. This is because we are using TypeScript, and TypeScript requires that we specify the type of the parameter.

This is how TypeScript can help us catch errors at compile time.

We have also typed the return value of the function to be a number as well. This helps the caller know that the function will return a number, instead of a string, or something else. In this way, TypeScript code is somewhat self-documenting.

Watch what happens if we try to accidentally pass a string instead of a number:

```
const square = (x: number): number => x * x;
const result = square("5");
console.log(result);
``` 
If you try to compile this TypeScript code, the compiler will throw an error:

```
app.ts:3:23 - error TS2345: Argument of type 'string' is not assignable to parameter of type 'number'.

3 const result = square("5");
                        ~~~
Found 1 error.
``` 
The TypeScript compiler will throw an error, letting you know that the parameter x is of type number and that the argument "5" is not of type number.

Because TypeScript caught the issue at compile time, we can fix the issue by changing the input from a square to a number, saving us from a potential runtime error.

That's it from my side. I hope this was helpful!
let's connect on [Github](https://github.com/Prathmesh-Dhatrak) or [LinkedIn](https://www.linkedin.com/in/prathmesh-dhatrak).













