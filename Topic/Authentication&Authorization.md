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




# 🔐 Web & API Authentication Techniques

A structured guide to common authentication methods used in web and API development.

---

## 📌 1. Basic Authentication

### ✅ What is
A simple authentication method where the client sends **username and password with every request**.

### ⚙️ How it works
- User enters username and password  
- Credentials are encoded using Base64  
- Sent in HTTP header:  
  `Authorization: Basic base64(username:password)`

### 🎯 Why used
- Easy to implement  
- No session or token management needed  

### ❌ Drawbacks
- Not secure without HTTPS  
- Credentials exposed in every request  
- No role-based access control  

### 💡 Use Case
- Internal tools  
- API testing (Postman, curl)  
- Simple applications  

---

## 📌 2. Token Authentication

### ✅ What is
A method where a **token replaces the password** after login.

### ⚙️ How it works
- User logs in with credentials  
- Server generates a token  
- Client sends token in every request:  
  `Authorization: Bearer <token>`

### 🎯 Why used
- More secure than Basic Authentication  
- Stateless and scalable systems  

### ❌ Drawbacks
- Token theft gives full access  
- Requires secure client storage  
- Needs expiration handling  

### 💡 Use Case
- REST APIs  
- Mobile applications  
- Single Page Applications (SPA)  

---

## 📌 3. JSON Web Token (JWT)

### ✅ What is
A **self-contained token** that stores authentication data.

### ⚙️ How it works
- User logs in → server generates JWT  
- JWT contains:
  - Header  
  - Payload (user info)  
  - Signature  
- Sent with requests:  
  `Authorization: Bearer <JWT>`

### 🎯 Why used
- No database lookup required  
- Highly scalable  
- Ideal for microservices  

### ❌ Drawbacks
- Difficult to revoke before expiry  
- Larger token size  
- Risk if token is exposed  

### 💡 Use Case
- Microservices architecture  
- Distributed systems  
- Scalable APIs  

---

## 📌 4. OAuth 2.0

### ✅ What is
An **authorization framework** that allows third-party access without sharing passwords.

### ⚙️ How it works
- User selects login via provider (Google, Facebook)  
- Redirects to provider  
- User grants permission  
- Application receives access token  

### 🎯 Why used
- Secure third-party access  
- No password sharing  
- Industry standard  

### ❌ Drawbacks
- Complex setup  
- Requires understanding different flows  
- Dependency on third-party providers  

### 💡 Use Case
- Social login (Google, Facebook)  
- Third-party integrations  
- API authorization  

---

## 📌 5. Multi-Factor Authentication (MFA)

### ✅ What is
Authentication requiring **multiple verification factors**.

### ⚙️ How it works
User provides:
- Password (something you know)  
- OTP/device (something you have)  
- Biometrics (something you are)  

### 🎯 Why used
- Adds strong security  
- Reduces risk of unauthorized access  

### ❌ Drawbacks
- Extra login steps  
- May impact user experience  
- Requires additional setup  

### 💡 Use Case
- Banking systems  
- Financial applications  
- Secure enterprise systems  

---

## 📌 6. Single Sign-On (SSO)

### ✅ What is
A system where one login provides access to **multiple applications**.

### ⚙️ How it works
- User logs in via Identity Provider (IdP)  
- IdP verifies identity  
- Access granted to connected systems  

### 🎯 Why used
- Improved user experience  
- Centralized authentication  

### ❌ Drawbacks
- Single point of failure  
- Complex implementation  
- Risk if compromised  

### 💡 Use Case
- Enterprise systems  
- Corporate tools (email, HR, CRM)  
- Cloud-based platforms  

---

## 📌 7. Session-Based Authentication

### ✅ What is
A traditional authentication method where the server creates a **session after login**.

### ⚙️ How it works
- User logs in  
- Server creates session ID  
- Session stored on the server  
- Client stores session ID in cookie  
- Cookie sent with each request  

### 🎯 Why used
- Easy to manage sessions  
- Allows immediate logout  

### ❌ Drawbacks
- Not scalable (server storage needed)  
- Requires session management  
- Vulnerable to session hijacking  

### 💡 Use Case
- Traditional web applications  
- Server-rendered apps  
- Banking portals  

---

## ⚡ Quick Summary

- **Basic** → Simple but insecure  
- **Token/JWT** → Modern API authentication  
- **OAuth** → Third-party login  
- **MFA** → Extra security layer  
- **SSO** → One login, multiple systems  
- **Session** → Traditional web apps  

---

✅ **Tip:** Combine **JWT + OAuth + MFA** for building secure modern applications.


