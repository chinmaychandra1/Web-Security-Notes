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

## Practice Screenshots
<img width="1915" height="512" alt="Screenshot 2026-01-31 184420" src="https://github.com/user-attachments/assets/39eb5b5a-22a8-4b4c-a5b1-bd5c6d59b9b5" />
<img width="1900" height="542" alt="Screenshot 2026-01-31 184310" src="https://github.com/user-attachments/assets/e8481033-3cad-467f-999c-a3b30a55245a" />
<img width="1919" height="953" alt="Screenshot 2026-01-31 184218" src="https://github.com/user-attachments/assets/479a1a32-5fab-4aff-9a26-0efc3f43dee2" />

