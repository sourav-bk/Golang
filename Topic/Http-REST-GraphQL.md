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




# HTTP Response Structure

An HTTP response is a structured message sent by a server to a client in reply to an HTTP request. It follows a standardized format to inform the client of the request's outcome and deliver any requested data.

## Core Structure
An HTTP response consists of four main parts:

1. **Status Line**: The first line of the response.
   * **HTTP Version**: The protocol version (e.g., `HTTP/1.1`).
   * **Status Code**: A three-digit number indicating the result (e.g., `200`).
   * **Reason Phrase**: A short text description of the status (e.g., `OK`).
2. **HTTP Headers**: Metadata about the response or the server formatted as `Name: Value` pairs.
   * `Content-Type`: Declares the media type (e.g., `application/json`).
   * `Content-Length`: The size of the body in bytes.
   * `Cache-Control`: Instructions for caching the response.
3. **Empty Line**: A mandatory blank line separating headers from the body.
4. **Message Body (Optional)**: The actual data requested by the client (HTML, images, JSON, etc.).

---

## Example HTTP Response

```http
HTTP/1.1 200 OK
Date: Fri, 29 May 2026 12:28:53 GMT
Server: Apache/2.4.1
Content-Type: text/html
Content-Length: 138

<html>
  <head><title>Example</title></head>
  <body><p>Hello World!</p></body>
</html>
```

---

## Status Code Categories

* **1xx (Informational)**: Request received, continuing process.
* **2xx (Success)**: Action was successfully received and accepted.
* **3xx (Redirection)**: Further action must be taken to complete the request.
* **4xx (Client Error)**: The request contains bad syntax or cannot be fulfilled.
* **5xx (Server Error)**: The server failed to fulfill a valid request.









# HTTP Request and Response Structures

Every HTTP communication consists of a request from a client and a response from a server. Both follow a highly structured, textual format.

---

## 1. HTTP Request Structure

An HTTP request is issued by a client to trigger an action on a server. It consists of four distinct sections:

### A. Request Line (Start-Line)
The very first line of the request. It contains three components separated by spaces:
* **HTTP Method:** The action to perform (e.g., `GET`, `POST`, `PUT`, `DELETE`).
* **Request Target:** The path or absolute URL of the resource (e.g., `/index.html`).
* **HTTP Version:** The protocol version being used (e.g., `HTTP/1.1`).

### B. Request Headers
Key-value pairs that pass additional metadata about the client and the request.
* **Host:** The domain name of the target server (Required in HTTP/1.1).
* **User-Agent:** Identifies the client software (browser, OS, or application).
* **Accept:** Specifies the content types the client can handle (e.g., `text/html`, `application/json`).

### C. Empty Line
A mandatory blank line (`\r\n`) indicating that the header section is complete.

### D. Request Body (Optional)
Contains data sent to the server. This is typically omitted for `GET` requests but required for data-submitting methods like `POST` or `PUT` (e.g., JSON payloads, form data).

### Request Example
```http
POST /api/users HTTP/1.1
Host: ://example.com
User-Agent: Mozilla/5.0
Content-Type: application/json
Content-Length: 35

{
  "name": "Alice",
  "role": "Admin"
}
```

---

## 2. HTTP Response Structure

An HTTP response is the server's acknowledgment and answer to the client's request. It mirrors the request structure closely:

### A. Status Line (Start-Line)
The first line of the response. It contains three components:
* **HTTP Version:** The protocol version (e.g., `HTTP/1.1`).
* **Status Code:** A 3-digit numeric code indicating the result (e.g., `200`, `404`, `500`).
* **Reason Phrase:** A brief, human-readable description of the status code (e.g., `OK`, `Not Found`).

### B. Response Headers
Key-value pairs providing metadata about the server and the returned payload.
* **Server:** Details about the server software handling the request.
* **Content-Type:** The MIME type of the document in the body (e.g., `text/html; charset=UTF-8`).
* **Content-Length:** The size of the response body in bytes.

### C. Empty Line
A mandatory blank line separating the metadata headers from the actual data payload.

### D. Response Body (Optional)
The core content requested by the client. It holds the HTML code, images, file downloads, or API data.

### Response Example
```http
HTTP/1.1 200 OK
Date: Fri, 29 May 2026 12:00:00 GMT
Server: Apache/2.4.41
Content-Type: application/json
Content-Length: 43

{
  "status": "success",
  "id": 10293
}
```


