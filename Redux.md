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

Once the Action is created, you need to send the action to the Redux Store so that the state can be updated. This is what Redux Action Creators are used for. A Action Creator returns the type of the action event when called.

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

In addition to sending types, you can also send action state to the store.