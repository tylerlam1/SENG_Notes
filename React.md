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

When rendering a component to the DOM, it is important to note there is a slight syntax difference compared to rendering JSX elements.

```javascript
ReactDOM.render(<ComponentToRender />, targetNode)
```

## Props

Props, or Properties, is one of the most important parts of React. 

In React, you can pass props from parent components to child components. For instance, you can pass a property *user* from a parent to child component.
Imagine you have a App parent component and a Welcome child component.

```javascript
<App>
    <Welcome user='Tyler'>
</App>
```

The child component can promptly access this property using the following syntax.

```javascript
const Welcome = (props) => <h1>Hello, {props.user}!</h1>
```

In addition, you can also pass an array as props. When passing an array to a JSX element, it must be treated as JavaScript and wrapped in curly brackets.

You can also set default props in React. This allows for a property to have a default value if nothing is modified in props. To override a default prop, you just simply need to explicitly set a new prop value.

As good practice, it may be valuable to use PropTypes to explicitly define the type of property a child component may expect. For example, if a component expects an array, you can use PropTypes to make sure it always receives an array in props.

In a ES6 React Component, you would simply use this.props to access props.

Good programming practices always encourages the use of stateless functional components whenever possible. You always want to minimize statefulness, as it helps contain state management to a specific area of the application. This makes the application easier to maintain and follow how state changes.

## State

In addition to props, state is one of the most important concepts in React. State is the information your application needs to know about, and is subject to change. Your application responds to state changes and the UI is updated as needed.

A React component has state by initializing *state* in the constructor. The property must be set to a JavaScript object. The following is an example.

```javascript
this.state = {
    // describe the state here
}
```

Throughout the life of the component, the state is maintained. It can be complicated or simple. In a stateful component, if you want to access a state value within a return statement, you must use the value inside curly braces.

Changes in state automatically re-renders the necessary components (including any child components that receive the data as a prop). React updates the actual DOM as necessary. State is also completely encapsulated.

You only need to use the curly braces in the return statement. In the render() method, it is not necessary to use the curly braces.

When updating state, it is important not to set state directly. Instead, you should use a this.setState() function that updates the state by entering the necessary key value pairs. 

```javascript
this.setState({
    name: 'Lam'
})
```
An important idea to keep in mind is that class methods in a component typically do not have access to the *this* keyword by default. As such, you need to *bind* it in the constructor to basically let the constructor know what this means. This is shown as below.

```javascript
this.handleClick = this.handleClick.bind(this)
```
Where handleClick is a class method.

Suppose that a setState call needs access to the previous value of state. When doing this, you should pass state and props in as parameters into set state as shown below.

```javascript
this.setState((state,props) => ({
    counter: state.counter + props.increment
}));
```

## Controlled Input and Forms

HTML form elements work differently than other DOM elements in React. This is due to the fact that form elements naturally keep some internal state. This includes elements like *input*, *textarea*, and *select*. In React, components have their own state, which is only updated with setState().

We can combine the two by utilizing React state. Thus, the React component that renders the form also controls what happens to the form in the subsequent user input. This is known as *Controlled Component*, where the input form element is also controlled by React.

## Important Ideas Regarding Relationship between State and Props

There may be times where you want to pass the state as props. That is perfectly legal - however data flow should only go from the stateful parent component to child component (unidirectional data flow). Child components receive the state data they need. It is good programming practice to avoid managing state in as many components as possible. Components should only be as complicated as they need to be.

Also, state is not limited to data. The props being passed can be functions or methods that is defined on a React component. This allows child components to interact with their parent components. This is done in the same way as you would pass any state.

## Lifecycle Hooks

Lifecycle hooks allow programmers to catch components at certain periods in time. This may include before they are rendered, before they update, or before they receive props, etc.

The following are lifecycle methods

* componentWillMount() - called before render
* componentDidMount()
* shouldComponentUpdate() - can be used to optimize performance (return boolean)
* componentDidUpdate()
* componentWillUnmount()

## Event Listeners

React provides pre-defined event handlers like onClick() that is already available to use. However, if you want to add a event listener onto a component that doesn't have this readily available, you'll need to add it to the component directly using lifecycle hooks.

The following piece of code is the typical syntax for adding a event listener.

```javascript
document.addEventListener(event, callback)
```

You can also remove an event listener as follows.

```javascript
document.removeEventListener(event, callback)
```

Good programming practice dictates the cleanup of React components before and after they are mounted/unmounted.

## Styling

Inline styling in JSX is very similar to HTML. However, you need to set the strings to a JavaScript object. Please ensure to maintain camel case syntax when declaring attributes.