# Event Driven Applications

- how to leverage
  - everything is an object
  - most actions in js are event driven
    - ui events
    - express routes
    - model lifecycle hooks
    - react...just the whole thing

## emitting events

- you can perform an `emit` action on a promise chain `emit('delete', request.query.id)`
- event handler can listen for it 

``` javascript
events.on('delete', (data)=>{
  // stuff
});
```

- we've used this with mongoose schemas, letting us do things like `users.pre('save')` to perform actions just prior to the save event.


### additional resources

- [event driven programming](https://alligator.io/nodejs/event-driven-programming/)
- [node docs: events](https://nodejs.org/api/events.html)
