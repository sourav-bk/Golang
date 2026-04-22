# RPC

RPC most commonly stands for Remote Procedure Call, a software communication protocol that allows a program on one computer to execute code on another computer (server) without needing to understand the network details. It acts like a local function call.


REST is good for Web or browser based comunication but not suitable for inter server comunication

#### 1. Handling Non-CRUD Actions ::

- ***The Problem (REST):***

  REST is resource-based so struggles on Action-Oriented Operations. REST is focuse on only resource based oparation like resource CRUD oparation example like user add update insert and Delete. For every resource oparation need specific end point.

  Also REST may need many API calls to complete one Complex task.

- ***The RPC Solution :***

  RPC follow action based oparation so it can handel CRUD or Action based oparation like calculate , notifly , Mailsend etc handel like a local function call.

#### 2. Statelessness and Request Overhead :: 

- ***The Problem (REST):***

  As we know REST stands for Representational State Transfer. REST is strictly Stateless, menaning that every single request must have necessary context ( Like Authentication tokens, Cookies, Accept-Headers, and Content-Types ).

  So that In microservices environment where servers talk to each other thousands of times per second, sending this redundant metadata over and over wastes significant bandwidth.

- ***The RPC Solution :***

  RPC can be stateless or stateful depending on the implementation. so it is more faxible. so don't need to resend heavy headers or content-type metadata with every call. This reduces the "per-request overhead" significantly.

#### 3. Transport Leayer Protocol ::

- ***The Problem (REST):***

  Sending Data and getting Response from server , transport layer REST mostly used Http version 1 or 1.1 over the network call. so it is unidirectional ( like request-response ) communication.

  so its slow and not support high speed Streaming  bidirectional  comunication .

- ***The RPC Solution :***

  but RPC can use on Transport Leayer HTTP version 2, TCP or other protocols over network for faster bidirectional or unidirectional comunication.

#### 4. Data Format and CPU Performance ::

- ***The Problem (REST):***

  Sending Data and getting Response from server REST API mostly used Text based format link Json or XML.
  Its take havy CPU timing during Data Serialization/Deserialization.

( Serialization/Deserialization : techniques for transforming complex data structure / object into format usually byte stream format suitable for stored on disk or in a buffer and vice versa )
  
   Text based format is suitable for human but not for machine. it is take Large Size as per binary based format.

- ***The RPC Solution :***

  so overcome those issue on REST , RPC use   binary based format so that Data Size shoud be  small and during Serialization/Deserialization take less CPU time.  

# g-RPC

g-RPC (stands for Google Remote Procedure Call) open-source Remote Procedure Call (RPC) framework. It was developed by Google and is now part of the Cloud Native Computing Foundation (CNCF).
It's a modern, high-performance framework mostly used for server-to-server or Inter-server communication. 

In g-RPC, the client application can directly call a method., on the server application., That is on a different machine over the network call as it is just a local Funtion call.

g-RPC follow that Developer is only focus on the business logic rather than instant of planning or under-line Implementation.

## Protocol Buffers (Protobuf)

Protocol Buffers is a concrete technology developed by Google. gRPC use protocol buffers as both the IDL (for Interface Definition Language ) and the serialization format (for converting data into binary format).

- #### The IDL (Interface Definition Language) and .proto file :
  
  g-RPC handels abstracting the complexity of client-server communication. It uses IDL(Interface Definition Language) which written in .proto file. It's a simple "contract" for the server and client. Contents means Defines messages (data structures) and services (RPC methods).
  
  - #### Stubs:
    Then .proto file use into the protoc compiler to generate code for client stubs and server skeletons in various languages (Go, Java, Python, etc.).
    
    - ***Client Stub:*** Provides local methods that the client can call directly. It handles the serialization of parameters and sends them over HTTP/2 Protocol, to the server.
    - ***Server Skeleton (or Base Class):*** Implements the service methods defined in the .proto file, allowing the server to handle incoming requests.
  
  These stubs allow developers to call remote methods as like local function calls, by abstracts the entire Transport Layer (that internally used HTTP/2), without writing low-level networking code.
  
- #### Data Format :
  gRPC uses Protocol Buffers, Its a binary-based format, for client–server data exchange. This approach minimizes data size from any other text bases format (like Json,XML) and improves performance by reducing CPU time during serialization and deserialization.

  gRPC manages request and response handling in a structured way, and provides features like streaming, authentication, and deadlines—making distributed communication more efficient and easier to implement.

  

