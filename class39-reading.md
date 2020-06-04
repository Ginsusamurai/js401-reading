# Redux - Additional Topics

## Other store designs

- `Redux Toolkit` was released to try and unify the design
- specifies how to build reducers and action sets

```javascript

const postsSlice = createSlice({
  name: 'posts', initialState: [], reducers: {
    createPost(state, action) {},
    updatePost(state, action) {},
    deletePost(state, action) {} } })

// Extract the action creators object and the reducer 
const { actions, reducer } = postsSlice 
// Extract and export each action creator by name 
export const { createPost, updatePost, deletePost } = actions 
// Export the reducer, either as a default or named 
export export default reducer

// ————— Sample Use ————– 
console.log(createPost({ id: 123, title: ‘Hello World’ }))

{type : “posts/createPost”, payload : {id : 123, title : “Hello World”}}

// Notice how createSlice transforms your defiition? 
console.log(postsSlice)
 { name: ‘posts’, actions : { createPost, updatePost, deletePost, }, reducer }
```

### Resources

#### Articles

- [Redux Toolkit(RTK)](https://redux-toolkit.js.org/)
  - [tutorial](https://redux-toolkit.js.org/tutorials/intermediate-tutorial)
    - uses object properties on a reducers object to make methods for handling state events
    - `keys` of this object are the command actions\
    - these action keywords are autogenereated and in the format of `type: reducer/method`

- [Ducks(modular redux)](https://github.com/erikras/ducks-modular-redux)
- [MobX](https://mobx.js.org/getting-started.html)
- [HookState](https://hookstate.js.org/)