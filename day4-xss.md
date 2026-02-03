# Day 4 – Cross-Site Scripting (XSS)

## What is Cross-Site Scripting (XSS)?
Cross-Site Scripting (XSS) is a web security vulnerability that allows attackers to inject and execute malicious JavaScript in the browser of a victim.
XSS occurs when an application includes user input in a web page without proper validation or escaping.

The injected script executes in the context of the vulnerable website.

---

## Why XSS Occurs
- User input is directly rendered in HTML
- Missing or improper output encoding
- Insecure client-side JavaScript handling
- Trusting user-controlled data

At its core, XSS happens because the application trusts user input.

---

## How XSS Works (High-Level)
1. Attacker injects malicious JavaScript via user input
2. Application processes and displays this input
3. Browser executes the injected script
4. Attacker gains control within the user’s browser context

---

## Types of XSS

### 1. Reflected XSS
- Payload is sent in the request
- Reflected immediately in the response
- Usually triggered via a crafted URL
- One-click attack

Reflected XSS is common in search fields and error messages.

---

### 2. Stored XSS
- Payload is stored on the server (database)
- Executed whenever a user visits the affected page
- Impacts multiple users
- High severity vulnerability

Stored XSS is often found in comments, profiles, and feedback forms.

---

### 3. DOM-Based XSS
- Vulnerability exists in client-side JavaScript
- Server response may appear safe
- Browser JavaScript modifies the DOM insecurely

DOM-based XSS depends on unsafe JavaScript sinks and sources.

---

## XSS Contexts (Very Important)
XSS payload behavior depends on where input is injected.

### HTML Context
User input is placed inside HTML content.

### Attribute Context
User input is placed inside HTML attributes.

### JavaScript Context
User input is placed inside JavaScript code.

Payloads must be crafted based on the context to execute successfully.

---

## Common XSS Payload Concept
A simple JavaScript function such as `alert()` is used as a harmless proof-of-concept to confirm JavaScript execution.
The purpose is to demonstrate impact without causing harm.

---

## XSS Detection Mindset
- Identify user-controlled input
- Observe how input appears in the response
- Test if input is executed as JavaScript
- Understand the injection context
- Confirm execution using a safe proof

Detection focuses on behavior, not memorization of payloads.

---

## Bug Bounty Relevance
- XSS can lead to account takeover
- Enables phishing and session abuse
- Stored XSS may affect many users
- Admin-context XSS can lead to full application compromise

XSS is one of the most commonly rewarded vulnerabilities.

---

## GSoC / Open Source Relevance
- Security tools detect XSS patterns
- Frontend frameworks focus on XSS prevention
- Output encoding and sanitization are core security concepts
- XSS detection and mitigation are common open-source project goals

Understanding XSS helps in building secure web applications and tools.

---

## Day 4 Summary
- Learned what XSS is and why it occurs
- Understood reflected, stored, and DOM-based XSS
- Learned the importance of injection context
- Developed a real-world XSS detection mindset

---

## Lab Observations (To Be Added Later)
<!--
ADD THIS SECTION LATER:

For each XSS lab, include:
- Vulnerable parameter or input field
- Type of XSS (Reflected / Stored / DOM)
- Injection context (HTML / Attribute / JS)
- High-level payload logic
- Why this confirms XSS

Add this section during revision or portfolio polishing.
-->
