# Redux

## Redux Store

- 3 distinct aspects make a `store`
  - state
  - reducers (strategies to alter state)
  - actions (`dispatched/run` methods which trigger reducers)

- `store` is where the application state resides
- identifies `reducers` and `middlware` needed available and used globally
- `reducers` hold and manage a small piece of the larger state
  - ex. e-commerce store with reducers for `products`, `categories`, and `carts`

```javascript 
let initialState = { customerId: null, items: [] };

const myReducer = (state = initialState, action) => {
  let { type, payload } = action;

  switch (type) {
    case 'INITIALIZE':
      return {customerId: payload.id};

    case 'ADD_ITEM':
      return { items: [...items, payload.item] };

    case 'CLEAR':
      return initialState;

    default:
      return state;
  }
};
```

- redux `dispatches` an `action` with a `payload`
- `action creator` sends a payload and an `action` to perform

```javascript
// actions.js
const newCart = customer => {
  return {
    type: 'INITIALIZE',
    payload: customer,
  };
};
```

- the `store` ties it all together

```javascript
import { createStore, combineReducers, applyMiddleware } from 'redux';

import cartReducer from './reducers/cart.js';

let reducers = combineReducers({
  cart: cartReducer,
});

export default () => createStore(reducers);
```

- componenets subscribe to the store and use the actions it provides
- components use `connect()` to attach to the store and get methods, but it needs to be `provided` for the app to see it

```javascript
import React from 'react';
import ReactDOM from 'react-dom';
import { Provider } from 'react-redux';

import './style.scss';

import App from './components/app';

import createStore from './store';
const store = createStore();

class Main extends React.Component {
  render() {
    return (
      <Provider store={store}>
        <React.Fragment>
          <App />
        </React.Fragment>
      </Provider>
    );
  }
}

const rootElement = document.getElementById('root');
ReactDOM.render(<Main />, rootElement);
```

### Resources

#### video

- [dan abramov redux tutorias](https://egghead.io/courses/getting-started-with-redux)
  - entire state is considered 1 object
  - `action` is a description of what to change in state
  - requiers a `type` property string to describe action
  - `action` can also have a payload passed with the `type` to give required context/info
  - `state` is `read-only` except for these actions
  - some redux functions need to be `pure functions` 
  - each method called by an action should have an input which is `previous state` and `new info` and then returns a `new state object` -> `the reducer`
  - on default action, just return state
  - we should also load an `initial state` when the app starts
  - `const { createStore } = Redux;` to set up
  - `store` has 3 key methods
    - `store.getState()` to get current state
    - `store.dispatch()` sends an action (with the `type`)
    - `store.subscribe()` registers a callback to be used
  - write a method, subscribe to the store `store.subscribe(method)` and then run method to instantiate state
  - `listeners` are registered and watch for state changes to render
    - no unsubscribe method, just return a `listeners.filter()` that returns everything BUT the one you want removed.

#### articles

- [worlds easiest guide to redux](https://medium.freecodecamp.org/understanding-redux-the-worlds-easiest-guide-to-beginning-redux-c695f45546f6)
- [testing with redux and enzyme](https://medium.com/netscape/testing-a-react-redux-app-using-jest-and-enzyme-b349324803a9)
- [testing reducers](https://medium.com/@netxm/testing-redux-reducers-with-jest-6653abbfe3e1)
- [redux docs](https://redux.js.org/)
- [enzyme-redux npm module](https://www.npmjs.com/package/enzyme-redux)
- [middleware tests with a mock store](https://gist.github.com/johncokos/4902683c8e33ed38fb2ba066b8764831)