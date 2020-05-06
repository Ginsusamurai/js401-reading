# Socket.io

## web sockets

- bidirectional com protocol with client and server over TCP

## Socket.io

- library for real-time dubplex communication
- uses `websocket` protocol for interface
  - client side: library in the browser
  - server side: library in node.js

## connections

- TCP -> connect directly to server with keep-alive connection
- socket.io -> connect over http, kept alive by websocket protocol

## messaging

- uses same as node events, `emit()` and `on()`
- socket.io allows for shared events with 'disconnected' participants through a server
- clients connect, emit events, respond to events from server

#### process

  - clients connect to a socket on a server
    - can be solo or in groups
  - a client speaks to the server
  - server listens for `speak`
  - server does a `broadcast` or `emit`
  - other cliens that may be able to `hear` on that message as well


#### additional 

- [web sockets](https://en.wikipedia.org/wiki/WebSocket)
- [socket.io tutorial](https://www.tutorialspoint.com/socket.io/)
- [socket.io vs web sockets](https://www.educba.com/websocket-vs-socket-io/)
- [socket.io documentation](https://socket.io/docs/)
- [socket.io server api](https://socket.io/docs/server-api)
- [socket.io client api](https://socket.io/docs/client-api)
- [socket testing tool](https://amritb.github.io/socketio-client-tool/)