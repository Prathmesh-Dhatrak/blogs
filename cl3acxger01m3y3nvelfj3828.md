# An Introduction to Webpack and Other Module Bundlers in React

As a beginner in the ReactJS framework, you may have started with Create React App (CRA) and never encountered the need for a module bundler like webpack. But as you dive deeper into building web applications with React, you'll soon realize that building a website with just HTML, CSS, and JavaScript is not enough.

![1636485841-bundle-up.webp](https://cdn.hashnode.com/res/hashnode/image/upload/v1652801588345/H2YdRXHnH.webp align="center")

You might want to use TypeScript instead of JavaScript, or a UI library like React instead of plain HTML. You'll also probably want to use a CSS preprocessor like SCSS or SASS. This is where module bundlers like webpack, rollup, parcel, and snowpack come in handy.

But what exactly is a module bundler, and why do you need one?

## **What is a Module Bundler?**

![Blog2-Moduler-bundlers.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1652801252199/0Pr7LnpPk.png align="left")

A module bundler is a tool that takes pieces of JavaScript and their dependencies and bundles them together into a single file. This file contains both your own code and the required libraries needed to run your code in the browser.

## Why do I need one?

Module bundlers are important because they make it easier to manage complex projects that involve multiple JavaScript files and dependencies. Without a module bundler, you would have to add separate `<script>` tags for each file in your HTML, which can be a hassle. There are also limitations on the number of concurrent AJAX requests, so fetching and loading all the modules individually can take a significant amount of time.

Module bundlers also help you manage the correct sequential order of dependencies in your HTML. For example, if module A depends on module B, you'll want to make sure that module B is loaded before module A. Without a module bundler, you would have to manually ensure that the `<script>` tags are in the correct order.

Finally, module bundlers help you avoid issues with global declarations of functions and variables. Without a module bundler, there is a risk of name collision and overridden variables, which can lead to unpredictable behavior in your code.

Here's an example of what your HTML might look like without a module bundler:

```xml
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

Each of these files requires a separate HTTP request, so it would take five round-trip requests just to get your application started. With a module bundler, you can combine all these files into a single file, reducing the number of requests and speeding up the loading time of your application.

## **How to Use a Module Bundler like Webpack**.

To get started with webpack, you'll need to install it and the webpack command-line interface (CLI). You can do this with the following command:

```javascript
npm install -D webpack webpack-cli
```

To use webpack, you'll need to create a `webpack.config.js` file with the following options:

* `devtool`: Enables source map generation in development mode.
    
* `entry`: The main file of your React application.
    
* `output.path`: The root directory to store output files in.
    
* `output.filename`: The filename pattern to use for generated files.
    
* `output.publicPath`: The path to the root directory where the files will be deployed on the web server.
    

Here is an example of what your `webpack.config.js` the file might look like this:

```javascript
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

This configuration works fine for plain JavaScript files, but when using webpack with React, you'll often need to perform additional transformations before shipping your code to users. This is where loaders and plugins come in handy.

Loaders are transformations that are applied to your code before it is bundled by webpack. They allow you to import and use non-JavaScript files, such as TypeScript or SCSS, in your JavaScript code. For example, the following configuration uses the `ts-loader` and `sass-loader` to transpile TypeScript and SCSS files:

```javascript
module.exports = {
  // ...
  module: {
    rules: [
      {
        test: /\.tsx?$/,
        use: "ts-loader"
      },
      {
        test: /\.scss$/,
        use: ["style-loader", "css-loader", "sass-loader"]
      }
    ]
  }
};
```

Plugins are extensions that allow you to perform a wide range of tasks, such as generating an HTML file or optimizing your code for production. For example, the `HtmlWebpackPlugin` generates an HTML file that includes a `<script>` tag for your bundled JavaScript:

```javascript
const HtmlWebpackPlugin = require("html-webpack-plugin");

module.exports = {
  // ...
  plugins: [
    new HtmlWebpackPlugin({
      template: "src/index.html"
    })
  ]
};
```

With these configurations in place, you can run a webpack to build your application. You can use the following command to build in development mode:

```javascript
webpack --mode=development
```

And the following command to build in production mode:

```javascript
webpack --mode=production
```

In development mode, webpack will generate source maps and perform transformations in an unminified manner. In production mode, webpack will minify your code and perform other optimizations to reduce the size and improve the performance of your application.

## **Module Bundlers vs. Create React App**

Now that you have a basic understanding of module bundlers, you might be wondering how they compare to Create React App (CRA).

CRA is a tool that generates a template for a new React application with webpack and other dependencies already set up for you. It allows you to get started with a new React project quickly without having to worry about configuring webpack yourself.

However, one of the downsides of CRA is that it hides the webpack configuration from you. This can be a disadvantage if you want to customize the configuration or add additional plugins and loaders. In these cases, you'll have to eject the configuration from CRA, which can be a complex process.

On the other hand, using a module bundler like webpack gives you full control over the configuration of your build process. This can be a powerful advantage if you have specific requirements or need to optimize your build process for performance.

## **Conclusion**

Module bundlers like webpack are important tools for building complex React applications. They allow you to manage multiple JavaScript files and dependencies and perform transformations on your code before it is bundled for the browser. While Create React App is a convenient option for getting started with a new React project, using a module bundler gives you more control over the build process and can be a powerful advantage for more advanced projects.  

That's it from my side. I hope this was helpful! let's connect on [GitHub](https://github.com/Prathmesh-Dhatrak) or [LinkedIn](https://www.linkedin.com/in/prathmesh-dhatrak).