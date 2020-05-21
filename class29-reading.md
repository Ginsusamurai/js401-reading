# Component Composition

## routing

- `react-router` can toggle visibility of components
- by using `Link` tags we can browse easier to components

## component composition - logical

- Send data to components and they render with own logic

## component composition - using logic-less children

- invoke the jsx form directly from a parent

```javascript
<Results>
    { listings.map( listing => listing ) }
</Results>
```

### resources

- [react basics recap](https://medium.freecodecamp.org/these-are-the-concepts-you-should-know-in-react-js-after-you-learn-the-basics-ee1d2f4b8030)
  - `updating` old state is compared to current state to see if a change has occured
  - components `unmount` when they are removed from the virtual dom
  - setState is async and you need to wait for an update to see a change UNLESS you pass a callback to setState and use the value from there. 
  - other options are to also set the state by calling previous state and modifying, getting THAT return and then using the callback. the reason to pass a function for this is that it can prevent state-setting race conditions as the funcs enter the stack to be resolved
- [props.children](https://codeburst.io/a-quick-intro-to-reacts-props-children-cb3d2fce4891)
- [browser router tutorial](https://blog.pshrmn.com/entry/simple-react-router-v4-tutorial/)
- [composition vs inheritance](https://reactjs.org/docs/composition-vs-inheritance.html)
- [browser router api docs](https://reacttraining.com/react-router/web/api)