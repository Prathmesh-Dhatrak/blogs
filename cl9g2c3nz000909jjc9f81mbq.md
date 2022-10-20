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
Then Import it to your page component

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
This is fine can't we create our own Debounce Function to do this same task? So we will try to build a custom debounce function so that there is no need of installing any package.

### Developing a custom debounce function.

Our Debounce Function will accept two arguments: the function that needs to be called when there is a delay and the duration of the delay at which the function needs to be called.
```
const customDebounceFunction = (function, delayTimeInMilliseconds) => {
    return () => {
      setTimeout(() => {
        function()
      }, delayTimeInMilliseconds)
    }
}
``` 
And now to pass the input from the (``this``) current target element to the delayed function we need to do some changes to the function.
```
const customDebounceFunction = (function, delayTimeInMilliseconds) => {
    let timer;
    return () => {
     let self = this;
      let args= arguments;
      clearTimeout(timer);
      timer = setTimeout(() => {
        function.apply(self, args)
      }, delayTimeInMilliseconds)
    }
}
``` 
Now just call the customDebounceFunction using **useCallback** hook so that we don't lose the reference to the older customDebounceFunction and its values.

```
const debounceValue = useCallback(customDebounceFunction((nextValue) => onSearchInputChange(nextValue), 1000), [])
```

So this is how you can handle and restrict multiple API calls in React.
That's it from my side, I tried sharing everything I could.
I hope this was helpful!

let's connect on [Github](https://github.com/Prathmesh-Dhatrak) or [LinkedIn](https://www.linkedin.com/in/prathmesh-dhatrak).



