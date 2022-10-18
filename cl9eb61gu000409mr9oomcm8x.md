# Understanding React Class-Based Component 
and Is it worth learning?

If you are someone like me who started learning React after 2018-19 then probably you have learned functional components in detail and not gotten a chance to learn or not have worked on Class-Based Components in depth.

And this is just because most of the new-age React tutorial series or Courses will go in-depth about Functional components, React Hooks and show how you can solve each and every problem regarding component states with Hooks rather than using Class-Based Components and its LifeCycle Methods.

And this is probably true we all know the advantages of functional components over Class-Based Components 

Like-:
- With Hooks, you do not need to use lifecycle methods. Side effects can be handled by a single function.
- Hooks offer more flexibility and they can be reused, especially custom ones in multiple components.
- Hooks make code cleaner and easy to read and test.
- Hooks don’t need the ```this``` to bind the functions for the click events, and also access values in the component or global states.

But 70% to 80% of companies (for which you are going to do the job) were using Class-Based Components and most certainly they will be upgradation the code in the future but to be able to accomplish that we need to have a good understanding of Class-Based Components and their life-cycle methods.

So that's why I'm writing this blog and trying to understand Class-Based Components.
And to do this we will try to create a simple count increment decrement app in react.

### **1. Make a class declaration and extend ``React.Component``** <br>
Class-based components have a similar structure to functional components. Instead of declaring with ```const``` for functional components, we extend ```React.Component``` subclass to declare a class. Below is an example of how a simple functional component could be refactored into a class-based component.

Functional Component
```
const FunCom = () => {
   return(
      <p>Functional Component</p>
   );
};
```
Class-based Component
```
class CounterClass extends React.Component {
   render() {
      return (
         <div className="counter">
            <h1>COUNTER</h1>
         </div>
      );
   }
};
```

### **2. Constructor() and render() lifecycle methods and State.** <br>
To display the COUNTER text to UI, we must call the render() method, as demonstrated in the above example. The render() is one of the lifecycle methods, which will be called multiple times when the class's state would change. In contrast, you may use a constructor() method to initialize the class. For example, when you access external data, you only need to call it once as your class gets initialized, so those callbacks should happen in the constructor().
```
class CounterClass extends React.Component {
  constructor(props) {
    super(props);
    this.state = { count: 0 };
  }
  render() {
      return (
         <div className="counter">
            <h1>COUNTER</h1>
             <p>{this.state.count}</p>  
         </div>
      );
   }
};
```
It can take some time for the data to become available after it has been requested from constructor(), or the data might change while the user is still viewing your page. You might want to update your page to reflect changes as the data becomes available or is updated. The ``state`` is used in the React class to manage these phases.

### **3. Update state**<br>
For accessing the state you can use ``this.state.count``  but for updating the state we have ``this.setState={count:newValue}``. So to complete this Counter app we will add an increment function and decrement function to its button and set the count in those functions. 

```
class CounterClass extends React.Component {
  constructor(props) {
    super(props);
    this.state = { count: 0 };
  }
  increment = () => {
    this.setState({
      count: this.state.count + 1,
    });
  }
  decrement = () => {
    this.setState({
      count: Math.max(this.state.count - 1),
    });
  }
  render() {
      return (
         <div className="counter">
            <h1>COUNTER</h1>
            <div className="buttons">
              <button onClick={this.increment}>Increment</button>
              <button onClick={this.decrement}>Decrement</button>
            </div>
            <p>{this.state.count}</p>  
         </div>
      );
   }
};
```
Now this will work you can just call the CounterClass in your App.js and see the output.

### **So The last part Lifecycle methods **<br>
- **constructor()** - Initializer for declaring variables or states.
- **componentDidMount()** - After the component has been rendered, this method is called. This method may be used in place of the constructor() to call the initial data request.
- **render()** - This is the main and required method that outputs HTML to the DOM.
- **componentDidUpdate()** - Called after the component is updated in the DOM.
- **componentWillUnmount()** - Called when the component is about to be removed from the DOM.


That's it from my side, I tried sharing everything I could.
I hope this was helpful!

let's connect on [Github](https://github.com/Prathmesh-Dhatrak) or [LinkedIn](https://www.linkedin.com/in/prathmesh-dhatrak).