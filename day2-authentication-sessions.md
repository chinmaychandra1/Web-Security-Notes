# Day 2 – Authentication, Sessions & JWT (Web Security)

## Why Authentication is Critical in Web Security
Authentication is responsible for verifying user identity. If authentication or session handling is weak, attackers can take over accounts, access sensitive data, and escalate privileges.
Most high-impact bug bounty vulnerabilities are related to broken authentication and session management.

---

## Authentication vs Authorization

### Authentication
Authentication answers the question: **Who are you?**
Examples:
- Username and password
- OTP
- Token-based login

### Authorization
Authorization answers the question: **What are you allowed to do?**
Examples:
- Accessing admin panel
- Viewing or editing specific resources

Security Issue:
- When authorization is missing or weak, it leads to vulnerabilities like IDOR.

---

## High-Level Login Flow
1. User enters username and password
2. Browser sends credentials to the server
3. Server verifies credentials
4. Server creates a session or token
5. Session ID or JWT is sent to the browser
6. Browser sends this data with every future request

Understanding this flow is essential for testing authentication issues.

---

## What are Cookies?
Cookies are small key-value pairs stored in the browser and sent with every request to the server.

Example:

Cookies are mainly used to:
- Maintain login state
- Store session identifiers
- Track user preferences

---

## Important Cookie Attributes (Security Perspective)

### HttpOnly
- Prevents JavaScript from accessing cookies
- Protects against cookie theft via XSS

### Secure
- Cookie is sent only over HTTPS
- Prevents sniffing attacks

### SameSite
- Controls cross-site cookie usage
- Helps mitigate CSRF attacks

### Path and Domain
- Define where the cookie is valid
- Improper scope can lead to access control issues

---

## What are Sessions?
Sessions store user-related data on the **server side**.
The browser stores only a session ID (usually in a cookie).

Server maps:

Sessions help maintain state in a stateless HTTP protocol.

---

## Session Lifecycle
1. Session is created after successful login
2. Session ID is stored in browser cookie
3. Session ID is sent with each request
4. Session is destroyed on logout or expiry

Security issue occurs if sessions are not properly invalidated.

---

## Cookie vs Session

| Cookie | Session |
|------|--------|
| Stored in browser | Stored on server |
| Client-side | Server-side |
| Less secure if misconfigured | More secure |
| Can be modified by user | Controlled by server |

In practice, sessions use cookies to store session IDs.

---

## What is JWT (JSON Web Token)?
JWT is a stateless authentication mechanism.
Instead of storing session data on the server, all required information is stored inside the token.

JWT format:

JWT is commonly used in APIs and modern web applications.

---

## JWT Structure

### Header
- Token type
- Signing algorithm

### Payload
- User data
- Claims (user id, role, expiry)

### Signature
- Ensures token integrity
- Prevents tampering

---

## JWT Security Risks
- Weak or leaked secret key
- Sensitive data stored in payload
- Missing expiration (`exp`)
- Storing JWT in localStorage (XSS risk)

Best practice: store JWT in HttpOnly cookies.

---

## Common Authentication Vulnerabilities

### Broken Authentication
- Weak passwords
- No rate limiting
- Credential stuffing attacks

### Session Fixation
- Attacker sets a known session ID
- Victim logs in using same session
- Attacker reuses session

### Session Hijacking
- Stealing cookies via XSS
- Insecure HTTP cookies

### IDOR (Insecure Direct Object Reference)
Example:
Changing user_id may expose other users’ data.

---

## Using Browser DevTools for Auth Testing
- Network tab: inspect login requests
- Application tab: view cookies and storage
- Check if session ID changes after login
- Verify logout properly invalidates session

These checks are the first step in real-world bug bounty hunting.

---

## Bug Bounty Relevance
- Account takeover vulnerabilities
- Privilege escalation
- IDOR and access control issues
- Session handling flaws

---

## GSoC / Open Source Relevance
- Secure authentication implementation
- Session management improvements
- Auth testing and security tooling
- Reducing auth-related vulnerabilities in projects

---

## Day 2 Summary
- Understood authentication vs authorization
- Learned cookies, sessions, and JWT basics
- Studied login flow and common auth vulnerabilities
- Practiced analyzing authentication using browser tools

---

## Personal Observation 
While testing a login page:
- Session cookie changes after login
- Cookie is invalidated on logout
- JWT storage location observed
