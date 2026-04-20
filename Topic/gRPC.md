# RPC
g-RPC RPC ? 

GRPC (stands for Google Remote Procedure Call) open-source Remote Procedure Call (RPC) framework. It was developed by Google and is now part of the Cloud Native Computing Foundation (CNCF).
It's a modern, high-performance framework mostly used for server-to-service or inter-server communication. 

In gRPC, the client application can directly call a method., on the server application., That is on a different machine over the network call as it is just a local Funtion call

g-RPC follow that Devloper is only focus on the business logic regar instanst or palling or under line Implementation.

so g-RPC handels ---

gRPC handels abstracting the complexity of client-server communication. It uses client stubs and server stubs, which are automatically generated from an Interface Definition Language (IDL) specified in a .proto file. These stubs allow developers to call remote methods as if they were local function calls, without writing low-level networking code.

gRPC also handles data serialization and deserialization using Protocol Buffers, ensuring efficient and compact message exchange. It hides the transport layer details (typically HTTP/2), manages request and response handling in a structured way, and provides features like streaming, authentication, and deadlines—making distributed communication more efficient and easier to implement.
 

Core Components::

- The IDL (Interface Definition Language):

This is the "contract" (like a .proto file in gRPC) that defines the methods and data types available for remote execution.

- Stubs (Client & Server):

These are pieces of auto-generated code. The Client Stub acts as a local proxy for the remote service, while the Server Stub (or Skeleton) acts as the receiver that dispatches requests to the actual implementation.

- Serialization (Marshaling):

The mechanism that converts complex data structures (like Go structs) into a platform-independent binary or text format for transmission.

- Transport Layer:

The underlying network protocol, such as HTTP/2, TCP, or UDP, that moves the serialized data from the client to the server.






<hr>

## What gRPC Handles (The Simple Version)
At its heart, gRPC acts as a bridge that makes a remote function call look and feel like a local one. It automates the "busy work" of networking through three main pillars:

1. Code Generation (The "Stubs")
Instead of writing manual networking code, you define your service once in a .proto file (using Protocol Buffers). gRPC then automatically generates:

Client Stubs: Local objects the client calls as if the logic were on its own machine.

Server Skeletons: Pre-built structures the server fills with actual logic.

Result: This "hides" the complexity of the underlying communication, allowing different languages (e.g., Python and Go) to talk to each other seamlessly.

2. Efficient Data Handling
gRPC handles the Serialization and Deserialization (marshaling) of data.

It converts your objects into a highly compressed binary format before sending them.

This is significantly faster and smaller than traditional JSON or XML.

3. Transport & Protocol Management
gRPC abstracts the entire Transport Layer by using HTTP/2. It automatically manages:

Multiplexing: Sending multiple requests over a single connection.

Streaming: Handling one-way or two-way data streams.

Error Handling: Systematically managing status codes, timeouts, and retries.




<hr>
REST is good for Web or browser based comunication but not suitable for inter server comunication

## 1. Handling Non-CRUD Actions::

- The Problem (REST):
REST is resource-based so struggles on Action-Oriented Operations. REST is focuse on only resource based oparation like resource CRUD oparation example like user add update insert and Delete. For every resource oparation need specific end point.\

Also REST may need many API calls to complete one Complex task.

- The RPC Solution :
RPC follow action based oparation so it can handel CRUD or Action based oparation like calculate , notifly , Mailsend etc handel like a local function call.



## 2. Statelessness and Request Overhead :: 
- The Problem (REST):
As we know REST stands for Representational State Transfer. REST is strictly Stateless, menaning that every single request must have necessary context ( Like Authentication tokens, Cookies, Accept-Headers, and Content-Types ).

So that In microservices environment where servers talk to each other thousands of times per second, sending this redundant metadata over and over wastes significant bandwidth.

- The RPC Solution :
RPC can be stateless or stateful depending on the implementation. so it is more faxible. so don't need to resend heavy headers or content-type metadata with every call. This reduces the "per-request overhead" significantly.

## 3. Transport Leayer Protocol ::
- The Problem (REST):
Sending Data and getting Response from server , transport layer REST mostly used Http version 1 or 1.1 over the network call. so it is unidirectional ( like request-response ) communication.

so its slow and not support high speed Streaming  bidirectional  comunication .

- The RPC Solution :
but RPC can use on Transport Leayer HTTP version 2, TCP or other protocols over network for faster bidirectional or unidirectional comunication.



## 4. Data Format and CPU Performance ::

- The Problem (REST):
Sending Data and getting Response from server REST API mostly used Text based format link Json or XML. 
Its take havy CPU timing during Data Serialization/Deserialization

( Serialization/Deserialization : techniques for transforming complex data structure / object into format usually byte stream format suitable for stored on disk or in a buffer and vice versa )

Text based format is suitable for human but not for machine. it is take Large Size as per binary based format.

- The RPC Solution :
so overcome those issue on REST , RPC use   binary based format so that Data Size shoud be  small and during Serialization/Deserialization take less CPU time.  







# what is gRPC ?
- ## what is Protocol Buffers ?
- ## What Problems do Protocol Buffers Solve?
- ## How do Protocol Buffers Work?
- ## What are the Benefits of Using Protocol Buffers?
- ## Who Uses Protocol Buffers?
- ## How do Protocol Buffers Work?

# lifecycle of gRPC?

# type of gRPC ?










