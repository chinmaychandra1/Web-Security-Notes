# Day 5 – IDOR & Access Control (Web Security)

## What is Access Control?
Access control ensures that users can only perform actions and access resources that they are authorized for.
It is responsible for enforcing permissions after a user is authenticated.

Authentication answers **who you are**, while access control answers **what you are allowed to do**.

---

## Authentication vs Authorization
- **Authentication**: Verifies user identity (login)
- **Authorization**: Verifies permissions (access rights)

A common security mistake is assuming that authenticated users are automatically authorized for all actions.

---

## What is IDOR (Insecure Direct Object Reference)?
IDOR is a type of access control vulnerability where an application exposes internal object references (such as IDs)
and fails to properly verify whether the logged-in user is allowed to access the requested resource.

Example:
/profile?user_id=1001

If changing the ID allows access to another user’s data, it indicates an IDOR vulnerability.

---

## Why IDOR Occurs
- Missing server-side authorization checks
- Trusting user-supplied identifiers
- Assuming frontend restrictions are sufficient
- Insecure API design

IDOR happens because the server does not validate ownership of the requested resource.

---

## Types of IDOR

### Horizontal IDOR
- User accesses another user’s data
- Same privilege level
- Example: User A accessing User B’s profile

---

### Vertical IDOR
- User accesses higher-privileged functionality
- Example: Normal user accessing admin endpoints
- Often leads to full application compromise

---

## Common Locations Where IDOR Occurs
- URL parameters (`id=123`)
- API endpoints
- JSON request bodies
- Hidden form fields
- File download paths
- Mobile application APIs

Any user-controlled identifier should be treated as potentially vulnerable.

---

## IDOR Detection Mindset
- Identify object references controlled by the user
- Modify identifiers and observe responses
- Check for missing permission checks
- Verify access control on the server side
- Never rely on UI restrictions alone

IDOR detection focuses on logic flaws rather than payload injection.

---

## Bug Bounty Relevance
- IDOR often leads to sensitive data exposure
- Can cause account takeover or privilege escalation
- Frequently rated as high or critical severity
- One of the most commonly rewarded vulnerabilities

IDOR vulnerabilities usually require minimal exploitation but have high impact.

---

## GSoC / Open Source Relevance
- Access control is a core security concept in software design
- Open-source projects often need better authorization enforcement
- Improving access control logic is a common security-focused project area
- IDOR prevention requires clear permission and ownership checks

Understanding IDOR helps in building secure backend systems and APIs.

---

## Day 5 Summary
- Understood access control fundamentals
- Learned what IDOR is and why it occurs
- Differentiated between horizontal and vertical IDOR
- Developed a real-world access control testing mindset

---

## Lab Observations (To Be Added Later)
<!--
ADD THIS SECTION LATER:

For each lab, include:
- Vulnerable object reference
- Type of IDOR (Horizontal / Vertical)
- How access control was bypassed
- Why the server-side check failed
- Security impact

Add this section during revision or portfolio polishing.
-->
