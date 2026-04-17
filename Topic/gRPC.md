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






# what is gRPC ?
- ## what is Protocol Buffers ?
- ## What Problems do Protocol Buffers Solve?
- ## How do Protocol Buffers Work?
- ## What are the Benefits of Using Protocol Buffers?
- ## Who Uses Protocol Buffers?
- ## How do Protocol Buffers Work?

# lifecycle of gRPC?

# type of gRPC ?

