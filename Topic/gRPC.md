# RPC
REST is good for Web or browser based comunication but not suitable for inter server comunication

### 1. Handling Non-CRUD Actions ::

- ***The Problem (REST):***

  REST is resource-based so struggles on Action-Oriented Operations. REST is focuse on only resource based oparation like resource CRUD oparation example like user add update insert and Delete. For every resource oparation need specific end point.

  Also REST may need many API calls to complete one Complex task.

- ***The RPC Solution :***

  RPC follow action based oparation so it can handel CRUD or Action based oparation like calculate , notifly , Mailsend etc handel like a local function call.

### 2. Statelessness and Request Overhead :: 

- ***The Problem (REST):***

  As we know REST stands for Representational State Transfer. REST is strictly Stateless, menaning that every single request must have necessary context ( Like Authentication tokens, Cookies, Accept-Headers, and Content-Types ).

  So that In microservices environment where servers talk to each other thousands of times per second, sending this redundant metadata over and over wastes significant bandwidth.

- ***The RPC Solution :***

  RPC can be stateless or stateful depending on the implementation. so it is more faxible. so don't need to resend heavy headers or content-type metadata with every call. This reduces the "per-request overhead" significantly.

### 3. Transport Leayer Protocol ::

- ***The Problem (REST):***

  Sending Data and getting Response from server , transport layer REST mostly used Http version 1 or 1.1 over the network call. so it is unidirectional ( like request-response ) communication.

  so its slow and not support high speed Streaming  bidirectional  comunication .

- ***The RPC Solution :***

  but RPC can use on Transport Leayer HTTP version 2, TCP or other protocols over network for faster bidirectional or unidirectional comunication.

### 4. Data Format and CPU Performance ::

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










