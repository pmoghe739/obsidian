It is a two directional transport layer which provides a way for the client and the server to communicate with each other seamlessly and without waiting for the other to start or initiate a request .

This can be used to build reactive UIs or automatically self-updating UIs where the server keeps pushing the latest updated data as it is being updated to the website like news feed .

When making an HTTP request and receiving a response, the actual two-way network communication involved takes place over an active TCP/IP connection.

As we now know, WebSockets are built on top of the TCP stack as well

`Normal HTTP request 
```plaintext
GET /index.html HTTP/1.1
Host: www.example.com
```

`Web Socket request
```plaintext
GET /index.html HTTP/1.1
Host: www.example.com
Connection: Upgrade
Upgrade: websocket
```

The `Connection` header tells the server that the client would like to negotiate a change in the way the socket is being used. The accompanying value, `Upgrade`, indicates that the transport protocol currently in use via TCP should change.

When initiating an upgrade to a WebSocket connection, the client must include a `Sec-WebSocket-Key` header with a value unique to that client. `Sec-WebSocket-Key` header with a value unique to that client. Here’s an example:

```plaintext
Sec-WebSocket-Key: BOq0IliaPZlnbMHEBYtdjmKIL38=
```
This is handled automatically at the browser side libraries , we only need to take care of this at the Server-side and response from server should contain 

```plaintext
Sec-WebSocket-Accept: 5fXT1W3UfPusBQv/h6c4hnwTJzk=
```
