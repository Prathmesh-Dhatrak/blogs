# Understanding webpack and different Module Bundlers

So when I started learning react js framework. I simply started with CRA and that's why never understood the need for Module-Bundler like webpack.<br/>
So as a beginner I always thought to Build a website we only need three things that is HTML, CSS, and JavaScript. <br/><br/>
![1636485841-bundle-up.webp](https://cdn.hashnode.com/res/hashnode/image/upload/v1652801588345/H2YdRXHnH.webp align="center")
This sounds pretty straightforward on the surface but here's a problem that nobody just uses HTML, CSS, and JavaScript to build a website. You might replace javascript with TypeScript and then use a UI liberty like Rect instead of Plain HTML. And you will definitely need a CSS preprocessor like SCSS or SASS.
![Blog2-Moduler-bundlers.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1652801252199/0Pr7LnpPk.png align="left")
So to do all of this we have Module Bundlers like webpack, roll-up, parcel and snowpack. Which makes this entire process a little less annoying.
## What is a Module Bundler?
A module bundler is a tool that takes pieces of JavaScript and their dependencies and bundles them. One of the most important tasks of a module bundler is to take multiple JS files and combine them to create a single file that contains code we wrote along with required libraries to load in the browser.
## Why do I need one?
There are server complex reasons but some of them I tried to explain below.

- Multiple tags in HTML — Adding tags for each file in HTML would bring challenges.
- Limitation on concurrent ajax requests — hence fetching and loading all modules will take a significant amount of time.
- Managing correct sequential dependency order in HTML — Dependent modules should come before the requestor modules.
- Global declaration of functions and variables — hence high chances of overriding function and variable name collision and overridden.

```
<!DOCTYPE HTML>
<html>
<head>
<title>Module Bundlers</title>
</head>
<body>
<script src="js/utils/add.js"></script>
<script src="js/utils/subtract.js"></script>
<script src="js/utils/multiply.js"></script>
<script src="js/utils/divide.js"></script>
<script src="js/utils/maths.js"></script>
<script src="js/main.js"></script>
</body>
</html>
``` 
Each file requires separate HTTP requests, which are 5 round trip requests in order to get your application started. So it would be better if you can combine all 5 files into 1.
## How to use Module-Bundler like webpack.
First, we need to install webpack  and webpack-cli
```
npm install -D webpack webpack-cli
``` 
Then we need to populate webpack.config.js with a configuration featuring the following options:
- ``` devtool``` : Enables source-map generation in development mode.
- ``` entry``` : The main file of our React application.
- ``` output.path``` : The root directory to store output files in.
- ``` output.filename``` : The filename pattern to use for generated files.
- ``` output.publicPath``` : The path to the root directory where the files will be deployed on the web server.

```
const path = require("path");

module.exports = function(_env, argv) {
  const isProduction = argv.mode === "production";
  const isDevelopment = !isProduction;

  return {
    devtool: isDevelopment && "cheap-module-source-map",
    entry: "./src/index.js",
    output: {
      path: path.resolve(__dirname, "dist"),
      filename: "assets/js/[name].[contenthash:8].js",
      publicPath: "/"
    }
  };
};
``` 
The above configuration works fine for plain JavaScript files. But when using Webpack and React, we will need to perform additional transformations before shipping code to our users.

That's it from my side. I hope this was helpful!
let's connect on [Github](https://github.com/Prathmesh-Dhatrak) or [LinkedIn](https://www.linkedin.com/in/prathmesh-dhatrak).