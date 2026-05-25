## Authentication
Authentication is.. the process of verifying, who you are (Proving your identity).

Exp - User Enter, email and password on system/software. The system/software checks, If the credentials match, user are authenticated. The system/software now knows who User are.

### Web & API Authentication Techniques
- Basic Authentication
- Token Authentication
- JSON Web Tokens (JWT)
- OAuth 2.0
- Multi-Factor Authentication (MFA)
- Single Sign-On (SSO)
- Session Based Authentication
  
## Authorization
Authorization is.. what you can do (Your permissions and access rights).

Exp - Once user logged-in/authenticated, user attempt to do some activity/access some resources, During that The system checks user profile's assigned Role (e.g., "Editor" vs. "Viewer") and as per the permission, User do the activity/access some resources. If not have permission, The system/software will denies the request. 








# Authentication Methods Overview

A breakdown of the primary authentication and authorization methods used in modern software development.

## 1. Basic Authentication
Basic authentication (Basic Auth) is a simple, built-in HTTP security method where a client (like a web browser or API tool) sends a request containing a username and password. The system encodes this data using Base64 and verifies the credentials before granting access to protected resources

- How it works :
  1. Client sends username + password in every request.
  2. Credentials are Base64 encoded in HTTP header: Authorization: Basic base64(username:password)
     

* **Mechanism**: Sends raw username and password in the HTTP header.
* **Format**: Credentials are encoded in Base64 (`Authorization: Basic <credentials>`).
* **Security**: Highly insecure unless paired strictly with HTTPS.
* **Use Case**: Simple internal APIs or legacy systems.

## 2. Session-Based Authentication
* **Mechanism**: Server validates credentials and stores a session in memory or a database.
* **Storage**: Server returns a unique `session_id` stored in a user cookie.
* **State**: Stateful method because the server must track every active session.
* **Use Case**: Traditional monolithic web applications.

## 3. Token Authentication
* **Mechanism**: Server exchanges credentials for a unique, random string (token).
* **Storage**: Client stores the token and sends it in subsequent headers.
* **State**: Can be stateless if the token contains encrypted data.
* **Use Case**: Mobile apps and basic REST APIs.

## 4. JSON Web Tokens (JWT)
* **Mechanism**: A specific compact, URL-safe type of token authentication.
* **Structure**: Composed of three parts: Header, Payload, and Signature.
* **State**: Completely stateless; the server verifies the signature without database lookups.
* **Use Case**: Modern microservices, single-page applications (SPAs), and mobile apps.

## 5. OAuth 2.0
* **Mechanism**: An authorization framework, not just a simple authentication protocol.
* **Function**: Allows third-party apps to access resources without exposing user passwords.
* **Components**: Uses access tokens, refresh tokens, scopes, and authorization servers.
* **Use Case**: "Sign in with Google/Apple" buttons and API integrations.

## 6. Single Sign-On (SSO)
* **Mechanism**: Allows a user to log in once and access multiple independent systems.
* **Protocols**: Built on top of protocols like SAML 2.0 or OpenID Connect (OIDC).
* **Benefit**: Eliminates password fatigue and centralizes user identity management.
* **Use Case**: Enterprise corporate networks and cloud software suites.

## 7. Multi-Factor Authentication (MFA)
* **Mechanism**: Requires two or more verification factors to gain access.
* **Factors**: Something you know (password), have (token/phone), or are (biometrics).
* **Layer**: Acts as an additional security layer on top of any method above.
* **Use Case**: Securing sensitive accounts, banking, and corporate logins.



# 🔐 Web & API Authentication Techniques

---




# 🔐 Web & API Authentication Techniques

---

## 1. Basic Authentication

### 1. What is
A simple authentication method where the client sends username and password with every request.

### 2. How it works
- User enters credentials  
- Credentials are encoded using Base64  
- Sent in HTTP header:  
  `Authorization: Basic base64(username:password)`

