# Day 1 – HTTP Basics for Web Security

## Why HTTP matters in Security
Every web vulnerability (SQLi, XSS, IDOR, CSRF) exists because of how HTTP requests and responses work.
Understanding HTTP is the foundation of bug bounty hunting and building security tools.

---

## What is HTTP?
HTTP (HyperText Transfer Protocol) is a stateless protocol used for communication between:
- Client (Browser)
- Server (Web application)

Each request is independent and does not remember previous requests.

---

## HTTP vs HTTPS
| HTTP | HTTPS |
|----|------|
| Data sent in plain text | Data encrypted using TLS |
| Vulnerable to MITM attacks | Secure communication |
| No certificate | SSL/TLS certificate required |

Security relevance:
- Sensitive data over HTTP can be intercepted
- HTTPS is mandatory for secure authentication

---




## Structure of an HTTP Request
Example:
- GET /login HTTP/1.1
- Host: example.com
- User-Agent: Chrome
- Cookie: sessionid=abc123


### Request Components:
1. **Method** – GET / POST / PUT / DELETE
2. **URL / Path** – Resource being accessed
3. **Headers** – Metadata (cookies, auth, content type)
4. **Body** – Data sent to server (mainly in POST)

---

## Structure of an HTTP Response
Example:

### Response Components:
1. **Status Code**
2. **Headers**
3. **Response Body**

---

## Common HTTP Methods (Security POV)

| Method | Usage | Security Risk |
|------|------|---------------|
| GET | Fetch data | IDOR via URL params |
| POST | Send data | SQLi, XSS |
| PUT | Update data | Unauthorized modification |
| DELETE | Delete data | Broken access control |

---

## Important HTTP Status Codes
| Code | Meaning | Security Context |
|----|--------|----------------|
| 200 | OK | Normal response |
| 301 | Redirect | Open redirect issues |
| 401 | Unauthorized | Auth issues |
| 403 | Forbidden | Access control |
| 404 | Not Found | Endpoint discovery |
| 500 | Server Error | Possible injection |

---

## Headers Important for Security
- **Cookie** – Session management
- **Authorization** – Tokens, JWT
- **Content-Type** – Input handling
- **Referer** – CSRF checks
- **User-Agent** – Client fingerprinting

---

## Cookies & Sessions (Intro)
- Cookies store session identifiers
- Sessions are maintained server-side
- Improper handling leads to:
  - Session hijacking
  - Fixation attacks

---

## Browser as a Security Tool
Using Chrome DevTools:
- Network tab to inspect requests
- Modify parameters
- Observe headers and cookies

This is the first step in real-world bug bounty hunting.

---

## Bug Bounty Relevance
Understanding HTTP helps identify:
- IDOR
- Broken authentication
- Parameter tampering
- Access control flaws

---

## GSoC Relevance
Security tools and scanners analyze:
- HTTP requests
- Parameters
- Headers
- Responses

Strong HTTP knowledge = strong security engineer.

---

## Day 1 Summary
- Learned HTTP fundamentals
- Understood request/response structure
- Explored security relevance
- Set up learning-in-public via GitHub

---


## Practice Screenshots
<img width="1915" height="512" alt="Screenshot 2026-01-31 184420" src="https://github.com/user-attachments/assets/39eb5b5a-22a8-4b4c-a5b1-bd5c6d59b9b5" />
<img width="1900" height="542" alt="Screenshot 2026-01-31 184310" src="https://github.com/user-attachments/assets/e8481033-3cad-467f-999c-a3b30a55245a" />
<img width="1919" height="953" alt="Screenshot 2026-01-31 184218" src="https://github.com/user-attachments/assets/479a1a32-5fab-4aff-9a26-0efc3f43dee2" />

