# TCP Servers

## Event Queues

- all events are on the `eventEmitter` constructor
- can pass data to the listeners with thsi
- 'disconnect' services can communicate this way via a central hub server or queue

## OSI Model

- `Open Systems Interconnection Reference Model` (osi model) has 7 layers
- not all networks use all 7 layers, but it's a common reference to use

## Internet Protocol Suite 

- called `TCP/IP` because they were the original protocols used
- 4 layers -> link, internet, transport, application

## TCP

- `transmission control protocol`
- two way coms between hosts, limits rates of senders to ensure reliable delivery
- IP packet between hosts carries TCP segment
- a segment has a header and data section

### TCP Header

- source port, destination port, sequence number, acknowledgement number, dataoffset/nsflag/3 undef bits, FLAGSSSSS, window size, checksum, urgent pointer, options

### Connection Establishment

- client sends a SYN packet, with random initial numbers.
- server sends back acknowledgement with same number +1.
- client sends ACK with number +1

### Connection Termination

- one end sends a FIN segment and the other an ACK followed by FIN


## Addtional resources

### videos

- [OSI model explained](https://www.youtube.com/watch?v=vv4y_uOneC0)
- [TCP handshakes explained](https://www.youtube.com/watch?v=xMtP5ZB3wSk)

### skim

- [OSI Model](https://www.cloudflare.com/learning/ddos/glossary/open-systems-interconnection-model-osi/)
- [What is TCP](https://searchnetworking.techtarget.com/definition/TCP)
- [Build a tcp server(code only)](https://techbrij.com/node-js-tcp-server-client-promisify)
- [node docs: net module](https://nodejs.org/api/net.html)