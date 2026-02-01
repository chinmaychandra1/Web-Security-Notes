# Day 3 – SQL Injection (Web Security)

## What is SQL Injection?
SQL Injection is a web security vulnerability that allows an attacker to interfere with the SQL queries that an application makes to its database.
It occurs when user-controlled input is directly included in a SQL query without proper validation or sanitization.

---

## Why SQL Injection Occurs
- User input is directly concatenated into SQL queries
- No input validation or sanitization
- Dynamic query construction
- Lack of prepared statements or parameterized queries

At its core, SQL Injection happens because the application trusts user input.

---

## How SQL Injection Works (High-Level)
1. User provides input through a request parameter
2. Application inserts this input into a SQL query
3. Database executes the modified query
4. Attacker gains unintended access to data or functionality

---

## Types of SQL Injection

### 1. Error-Based SQL Injection
In this type, database error messages are returned in the response.
These errors may reveal:
- Database type
- Table or column names
- Query structure

This helps attackers craft more advanced attacks.

---

### 2. UNION-Based SQL Injection
UNION-based SQL Injection allows attackers to combine the results of multiple SELECT queries.
By injecting a UNION SELECT statement, attackers can retrieve data from other tables.

This type often leads to direct data leakage.

---

### 3. Blind SQL Injection
In blind SQL Injection, the application does not display database errors or query results.
Attackers infer information based on:
- Boolean responses (true / false)
- Time delays in server response

Blind SQL Injection is common in real-world applications.

---

## Common SQL Injection Payload Logic
- Injecting special characters to break queries
- Using logical conditions to alter query behavior
- Observing differences in responses
- Identifying how the backend query reacts to input

The focus is on understanding logic, not memorizing payloads.

---

## SQL Injection Detection Mindset
- Identify parameters controlled by the user
- Test how input affects application behavior
- Compare responses for different inputs
- Look for unexpected data exposure or logic bypass

This mindset is crucial for both bug bounty hunting and security tooling.

---

## Bug Bounty Relevance
- SQL Injection can lead to full database compromise
- High-severity and high-impact vulnerability
- Often results in critical security reports

Understanding SQL Injection greatly increases bug bounty success.

---

## GSoC / Open Source Relevance
- Security tools aim to detect SQL Injection patterns
- Prevention techniques include parameterized queries
- Improving SQL Injection detection is a common GSoC project area

Strong SQL Injection knowledge helps in building and improving security tools.

---

## Day 3 Summary
- Learned what SQL Injection is and why it occurs
- Understood major types of SQL Injection
- Developed a detection-focused security mindset
- Completed hands-on labs for practical understanding

---

## Lab Observations (To Be Added)
<!--
ADD THIS SECTION LATER:

For each PortSwigger lab, include:
- Vulnerable parameter name
- Type of SQL Injection
- High-level payload logic (no exact payload required)
- Response behavior change
- Why this confirms SQL Injection

Do NOT rush this section. Add it when revising Day 3.
-->
