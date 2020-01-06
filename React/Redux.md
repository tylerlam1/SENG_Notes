# Redux

## What is Redux?

Redux is an open-source JavaScript library for managing application state. While React is largely focused on the UI, Redux is more focused on the logic. Both are front-end web technologies.

Redux can be seen as the *single source of truth* in regards to application state. Every time a piece of an application wants to update state, it must flow through the Redux store.

## Redux Store

The Redux store is an object which holds and manages the application state. It's the highest level of 'power' in regards to application state. Even though each component has its local state, the entire state of the application is defined through the Redux Store. A method called createStore() on the Redux object which is used to create the Redux store.

```javascript
const store = Redux.createStore(reducer);
```

createStore returns a store object, and accepts a reducer as a argument. You can use .getState() to get the current state of a Redux Store. 

## Redux Actions

There's no real point of having state in the Redux Store if you can't update it. In order to update the state in Redux, all updates are triggered by dispatching actions. An action is an object that contains information about a event that occurs. Redux Store accepts these actions and updates its state correspondingly. 

```javascript
const action = {
    type: 'Action';
}
```

Once the Action is created, you need to send the action to the Redux Store so that the state can be updated. This is what Redux Action Creators are used for. A Action Creator returns the type of the action event when called. As the name suggests, an action creator creates an action as shown below.

```javascript
function addTodo(text) {
    return {
        type: ADD_TODO,
        text: 'sooso'
    }
}
```

In order to dispatch an action event, you use the following syntax.

```javascript
store.dispatch();
```

You pass the value returned from the action creator, which sends the action to the store.

Once the Redux Store receives the action, it needs to respond to that action. That's what the *reducer* is used for. The Reducer is responsible for the state modifications in response to actions. A reducer takes state and action as arguments and returns the new state. It's also important to note that in Redux, State is read-only. Therefore we never modify state directly. Rather, a new copy of state is returned.

A reducer takes action and state as arguments, and returns new state. A prototype of the object is shown below.

```javascript
const reducer = (state = defaultState, action) => {
    // change the state as necessary here
};
```

When working with working with different states, you can use a switch statement to decide what steps need to be taken. It's good practice to write action types as constants.

## Store Listeners

A Store Listener allows you to subscribe listener functions to the Redux Store. The function is called whenever an action is dispatched to the store. For example, this function can log a message.

## Working with Multiple Reducers

As your React application becomes more complicated, there will be more pieces of information that comprises your state. In order to make things as smooth as possible, you can divide your state into multiple pieces and have multiple reducers.

### CombineReducers()

You can use the combineReducers() function to combine multiple reducers together. This method accepts an object as an argument in which you define properties which associate keys to specific reducer functions. 

A good way to divide state is to consider how many distinct pieces of application state there are. For example, in a note-taking application, one reducer can handle authentication while another handles note submission. The combineReducers() function may look like this:

```javascript
const rootReducer = Redux.combineReducers({
    auth: authenticationReducer,
    notes: notesReducer
});
```

You can see everything is stored in key-value pairs. The `notes` key will contain all state associated with the notes. 

## Sending Action Data to the Store

In addition to sending types, you can also send action state to the store. Simply add the necessary data into the action object you're sending.

## Middlewares

Redux Middlewares are used for asynchronous actions. Our current action/reducer process flow is relatively clean. But what if we wanted to add in an external API call somewhere? How do we do this without interrupting the flow of the application?

Middleware allows this to happen.

Middleware essentially allows 'side-effects' to run without blocking state updates. Therefore, we can make external API calls, log actions, and perhaps do crash-reporting as well.

Here's the current flow of data without middleware.

1. An event occurs.
2. An action is dispatched that informs Redux Store of this change.
3. The reducer creates a new state that reflects this change.
4. New state is passed into React via props.

Middleware adds a step between steps 2 and 3. Let's take a look.

1. An event occurs.
2. An action is dispatched that informs Redux Store of this change.
3. Middleware receives the action.
4. The reducer creates a new state that reflects this change.
5. New state is passed into React via props.

## Recap

To recap everything, let's trace the steps of data flow from the React application View to the Redux Store. Keep in mind the view would be the front-end of the application and the Redux Store is the location where the application state is stored.

Redux architecture *strictly* revolves around _unidirectional data flow_. All data in an application follows the same lifecycle pattern, which makes your application easier to understand. 

1. An event takes place in the view. 
2. This action is a object that describes that happened. You may see an example below.

```javascript
{ type: 'LIKE_ARTICLE', articleID: 42 }
```

3. The action is dispatched to the Redux Store. This is done by using `store.dispatch(action)`. 

4. Once the Redux Store receives it, it will call the reducer function provided. The reducer takes the current state and the action.

Please note that you may have multiple reducers, and you can call `combineReducers` to combine all reducers to one.

5. The Redux store saves the complete state tree returned by the root reducer.