At the transport layer, gRPC uses the HTTP/2 protocol. HTTP/2 is faster than HTTP/1 and supports faster bidirectional communication. ( Also unidirectional )
gRPC supports four primary types of service methods that define how clients and servers exchange messages: 

- ***Unary RPC:*** The simplest form, where the client sends a single request and receives a single response, similar to a traditional function call.
- ***Server Streaming RPC:*** The client sends one request and receives a stream of multiple messages from the server. The client reads from the stream until there are no more messages.
- ***Client Streaming RPC:*** The client sends a sequence of messages to the server. Once the client finishes sending, it waits for the server to process the entire stream and return a single response.
- ***Bidirectional Streaming RPC:*** Both the client and server send a sequence of messages using a read-write stream. The two streams operate independently, allowing messages to be sent and received in any order. 

# Implementation of gRPC server in Go

# Advanced Features of gRPC

gRPC also offers several advanced features that make developing and debugging distributed systems easier:

- ***Synchronous and Asynchronous Calls:***

  gRPC supports both synchronous and asynchronous RPC calls. Synchronous calls wait for the remote server to return a response before continuing. Asynchronous calls return immediately and the response is handled as a separate task.

- ***Metadata:***

  gRPC allows you to attach metadata to calls. This metadata can be used to describe services and methods, helping clients find the right services and their methods. Developers can also use metadata to validate calls.

- ***Channels:***

  gRPC channels allow simultaneously sending and receiving multiple calls. This can improve performance by enabling the server to handle multiple requests simultaneously.

- ***Interceptors:***

  gRPC supports interceptors, which are a powerful mechanism for extending gRPC functionality. They can be used for logging, authentication, monitoring, and more.

- ***Deadlines/Timeouts:***

  gRPC allows clients to specify how long they are willing to wait for an RPC to complete. The gRPC framework will automatically cancel the RPC if it exceeds this deadline.


# Why use gRPC?
There are several reasons you may want to use the gRPC framework for developing your APIs.

- ***1. Broad language support***
  
gRPC has broad language support. It's widely supported in most modern languages and frameworks, including Java, Ruby, Go, Node.js, Python, C#, and PHP. As mentioned above, gRPC clients can invoke any function just GET and making it more versatile than traditional APIs.

- ***2. Smaller message size***

gRPC messages are smaller than traditional RESTful API messages because the binary message formats—Protocol Buffers—are smaller and faster to parse than text-based formats like JSON. This results in faster transmission between the client and the server.

- ***3. Faster communication***

HTTP/2 is more efficient than older protocols like HTTP/1.1—allowing gRPC to reduce network bandwidth usage and decrease latency. Also, since the messages are smaller, they can be transferred more quickly between servers and clients. This also helps to reduce the load on the network and provides a smoother user experience.

- ***4. Streaming Connection***

Another advantage of gRPC is its support for streaming connection mode. Streaming mode sends or receives data in chunks, which can improve performance when the data is too large to send or receive at once. This allows clients to continuously receive data from the server without waiting for the entire response to arrive. As a result, users don't have to wait until all the data transfer is complete.

During streaming, the connection between the client and the server is maintained, meaning no data is lost or corrupted while transmitted. gRPC streaming is ideal for real-time applications like chat or gaming.

- ***5. Pluggable Support***

gRPC supports plugging in load balancing, tracing, health checking, and authentication. This makes it easy to set up and manage high-performance systems. gRPC is modular, so it's simple to set up and configure its different feature sets.

- ***6. Strong Typing***

gRPC uses Protocol Buffers, which provide strong typing for messages. This can help catch errors at compile-time rather than runtime, leading to more robust and reliable systems.

- ***7. Code Generation***

gRPC automatically generates client and server code from your service definitions. This can significantly reduce the amount of boilerplate code you need to write and maintain.



# Advanced Features of gRPC?

# Disadvantages  Features of gRPC?

# gRPC

<hr>

# what is gRPC ?
- ## what is Protocol Buffers ?
- ## What Problems do Protocol Buffers Solve?
- ## How do Protocol Buffers Work?
- ## What are the Benefits of Using Protocol Buffers?
- ## Who Uses Protocol Buffers?
- ## How do Protocol Buffers Work?

# lifecycle of gRPC?

# type of gRPC ?










