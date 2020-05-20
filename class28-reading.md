# Props and State

## Forms and Inputs

- forms maintain internal state
- parent components will handle state of child components
- all inputs have an `onChange` trigger

## Props

- components take inputs called `props`
- passing in `props` adds them to the constructor via the `super` function
- can be data or functions
- parents can pass down data/funcs to children which can be envoked
- state can only be passed down the tree
- a parent can give a child a function that can then pass data to the parent state for use

### additional docs

#### articles

- [setState explained](https://css-tricks.com/understanding-react-setstate/)
  - possible to get previous `state` if needed
  - state only updates after a re-render, so you can't modify it multiple times in the same element before the render occurs
  - can use an `updater` to change the current state before the render
- [handling events](https://facebook.github.io/react/docs/handling-events.html)
- [forms](https://facebook.github.io/react/docs/forms.html)
- [state and lifecycle](https://facebook.github.io/react/docs/state-and-lifecycle.html)
- [components and props](https://facebook.github.io/react/docs/components-and-props.html)
