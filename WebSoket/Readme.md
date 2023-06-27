## How is web sockets different from HTTP?

- Connection type: HTTP is a request-response protocol, where the client sends a request to the server, and the server responds with a response. WebSockets, on the other hand, provide a full-duplex, persistent connection between the client and the server that allows data to be transmitted in both directions at any time.
- Data format: HTTP is a text-based protocol that uses structured messages (requests and responses) in a specific format. WebSockets use a binary protocol that allows for more efficient transmission of data and can transmit any type of data, not just text.
- Efficiency: Because HTTP requires a new request and response for each piece of data sent between the client and the server, it can be less efficient than WebSockets, which use a persistent connection to transmit data more efficiently.
- Real-time capabilities: HTTP is not designed for real-time communication, and while techniques like long-polling can be used to simulate real-time communication, it is not as efficient as WebSockets, which are specifically designed for real-time communication.
- Support for server-initiated updates: HTTP requests are always initiated by the client, whereas WebSockets can support server-initiated updates, where the server can send data to the client at any time without the client first requesting it.



## What are web sockets?

- WebSockets are a communication protocol that allows real-time bidirectional data transfer between a client and a server over a single, persistent TCP connection. Unlike traditional HTTP requests, which are stateless and require a new connection to be established for each request, WebSockets allow for a long-lived connection to be established between a client and a server, enabling both the client and the server to send and receive data at any time without the overhead of establishing a new connection.
- WebSockets are particularly useful for applications that require real-time data transfer, such as online gaming, chat applications, financial trading platforms, and other applications that require constant, low-latency communication between a client and a server.
- example how WebSockets work in practice:
    - 1) The client sends an HTTP request to the server requesting to open a WebSocket connection.
    - 2) The server responds with an HTTP response containing an "Upgrade" header that indicates that the connection is being upgraded to a WebSocket connection.
    - 3) The client and server negotiate the WebSocket protocol version and other parameters, and establish a persistent TCP connection between the client and the server.
    - 4) Once the WebSocket connection is established, both the client and the server can send data to each other at any time, without the need to establish a new connection.
    - 5)The data sent over the WebSocket connection is encapsulated in frames, which contain a header and a payload. The header specifies the type of data contained in the frame, such as text or binary data, and whether the frame is the final frame in a sequence of frames. The payload contains the actual data being sent.
    - 6) When the client or server wants to close the WebSocket connection, they send a special close frame to the other end of the connection, indicating that the connection is being closed.




## Differences between webhooks and WebSockets

- Webhooks are used for one-way communication from a source application to a destination application, while WebSockets facilitate two-way communication between server and client.
- Webhooks are mostly used by two servers to pass information, while WebSockets are used primarily for server-to-client (mostly web browsers) communication.
- Also, webhooks close the socket connection on the receiving application once a response has been sent back, while WebSockets keep the connection open for as long as required and not just for a single transfer of information.
- In terms of communication protocols, WebSocket uses its own custom WS protocol while webhooks use regular HTTP.