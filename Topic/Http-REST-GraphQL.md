HTTP (HyperText Transfer Protocol) is the foundation of data communication on the World Wide Web. It is an application-layer protocol and transport layer it used TCP protocol for transferring web resources such as HTML documents, images, videos, APIs, etc., 

HTTP follows client-server model, with a client opening a connection to make a request, then waiting until it receives a response from the server. HTTP is a stateless protocol, meaning that the server does not keep any session data between two requests, although the later addition of cookies adds state to some client-server interactions.



Key Concepts of HTTP:

***Client →*** sends requests (e.g., your browser)

***Server →*** processes requests and sends responses

- ***HTTP request contains:***
    - Request Header
      - Start line method name ( GET, POST, PUT, DELETE )
      - request URI
      - Protocol version (1.1 , 2 )
      - Content-Type (HTML, json, xml)
  
    - Request Body (optional)
      - A body consists of data in any format (HTML, json, xml) 
      - The format must match that specified by the Content-Type header 

      
- ***HTTP request contains:***
  
    - Header
      - The start line includes a method name
      - a request URI
      - the protocol version
  
    - Body
      - A body consists of data in any forma.
      - The format must match that specified by the Content-Type header 
