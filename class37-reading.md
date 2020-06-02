# Redux - Combined Reducers

- just pulling in more than one reducer from source and creating a keyed object from them
- any component can reach into the store and get any/all of them


## Why bother?

- single responsibility principle
  - each reducer should only handle 1 part of state
  - more work/boilerplate? yes
  - allow for decoupled logic? yes

## What about actions?

- each reducer has it's own actions and creators
- however, these can cross polinate
  - can send `RESET` across multiple reducers
  - can be error prone if not understood


## Examples

- combine reducers

```javascript
import todoReducer from './todo.store.js';
import itemReducer from './item.store.js';

let reducers = combineReducers({
  todo: todoReducer,
  item: itemReducer,
});
```

- use multiple reducers

```javascript
import * as actions from "../../store/todo.store.js";
import * as itemActions from "../../store/item.store.js";

const mapStateToProps = state => ({
  todo: state.todo,
  item: state.item,
});

const mapDispatchToProps = (dispatch, getState) => ({
  deleteItem: id => dispatch(actions.deleteItem(id)),
  hideDetails: id => dispatch(itemActions.hideDetails()),
});
``` 

- wide use of `RESET`

```javascript
//counter.store.js
export default function reducer (state = initialState, action) {
  switch (action.type) {
    case 'INCREMENT':
      return { value: state.value + 1 }
    case 'RESET':
      return {value:0};
    default:
      return state;
  }
}

//history.store.js
export default function reducer (state = initialState, action) {
  switch (action.type) {
    case 'CLICK':
      return { clicks: state.clicks + 1 }
    case 'RESET':
      return {clicks:0};
    default:
      return state;
  }
}
```


### Resources

#### videos

- [multiple reducers example](https://www.youtube.com/watch?v=gBER4Or86hE)

#### articles

- [Redux Docs: Using combined reducers](https://redux.js.org/recipes/structuring-reducers/using-combinereducers/)
- [Redux Docs: combined reducer syntax](https://redux.js.org/api/combinereducers/)