### 3. Characteristics
- Stateless (no server storage)  
- Simple and easy to implement  
- Credentials sent on every request  

### 4. Drawbacks
- Not secure without HTTPS  
- Credentials can be intercepted  
- No session or role control  

### 5. Use Case
- Internal tools  
- Testing APIs  
- Simple applications  

---

## 2. Token Authentication

### 1. What is
A method where a token (instead of password) is used to access resources after login.

### 2. How it works
- User logs in with credentials  
- Server generates a token  
- Client sends token in each request:  
  `Authorization: Bearer <token>`

### 3. Characteristics
- Stateless  
- Server doesn’t store session  
- Token represents user identity  

### 4. Drawbacks
- Token theft gives access  
- Requires secure storage on client  
- Token expiration handling needed  

### 5. Use Case
- REST APIs  
- Mobile apps  
- Single Page Applications (SPA)  

---

## 3. JSON Web Token (JWT)

### 1. What is
A self-contained token that securely carries user data and authentication info.

### 2. How it works
- User logs in → server generates JWT  
- JWT contains:
  - Header  
  - Payload (user info)  
  - Signature  
- Sent with requests:  
  `Authorization: Bearer <JWT>`

### 3. Characteristics
- Stateless  
- Self-verifiable (no DB lookup)  
- Contains user roles and expiry  

### 4. Drawbacks
- Hard to revoke before expiry  
- Large token size  
- Risk if token is exposed  

### 5. Use Case
- Microservices  
- Distributed systems  
- Scalable APIs  

---

## 4. OAuth 2.0

### 1. What is
An authorization framework that allows apps to access user data from another service without sharing passwords.

### 2. How it works
- User chooses login via Google/Facebook  
- Redirect to provider  
- User grants permission  
- App receives access token  

### 3. Characteristics
- Delegated access  
- Uses access & refresh tokens  
- Supports multiple flows  

### 4. Drawbacks
- Complex to implement  
- Requires understanding flow types  
- Dependency on third-party provider  

### 5. Use Case
- Social login  
- Third-party integrations  
- API authorization systems  

---

## 5. Multi-Factor Authentication (MFA)

### 1. What is
Authentication requiring more than one verification factor.

### 2. How it works
User must provide:
- Password (something you know)  
- OTP / device (something you have)  
- Biometrics (something you are)  

### 3. Characteristics
- Adds extra security layer  
- Combines multiple authentication methods  

### 4. Drawbacks
- Extra step for users  
- Can impact user experience  
- Requires additional setup  

### 5. Use Case
- Banking systems  
- Financial apps  
- High-security platforms  

---

## 6. Single Sign-On (SSO)

### 1. What is
A system where a user logs in once and accesses multiple applications.

### 2. How it works
- User logs in via Identity Provider (IdP)  
- IdP verifies identity  
- Grants access to multiple services  

### 3. Characteristics
- Centralized authentication  
- Uses SAML, OAuth, OIDC  
- Improves user experience  

### 4. Drawbacks
- Single point of failure  
- Complex setup  
- If compromised → access to all systems  

### 5. Use Case
- Enterprise environments  
- Corporate applications  
- Cloud services access  

---

## 7. Session-Based Authentication

### 1. What is
Traditional authentication where the server creates a session for the user after login.

### 2. How it works
- User logs in  
- Server creates session ID  
- Session stored on server  
- Client stores ID in cookie  
- Cookie sent with each request  

### 3. Characteristics
- Stateful (server stores sessions)  
- Session tied to user  

### 4. Drawbacks
- Not scalable (needs server storage)  
- Requires session management  
- Can be vulnerable to session hijacking  

### 5. Use Case
- Traditional web applications  
- Server-rendered apps  
- Banking portals  

---

## ✅ Quick Revision

- **Basic** → simplest but least secure  
- **Token/JWT** → modern API authentication  
- **OAuth** → third-party access  
- **MFA** → extra security  
- **SSO** → one login for many apps  
- **Session** → traditional web apps  

---
``


