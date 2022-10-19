# What is the problem with multiple API calls and How do we handle them?

So I was working on a project called **Cinemagram** a social media platform for movie lovers and in that I was building a search box that finds posts and users according to the input.

When I completed the functionality it was working correctly and giving me the result but I noticed a problem. That each time a user inputs something, an API request is made to the server, and because of this API request, the component was re-rendering multiple times. 

After some research, I found out that multiple unnecessary API calls are really not good for our project because of the re-rendering but especially because it increases the load of HTTP requests on the server.

So I needed to handle this in the project and as always I googled my issue and found this technique called **Debounce**.
### What is Debounce?
Debounce is a rate-restrict approach that demands a function or method to run just once after a predetermined period of time. It is a higher-order function, i.e. a function that returns another function. It forms a closure around the function parameters.

So we have a package called [lodash.debounce](https://www.npmjs.com/package/lodash.debounce) which is a JavaScript library that provides utility functions for common programming tasks using the functional programming paradigm and using this we can fix the multiple API calls problem in React.

- The Debounce function merges several repeated calls into a single request.
- Debounce Function takes two parameters a callback function and the delayed time.
- The callback function passed through debounce function will be fired after the delayed time.

First, install the package

```
npm install lodash.debounce
``` 
Then Import it in your page

```
import debounce from 'lodash.debounce';
``` 
and then use it with the input element by passing callback_function and delay time.

```
<input
  className=""
  placeholder="Search..."
  type="text"
  onFocus={onFocusInput}
  onChange={debounce(onSearchInputChange, 200)}
  onKeyDown={onSearchSubmit}
/>
```
So this is how you can handle and restrict multiple API calls in React.
That's it from my side, I tried sharing everything I could.
I hope this was helpful!

let's connect on [Github](https://github.com/Prathmesh-Dhatrak) or [LinkedIn](https://www.linkedin.com/in/prathmesh-dhatrak).




