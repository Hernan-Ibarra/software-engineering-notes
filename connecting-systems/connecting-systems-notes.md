# Notes on HTTP/1.1

## What is HTTP?

HTTP stands for (H)yper (T)ext (T)ransfer (P)rotocol. It is a set of rules and procedures (i.e. a protocol) for sending and requesting data over the internet. Here 'data' could mean a variety of things, most commonly HTML files, but also images, text, and other kinds of media.

Since the creation of the HTTP in the 90s, it has undergone constant revisions and updates. Different versions and variants of the protocol exist. As of 2024, we have HTTP/1.1, HTTP/2, and HTTP/3 as the main non-obsolete versions. A popular alternative to HTTP is HTTPS, a secure variant of the protocol, where data transfer happens by means of encryption. 

In these notes we focus on HTTP/1.1, which is the oldest still-in-use version of HTTP.

## How does HTTP work?

Oversimplifying, the client tries to establish a connection with the server. After the server accepts this, it waits for a request message from the client. All data is transferred via request-response messages. Once the server gets a request message it sends data to the client; this usually consists of a *header*, which contains information about the message and the request, and a *body* with the actual data. 

One of the main differences between HTTP/1.1 and its predecessors, is its keep-alive-mechanism. This means that after the request-response transaction is finished, the server doesn't end the connection but rather keeps it open in case there are further requests, hence optimizing how the speed at which the client gets data from its request: it is not necessary that they connect and disconnect to the server constantly.

### Methods

Requests from the client to the server come in different types. HTTP standarized different types of requests using *methods* which we now describe. A method is a specifc keyword or function that announces the kind of request the client makes to the server. Here are some examples.

- The most fundamental method is **GET**. By using the **GET** method, the client announces that it wants to be sent a specific resource, say an HTML file, from the server. 

- If the client wants to send data and request it be stored in a particular location on the server-side  (creating a new file, or replacing an existing file if necessary), the client will use the **PUT** method.

- On the other hand, if the client wants to delete a file on the server-side we are looking at the **DELETE** method. 

One example of a method that is exclusive to versions 1.1 and newer is the **OPTIONS** method, which asks the server which operations/requests it is willing to accept. 

### Status codes

We have talked about how the client communicates with the server. What about the other way around? HTTP has designated *status codes* that the server sends to the client to indicate how the server is handling requests.

There are many codes, but they are subdivided into 5 categories:

- **1xx: Informational**: These codes are just meant to convey that the request is being processed. Here HTTP/1.1 introduced the request code **100 Continue**. This is used when the server is not certain it can process requests, maybe due to their size, or because they lack the right authorizations. In such cases the client can send only the headers of their request, without the body. If the server thinks the request is OK they send the code 100 to ask the user to *continue* and send the body of the original request.

- **2xx: Success**: These are used when the server wants to communicate that a previous client request was handled successfully. 

- **3xx: Redirection**: When the server cannot process the request without further action, it sends a 3xx code.

- **4xx: Client Error**: If the server is unhappy with the request, and thinks its the client's fault, it gives one of the 4xx codes, the most famous one of these being, of course, **404 Not Found**.

- **5xx: Sever Error**: If the server is unhappy with the request, but it is the server's fault, one of the 5xx codes is used.

## Other differences

One of the main differences between HTTP/1.1 and its predecessors is the ability to do *chunked transfer encoding*. This means that the content transfer in the client-server model is done in *chunks*, i.e. in small parts at the time. This way of streaming information means that the server doesn't need to know the size of the data in advance, because it is being dynamically generated. 

