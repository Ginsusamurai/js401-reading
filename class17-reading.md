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
  - developed by ISO
  - application layer is an array of specific protocols
  - presentation -> chars and nums -> to Machine (via translation) and reducs the bits via compression (lossy, lossless), and encrypted with SSL
  - session -> sets up and manages the connections, including termination. authentication used. a session is opened for every individual file to track the receiving of data and ensure completeness
  - transport -> from session, data is cut in to segments. ports and unit number for each so that 1 object can be split up and recombined. client can tell server to slow down if data rate is not possible (phone vs T1). if something doesn't arrive, repeat data sent. UDP is faster, but can lose data. TCP gaurantees delivery.
  - network -> packets move between networks. each packet has sender and recipient IP. paths determination optimize speed of transport
  - data link layer -> logical (network layer) and physical addressing (data link layer). MAC address is included in sender to receiver on the packet. Each network interface card has a built in MAC. allows for data to be transfered via 'framing'. as data moves, each piece packet is put in a 'frame'. these frames nest over and over until unwound on the recipient. also watches the means of transmission and waits for a gap to send data.
  - physical layer -> this is actually changing the bits to a signal and up through the layers to be deciphered
- [TCP handshakes explained](https://www.youtube.com/watch?v=xMtP5ZB3wSk)

### skim

- [OSI Model](https://www.cloudflare.com/learning/ddos/glossary/open-systems-interconnection-model-osi/)
  
- [What is TCP](https://searchnetworking.techtarget.com/definition/TCP)
- [Build a tcp server(code only)](https://techbrij.com/node-js-tcp-server-client-promisify)
- [node docs: net module](https://nodejs.org/api/net.html)