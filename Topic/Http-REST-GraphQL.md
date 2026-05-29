# HTTP (HyperText Transfer Protocol)

## Overview

HTTP (HyperText Transfer Protocol) is the foundation of communication on the World Wide Web. It is an **Application Layer Protocol** that uses **TCP** as the transport protocol to transfer resources such as:

- HTML pages
- Images
- Videos
- APIs
- JSON/XML data

HTTP follows a **Client-Server Architecture**:

- **Client** → Sends HTTP requests (Browser, Mobile App, Postman, etc.)
- **Server** → Processes requests and returns HTTP responses

### Key Characteristics

- Stateless protocol
- Request-Response communication model
- Human-readable text-based protocol
- Supports multiple versions:
  - HTTP/1.0
  - HTTP/1.1
  - HTTP/2
  - HTTP/3

> Since HTTP is stateless, the server does not remember previous requests. Cookies, Sessions, and Tokens are commonly used to maintain state.

---

# HTTP Request

An HTTP Request is sent by a client to a server to fetch or modify a resource.

## Request Structure

```text
+--------------------------------------------------+
| Request Line                                     |
+--------------------------------------------------+
| Headers                                          |
+--------------------------------------------------+
| Blank Line                                       |
+--------------------------------------------------+
| Body (Optional)                                  |
+--------------------------------------------------+
```

## 1. Request Line

The first line of an HTTP request.

```http
POST /api/users HTTP/1.1
```

Contains:

| Component | Description |
|------------|------------|
| Method | Action to perform |
| URI/Path | Target resource |
| HTTP Version | Protocol version |

### Common HTTP Methods

| Method | Purpose |
|----------|---------|
| GET | Retrieve data |
| POST | Create new resource |
| PUT | Replace existing resource |
| PATCH | Partially update resource |
| DELETE | Remove resource |

---

## 2. Request Headers

Headers provide additional information about the request.

### Common Request Headers

| Header | Purpose |
|----------|---------|
| Host | Target server/domain |
| Content-Type | Format of request body |
| Authorization | Authentication credentials |
| User-Agent | Information about client |
| Accept | Expected response format |

Example:

```http
Host: example.com
Content-Type: application/json
Authorization: Bearer token
User-Agent: Chrome
```

---

## 3. Blank Line

A mandatory empty line (`CRLF`) that separates headers from the body.

---

## 4. Request Body (Optional)

Contains data sent to the server.

Usually used with:

- POST
- PUT
- PATCH

Example:

```json
{
  "name": "Sourav",
  "role": "Backend Developer"
}
```

---

## Complete HTTP Request Example

```http
POST /api/v1/login HTTP/1.1
Host: example.com
Content-Type: application/json
Authorization: Bearer token123

{
  "username": "developer",
  "password": "secret"
}
```

---

# HTTP Response

An HTTP Response is sent by the server back to the client after processing the request.

## Response Structure

```text
+--------------------------------------------------+
| Status Line                                      |
+--------------------------------------------------+
| Headers                                          |
+--------------------------------------------------+
| Blank Line                                       |
+--------------------------------------------------+
| Body (Optional)                                  |
+--------------------------------------------------+
```

---

## 1. Status Line

The first line of the response.

```http
HTTP/1.1 200 OK
```

Contains:

| Component | Description |
|------------|------------|
| HTTP Version | Protocol version |
| Status Code | Result of request |
| Reason Phrase | Human-readable status |

---

## 2. Response Headers

Provide metadata about the response.

### Common Response Headers

| Header | Purpose |
|----------|---------|
| Content-Type | Type of returned content |
| Content-Length | Size of response body |
| Cache-Control | Caching rules |
| Server | Server information |

Example:

```http
Content-Type: application/json
Content-Length: 128
Cache-Control: no-cache
```

---

## 3. Blank Line

Separates response headers from response body.

---

## 4. Response Body (Optional)

Contains actual data returned by the server.

Examples:

- HTML
- JSON
- XML
- Images
- Files

Example:

```json
{
  "status": "success",
  "id": 10293
}
```

