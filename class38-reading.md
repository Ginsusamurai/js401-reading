# Redux - Asynchronous Actions

## THUNK

- typical example if async call and action

```javascript
let api = 'https://api.mockable.io/api/v1/stuff';

export const get = () => dispatch => {
  return utils.fetchData(api).then(records => {
    dispatch(getAction(records));
  });
};

const getAction = payload => {
  return {
    type: 'GET',
    payload: payload,
  };
};
```

- `thunk` middleware

```javascript
export default store => next => action =>
  typeof action === 'function'
    ? action(store.dispatch, store.getState)
    : next(action);
```

- this allows for curried functions
  - `func store => next => action => more` is curried. They happen in sequence


### Resources

#### videos

- [dan abramov on suspense](https://www.youtube.com/watch?v=6g3g0Q_XVb4)

#### articles

- [async actions](https://redux.js.org/advanced/asyncactions)
- [thunk middleware](https://github.com/reduxjs/redux-thunk)
- [redux thunk](https://alligator.io/redux/redux-thunk/)
- [suspense](https://blog.logrocket.com/async-rendering-in-react-with-suspense-5d0eaac886c8)