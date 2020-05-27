# Custom Hooks

## What?

- extract duplicated logic from components
- share funtionality (not state)
- utilized `useEffect` lifecycle

- Common uses:
  - handle forms
  - pre-fetch api data
  - connect to services (socket.io, Q, etc.)

## The How...

- hooks are exported as a function
- hooks return data or functions
- imported to components
- component can then re-use functionality or data/state
- hooks do NOT render

### Resources

#### Authoring

- [custom hooks - all you need to know](https://www.telerik.com/blogs/everything-you-need-to-create-a-custom-react-hook)
  - prefixed with `use`
  - hooks are just imported functions, which can in turn access other functions
- [async hooks](https://dev.to/vinodchauhan7/react-hooks-with-async-await-1n9g)
- [useReducer hook](https://reactjs.org/docs/hooks-reference.html#usereducer)
- [react custom hooks](https://reactjs.org/docs/hooks-custom.html)

#### Hooks Lists/Collections

- [use hooks](https://usehooks.com/)
- [hooks list](https://github.com/rehooks/awesome-react-hooks)
- [10 essential react hooks](https://blog.bitsrc.io/10-react-custom-hooks-you-should-have-in-your-toolbox-aa27d3f5564d)