---

## Complete HTTP Response Example

```http
HTTP/1.1 200 OK
Date: Fri, 29 May 2026 12:00:00 GMT
Server: Apache/2.4.41
Content-Type: application/json

{
  "status": "success",
  "message": "User created successfully"
}
```

---

# HTTP Status Codes

HTTP status codes indicate the outcome of a request.

# HTTP Status Codes

HTTP status codes are three-digit numbers returned by a server to indicate the result of a client's request.

| Category | Code | Status | Description |
|----------|------|---------|-------------|
| **1xx Informational** | 100 | Continue | Request received, continue sending data. |
|  | 101 | Switching Protocols | Server agrees to switch protocols. |
|  | 102 | Processing | Server is processing the request. |
| **2xx Success** | 200 | OK | Request completed successfully. |
|  | 201 | Created | New resource created successfully. |
|  | 202 | Accepted | Request accepted for processing. |
|  | 204 | No Content | Request successful, no content returned. |
| **3xx Redirection** | 301 | Moved Permanently | Resource permanently moved to another URL. |
|  | 302 | Found | Resource temporarily moved. |
|  | 303 | See Other | Redirect to another resource using GET. |
|  | 304 | Not Modified | Cached version is still valid. |
|  | 307 | Temporary Redirect | Temporary redirect with same HTTP method. |
|  | 308 | Permanent Redirect | Permanent redirect with same HTTP method. |
| **4xx Client Error** | 400 | Bad Request | Invalid request syntax or parameters. |
|  | 401 | Unauthorized | Authentication required. |
|  | 403 | Forbidden | Access denied. |
|  | 404 | Not Found | Requested resource not found. |
|  | 405 | Method Not Allowed | HTTP method not supported. |
|  | 408 | Request Timeout | Request took too long. |
|  | 409 | Conflict | Conflict with current resource state. |
|  | 415 | Unsupported Media Type | Unsupported request content type. |
|  | 422 | Unprocessable Entity | Validation failed. |
|  | 429 | Too Many Requests | Rate limit exceeded. |
| **5xx Server Error** | 500 | Internal Server Error | Generic server-side error. |
|  | 501 | Not Implemented | Feature not supported by server. |
|  | 502 | Bad Gateway | Invalid response from upstream server. |
|  | 503 | Service Unavailable | Server temporarily unavailable. |
|  | 504 | Gateway Timeout | Upstream server did not respond in time. |

## Most Common HTTP Status Codes for REST APIs

| Code | Status | Common Usage |
|------|---------|-------------|
| 200 | OK | Successful GET request |
| 201 | Created | Successful POST request |
| 204 | No Content | Successful DELETE request |
| 400 | Bad Request | Invalid request payload |
| 401 | Unauthorized | Missing or invalid token |
| 403 | Forbidden | Permission denied |
| 404 | Not Found | Resource does not exist |
| 409 | Conflict | Duplicate resource |
| 422 | Unprocessable Entity | Validation error |
| 429 | Too Many Requests | API rate limit exceeded |
| 500 | Internal Server Error | Unexpected server error |



---

# HTTP Request vs Response

| Feature | Request | Response |
|----------|----------|----------|
| Sent By | Client | Server |
| Purpose | Ask for resource/action | Return result |
| First Line | Request Line | Status Line |
| Contains Headers | Yes | Yes |
| Contains Body | Optional | Optional |

---

# Quick Interview Summary

- HTTP stands for HyperText Transfer Protocol.
- It is an Application Layer Protocol.
- Uses TCP for communication.
- Follows Client-Server architecture.
- Stateless by nature.
- Request contains:
  - Request Line
  - Headers
  - Blank Line
  - Body (Optional)
- Response contains:
  - Status Line
  - Headers
  - Blank Line
  - Body (Optional)
- Common methods: GET, POST, PUT, PATCH, DELETE.
- Common status codes:
  - 200 OK
  - 201 Created
  - 400 Bad Request
  - 401 Unauthorized
  - 404 Not Found
  - 500 Internal Server Error
 











