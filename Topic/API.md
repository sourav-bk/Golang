## API ::
An API, stands for **Application Programming Interface**, is a set of rules and protocols that allows different software applications to communicate and share data with each other.

## REST api ::
REST API ( **Representational State Transfer** Application Programming Interface) is an architectural style that defines a set of rules for how different software applications communicate with each other over the internet or network . Its built on top of http application layer protocol and Using standard HTTP methods like GET, POST, PUT, and DELETE.

It follows a set of rules where resources are identified by URLs, and clients can request or modify these resources by sending HTTP requests to a server. During communication or data exchange with client-server it use Json format.

## GraphQL ::
GraphQL is a query language for APIs and runtime used to fetch and manipulate data from a server. It was developed by Facebook as an alternative to REST APIs, that allowing clients to request exactly the data they need instead of receiving fixed responses. 

In GraphQL, a client sends single request with query specifying the required fields, and the server returns only that data in a structured format. This reduces over-fetching and under-fetching of data, improves performance, and makes APIs more flexible. 

## REST api && GraphQL :: 

In a REST API, the server exposes multiple endpoints (URLs), each representing a specific resource such as users, products, or orders, and the client interacts with those endpoints using standard HTTP methods like GET, POST, PUT, and DELETE. and Request for Specific resource operations like create, update insert and Delete.
As per that server returns a fixed structure of data for each request, which can sometimes result in over-fetching (receiving unnecessary data) or under-fetching (requiring multiple requests to gather all needed data).

GraphQL uses a single endpoint with Standard HTTP POST methods and allows the client to send a flexible query specifying exactly what data it needs. Server then returns only that specific data, that reducing unnecessary data transfer and improving efficiency. 

While REST is simple, widely adopted, and effective for many use cases, GraphQL provides greater flexibility, better performance for complex data requirements, and reduces the number of API calls in modern applications.

