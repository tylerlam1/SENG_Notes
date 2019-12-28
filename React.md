# React

## What is React?

React is a open-source, efficient, and flexible JavaScript library that is used for building user interfaces. It's primary use is to render the User Interface (UI) of modern web applications. 

React uses something called JSX, which is a syntax extension to JavaScript. Basically, JSX produces the React "elements". Compared to JavaScript, JSX carries several benefits.

1. It permits the use of JavaScript within HTML.
2. Keeps the code readable.

However, there are several key features of JSX that diffrentiate it from HTML which will be further explored below.

One of the things about JSX is that you can directly write JavaScript code within JSX. This is done by including the JavaScript code within curly braces as shown below.

```Java
{ 'this is now treated as JavaScript code' }
```

JSX is not JavaScript. As such, JSX code must be separately compiled in JavaScript. One of the popular tools for doing this is a transpiler called Babel. A transpiler is a type of compiler that takes written source code within a particular programming language, and produces equivalent source code that is usually in a different programming language. 

The advantage of using React is the fact that it mitigates the need to *re-load* an either page when a small change is needed to a particular part of a webpage. For instance, if a Facebook webpage needed to update the number of likes on a post while a user is scrolling through their news feed, React allows the webpage to *solely* update the number of likes without updating the entire web page.

React designs simple views for each state of your application. It updates and renders the necessary components when the data on a webpage is changed. A react application is made of multiple components, where each component is responsible for rendering a small, reusable object on that webpage (HTML). Components can be nested within other components to enable the development of large, complex websites. Each component may also maintain an internal state.

## A bit of background

A DOM (Document Object Model) is an API for HTML and XML documents. In essence, it represents the page so programs can change document structure, style and content. Basically, programming languages can connect to the web. The web page itself is a document. 

When working with the DOM, it can be slow. The goal of React is to implement a virtual DOM. So when React wants to read or write to the DOM, it first accesses this 'paper' or virtual DOM, and the virtual DOM will subsequently find the most efficient way to update the browser's DOM. 

Every time your JSX tries to render new content onto the React DOM, it actually calls the following code in the background. 

```Java
ReactDOM.render(JSX, document.getElementById('root'));
```

This function is what places the JSX in React's lightweight representation of the DOM (virtual), which then the React DOM will determine which parts need to be updated.

## More on JSX

When working with a JSX element, it is important to keep in mind that a nested must only resturn a single element. The parent element would wrap all other levels of the nested elements. Therefore, if you to have several <h1> or <p> tags, you should have a <div> tag encapsulate all of it.

When adding comments, use {/* */} to wrap any comment text.

## Rendering HTML elements to the DOM

React allows you to easily render React elements to the DOM using the following piece of code.

```Java
ReactDOM.render(componentToRender, targetNode);
```

The first argument denotes the React element or component you want to render, and the second argument is the DOM node that you want to render the component to. It goes without saying that ReactDOM.render() should be called after your JSX element declarations.

## Defining HTML classes in JSX

In JSX, you can no longer use the word class to define HTML classes. Instead, JSX uses className. The following is an example of this in action.

```javascript
const JSX = (
    <div className = 'myDiv'>
        <h1>Adding a class to this div.</h1>
    </div>
)
```

Please be advised that camelcase is used for all HTML attributes and event references. 