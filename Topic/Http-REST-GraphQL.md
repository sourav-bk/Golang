HTTP (HyperText Transfer Protocol) is the foundation of data communication on the World Wide Web. It is an application-layer protocol and transport layer it used TCP protocol for transferring web resources such as HTML documents, images, videos, APIs, etc., 

HTTP follows client-server model, with a client opening a connection to make a request, then waiting until it receives a response from the server. HTTP is a stateless protocol, meaning that the server does not keep any session data between two requests, although the later addition of cookies adds state to some client-server interactions.



Key Concepts of HTTP:

***Client →*** sends requests (e.g., your browser)

***Server →*** processes requests and sends responses

- ***HTTP request contains:***
    - Request Header
      - Start line method name ( GET, POST, PUT, DELETE )
      - request URI
      - Protocol version ( 1 , 1.1 , 2 , 3 )
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






# HTTP Request Structure and Contents

An HTTP Request is a message sent by a client (such as a web browser or mobile app) to a server to initiate an action or retrieve a resource. Every request follows a strict, standardized format.

---

## The 4 Main Components

```text
+------------------------------------------------------------+

| 1. Request Line (Method, Path, HTTP Version)               |
+------------------------------------------------------------+

| 2. HTTP Headers (Metadata: Host, Content-Type, etc.)       |
+------------------------------------------------------------+

| 3. Blank Line (CRLF - Crucial separator)                   |
+------------------------------------------------------------+

| 4. Message Body (Optional data: JSON, Form Data, XML)      |
+------------------------------------------------------------+
```

### 1. Request Line
The very first line of the request. It specifies the operation to perform.
* **Method (Verb):** The action required. Common ones include:
  * `GET`: Fetches a resource.
  * `POST`: Submits new data to the server.
  * `PUT` / `PATCH`: Modifies or updates existing resources.
  * `DELETE`: Removes a resource.
* **Request Target (URI):** The path to the target resource on the server (e.g., `/index.html`, `/api/v2/users`).
* **HTTP Version:** The protocol version being utilized (e.g., `HTTP/1.1`, `HTTP/2`).

### 2. HTTP Headers
Key-value pairs containing metadata about the request, the client environment, and the preferred response format.
* `Host`: The domain name of the server (e.g., `://example.com`). *Required in HTTP/1.1*.
* `Content-Type`: The format of the data inside the body (e.g., `application/json`, `text/html`).
* `Authorization`: Credentials or tokens used to authenticate the client with the server.
* `User-Agent`: Information about the client software making the request (e.g., Chrome, Safari, Python-requests).

### 3. Blank Line
A mandatory empty line (`\r\n` or CRLF) that explicitly marks the end of the HTTP headers and the beginning of the body payload.

### 4. Message Body (Optional)
The data payload sent to the server. 
* **When it is used:** Primarily used with data-submitting methods like `POST`, `PUT`, and `PATCH`.
* **When it is empty:** Typically omitted in `GET` and `DELETE` requests, where all query details live in the URL path.

---

## Raw HTTP Request Example

Below is an authentic raw example of a `POST` request submitting JSON data to a server:

```http
POST /api/v1/login HTTP/1.1
Host: example.com
Content-Type: application/json
Content-Length: 45
Authorization: Bearer mock_token_123

{
  "username": "developer_alpha",
  "pin": 1234
}
```
