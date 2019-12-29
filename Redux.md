# Redux

## What is Redux?

Redux is an open-source JavaScript library for managing application state. While React is largely focused on the UI, Redux is more focused on the logic. Both are front-end web technologies.

Redux can be seen as the *single source of truth* in regards to application state. Every time a piece of an application wants to update state, it must flow through the Redux store.

## Redux Store

The Redux store is an object which holds and manages the application state. A method called createStore() on the Redux object which is used to create the Redux store.