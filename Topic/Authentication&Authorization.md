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


