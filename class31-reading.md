# Hooks API

## Hooks

- react hooks allow `state` manipulation in `functional` component
- hooks are js funcs with more rules
  - require `use` prefix (`useIncrementor`)
  - only calls hooks at top level
  - only call hooks from function components, not regular js functions

## built in hooks

- `import { useState } from 'react';`
- `useState()` returns `stateVariable` and `setterFunciton`
- naming convention `set` + `statVar` so `setClicks` or `setLoading`

### Resources

#### Videos

- [making sense of hooks](https://medium.com/@dan_abramov/making-sense-of-react-hooks-fdbde8803889)
- `useState` is a hook provided by React
  - multiple variables can be declared inside the same function
  - `useContext` to apply styling via className
  - can't call a hook in a condition or other level
    - reason for this is that order of `useState` is how the system keeps track of what is working

#### Articles

- [the state hook](https://reactjs.org/docs/hooks-state.html)
  - hooks don't work inside classes, but can let us code without a class
  - state variables used this way persist after function exits
  - `this.state.foo` not required for hooks, just the `foo` part
  - `useState` returns 2 items, a state value and a setter function (via array destructuring)
- [hooks api](https://reactjs.org/docs/hooks-overview.html)
  - `useEffect` is similar to `useState` but does effects from a function component
  - when used, runs a provided funciton after flush changes to the DOM
  - runs after EVERY render, including first
  - can have multiple state hooks in the same function, they are all isolated from each other
  - `use` is the prefix for a custom hook
- [hooks api reference](https://reactjs.org/docs/hooks-reference.html)
  - with setting state, if the value passed in is same as current state, no re-render will occur
  - `useEffect` is jumping out from `functional` to `imperative` world
  - pass array of depent values as a second argument, will only trigger when those arguments change (pass in props and state versions to ensure no stale state, passing [] tells it to just run once)
  - `useContext` will apply the 'nearest' context to the item. Requires a context object be passed in
- [effects hook](https://reactjs.org/docs/hooks-effect.html)
  - `useEffect` inside of the function lets it access the `useState` created variables
