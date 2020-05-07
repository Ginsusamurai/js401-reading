# Message Queues

- queue sever runs independently to route events and messages for clients
  - any client can 'publish' a message to server
  - any client can 'subscribe' to receive messages
- queue controls visibility of each client for this, acts as a hub

## what is a message?

- `queue` -> which bucket does this belong to?
- `event` -> what CRUD or other method?
- `payload` -> data associated

## real time vs queued messaging

- with real-time, messages come in and are sent out
- if a client loses connection, they lose new messages

- queue tracks delivery of messages 
- anything not received stays in the queue until the subscriber acknowledges delivery

### use case

- api -> gets a post request, rights confirmed, data normalized, data sent to db, db `publishes` message to queue, data sent back
- logging app -> subscribed to db queue listening for `create`, records the event
- web dashboard -> subscribed to the queue, also subscribed to DB/Create, updates a counter on the browser when this happens


### additional resources

- [rooms and namespaces](https://socket.io/docs/rooms-and-namespaces/)
- [socket.io emit cheatsheet](https://socket.io/docs/emit-cheatsheet/)