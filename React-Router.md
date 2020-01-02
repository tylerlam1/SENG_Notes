# React Router

React Router basically conditionally renders certain components to display depending on the route being used in the URL. It allows for single-page navigation that looks like multiple pages in React applications.

## Installing React Router

Use the following command to install React Router

```console
npm install react-router-dom
```

Once React Router has successfully installed, several libraries will need to be imported.

1. BrowserRouter
2. Route
3. Switch

Before anything starts, you need the application to work with React Router. You can wrap everything inside the BrowserRouter element when rendering it to the DOM.

```javascript
ReactDOM.render(
    <BrowserRouter>
    <App />
    </BrowserRouter>.
    document.getElementById('root')
)
```

Next, you need to add the Switch element into your App component. This ensures that only one component is rendered at a time.

```javascript
function App() {
    return (
        <main />
            <Switch>
            // calling the child components here
            </Switch>
        <main />
    )
}
```

The Route tags now need to be added. They accept a path attribute and a component attribute. The component is the one you want to load. AN example is shown below.

```javascript
<Route path='/' component={Home} />
```

After doing this, the components only appear when the paths are entered into the URL. This isn't very useful. Therefore we need to add Link tags to set up easy accessible navigation for the browser.

```javascript
<Link to="/">Home </Link>
<Link to="/about">About us </Link>
```

That's all. The site will now have clickable links that 