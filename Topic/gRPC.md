# RPC

1. Handling Non-CRUD Actions ::

REST is resource-based so struggles on Action-Oriented Operations:

REST is focuse on resource based oparation like resource CRUD oparation example like user add update insert and Delete. For every resource oparation need specific end point.

BUT RPC follow action based oparation so it can handel CRUD or Action based oparation like calculate , notifly , Mailsend etc handel like a local function call.

so REST  may need many API calls to complete one Complex task.


2. REST api is stateless ::

As we know REST stands for REpresentational State Transfer and it is stateless, menaning that every single request must have necessary context ( Content-types, accept headers, Authorization headers ).
But RPC can be stateless or stateful depending on the implementation. so it is more faxible. 


3. Transport Leayer protocols ::
REST APIs primarily use HTTP/1.1 (or HTTP/2) for stateless, resource-oriented communication. RPC APIs are more flexible, often using HTTP (JSON-RPC) or HTTP/2 (gRPC). 
While REST relies solely on standard HTTP methods (GET, POST, PUT, DELETE), RPC can use HTTP/2, TCP, or other protocols for faster, procedure-based


4. Payload Efficiency ::

Basically for Communication purposes Data send or receive REST API mostly used Text based format link Json or XML. It is take high time to convert between serialization and deserialization.

also that text based format (like json, xml ) payload for getting response getting bigger memory bcz of repication of some same content. but RPC use binary formate. so data repication and data formate take less or more opimize Payload. so it make first and efficiency . 

5. Streaming and Multiplexing ::









1. Action-Oriented vs. Resource-Oriented
The Problem with REST: REST forces every action into a CRUD (Create, Read, Update, Delete) model. This creates "Semantic Friction" when you need to perform an action that isn't a resource, such as ProcessPayment or CalculateTax. You end up with "hacky" URLs like POST /orders/1/calculate-and-validate.

The RPC Solution: RPC is Procedure-Based. It treats operations as functions. You don't have to map your business logic to a "resource"; you simply call a function. This is more natural for complex workflows, reducing the number of API calls needed to complete a single multi-step task.

2. Statelessness and Flexibility
The Problem with REST: By definition, REST is strictly stateless. While this is great for scaling, it forces the client to send the entire context (Auth tokens, headers, metadata) with every single request, which increases bandwidth overhead.

The RPC Solution: RPC offers architectural flexibility. While it can be stateless, it also supports Stateful connections and Long-lived streams. Because gRPC (a modern RPC) keeps a persistent connection open via HTTP/2, you don't need to re-negotiate headers or resend heavy metadata for every small interaction.

3. Protocol and Transport Layer
The Problem with REST: REST is traditionally "bound" to the HTTP semantics. It relies heavily on HTTP verbs and status codes, which can be limiting when you need lower-level control or non-standard communication.

The RPC Solution: RPC is Transport-Agnostic. While gRPC uses HTTP/2 for its advanced features (like multiplexing), other RPC implementations can run directly over raw TCP or even UDP. This allows for significantly lower latency and faster data transmission than the standard HTTP/1.1 request-response cycle.

4. Payload Efficiency and Serialization
The Problem with REST: JSON is human-readable, but it is expensive for machines.

Size: Every message repeats field names (e.g., "username": "admin"), which bloats the payload.

CPU Cost: Parsing text into objects is a heavy CPU task.

The RPC Solution: RPC (via Protobuf) uses Binary Serialization.

Compactness: It uses field tags (numbers) instead of string names, making the payload up to 5x–10x smaller than JSON.

Speed: Converting binary to a Go struct is a direct memory operation, making serialization and deserialization significantly faster and reducing CPU load on your servers.








# what is gRPC ?
- ## what is Protocol Buffers ?
- ## What Problems do Protocol Buffers Solve?
- ## How do Protocol Buffers Work?
- ## What are the Benefits of Using Protocol Buffers?
- ## Who Uses Protocol Buffers?
- ## How do Protocol Buffers Work?

# lifecycle of gRPC?

# type of gRPC ?











1. Handling Non-CRUD Actions::

REST is resource-based so struggles on Action-Oriented Operations:

REST is focuse on resource based oparation like resource CRUD oparation example like user add update insert and Delete. For every resource oparation need specific end point.

BUT RPC follow action based oparation so it can handel CRUD or Action based oparation like calculate , notifly , Mailsend etc handel like a local function call.

so REST  may need many API calls to complete one Complex task.


2. Statelessness and Request Overhead ::

As we know REST stands for REpresentational State Transfer and it is stateless, menaning that every single request must have necessary context ( Content-types, accept headers, Authorization headers ).
But RPC can be stateless or stateful depending on the implementation. so it is more faxible. 


3. Transport Leayer Protocol ::

Sending Data and getting Response from server , transport layer REST mostly used Http version 1 or 1.1 over the network call. so it is unidirectional ( like request-response ) communication.
so its slow and not support high spreed Streaming  bidirectional  comunication .
but RPC can use on Transport Leayer HTTP/2, TCP or other protocols over network for faster bidirectional or unidirectional comunication.



4. Data Format and CPU Performance ::
Sending Data and getting Response from server REST API mostly used Text based format link Json or XML. 
Its take havy CPU timing during Data Serialization/Deserialization ( techniques for transforming complex data structure / object into format usually byte stream format suitable for stored on disk or in a buffer and 
vice versa ). 

Text based format is suitable for human but not for machine. it is take Large Size as per binary based format.

so overcome those issue on REST , RPC use   binary based format so that Data Size shoud be  small and during Serialization/Deserialization take less CPU time.  





