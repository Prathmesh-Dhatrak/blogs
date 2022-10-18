# What We Can Do To Lazy Load React Components?

## What is lazy loading?
Your website should render pages as rapidly as feasible when a visitor visits. Only the topmost part of the page would be visible to the user. Imagine that the page's lower portion contains numerous images. The user will acquire unnecessary data and the website will appear to be of becoming slow if you download all the pictures on the first page.

Instead, it's indeed beneficial to delay image loading until the user sees or is about to see them. This will significantly improve performance, user experience, and even SEO.

So, how can we straightforwardly achieve lazy loading? Several packages address this problem. The **[react-lazyload](https://www.npmjs.com/package/react-lazyload)** package is among my absolute favorites and is probably the most widely used. I prefer to use a third-party package for this because it is fast, performant, and simple to use.

## Using react-lazyload

**[react-lazyload](https://www.npmjs.com/package/react-lazyload)**  is an open-sourced and free package that controls the lazy loading of React components, images, and other resources. It has over 100k weekly downloads and simplifies lazy loading.

To install the package run

```yarn add react-lazyload```
Then import the component into your application

```import LazyLoad from 'react-lazyload'```

Then wrap the component you want to lazy load with```<LazyLoad>```
```
<LazyLoad>
    <Component />
</LazyLoad>
```
That’s it. This will load the ```<Component />``` first when it is visible in the viewport.

## Specify the LazyLoad component's properties.
The components themselves will default remain hidden till the LazyLoad component loads itself. You have several alternatives depending on the type of component you want to lazy load.

To prevent layout changes whenever the component loads, you can provide a height for images. You may accomplish this using the property height. Set the height to a specific amount of pixels and the component will take up that much space before being loaded.
```
<LazyLoad height={300}>
    <Component />
</LazyLoad>
```
Use the offset property to render the component immediately before the user actually sees that portion of the page. Thus, you can specify that a component should be loaded when a user is x pixels away from seeing it.
```
<LazyLoad offset={100} height={300}>
    <Component />
</LazyLoad>
```
So when the component is 100 pixels away from the viewport, it is loaded. Since the user won't detect the actual loading and can keep scrolling unobserved, this improves the user experience.

Other attributes, including style, resize events, and placeholders, can be set. To learn more, visit the official documents.

Happy loading, lazy in React!

That's it from my side. I hope this was helpful!
let's connect on [Github](https://github.com/Prathmesh-Dhatrak) or [LinkedIn](https://www.linkedin.com/in/prathmesh-dhatrak).