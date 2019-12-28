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

When working with a JSX element, it is important to keep in mind that a nested must only resturn a single element. The parent element would wrap all other levels of the nested elements. Therefore, if you to have several h1 or p tags, you should have a div tag encapsulate all of it.

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

## Self Closing tags in JSX

In HTML, basically all tags need to be open and closed. However, there may be special cases where the tags are self closing, like line-break (br) tags.

In JSX, any element can be written with a self-closing tag, like shown below. Each element *must* be closed.

```javascript
<div />
```

## Components

Everything in React is a component. As mentioned above, a React web page is built from components. There are two ways to create a React component.

1. Using a JavaScript function. By creating a function this way, you are creating a stateless functional component. A stateless functional component means that this component will receive and render data, but will not track or manage it in any way. Below is an example of a React component.

```javascript
const DemoComponent = function() {
    return (
        <div className = 'customClass'/>
    )
}
```

Please note that function names must start with a capital letter. You can create complicated HTML pages that consists of many different components, which allows for easier maintenance and development process.

The other way to create a React component is with ES6 syntax.

6. Using React.Component and class

By using React.Component, many React features can now be utilized like local state and hooks. Below is an example of a React Component using class.

```javascript
class Kitten extends React.Component {
    constructor(props) {
        super(props);
    }

    render() {
        return (
            <h1>Learning React!</h1>
        )
    }
}
```
As we have gleaned from our 409 class, the extends keyword allows class Kitten to inherit all the features from React Component. The constructor,  passes in props to the superclass. Props basically stands for properties.

Next, let's investigate how to mend multiple React components together.

When combining multiple React components together, you need a parent component which renders these components together. This is done by having a return statement that encapsulates the child component name in a self-closing JSX tag.

```javascript
return (
    <App>
    <Navbar />
    <Dashboard />
    <Footer />
    </App>
)
```

Let's also take a look at nested components.

The advantages of React is that you can nest components within components. By doing this, you can really start breaking down your application/webpage into many basic manageable parts. This separates logic and UI management, which is an important part of developing clean, manageable and readable code.