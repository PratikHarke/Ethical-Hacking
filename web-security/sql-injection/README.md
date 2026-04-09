# 💉 SQL Injection

## 📌 Overview
SQL Injection (SQLi) is a web vulnerability that occurs when user-controlled input is inserted into SQL queries without proper sanitization or parameterization.

This allows an attacker to interfere with query logic and, in severe cases, read, modify, or delete database data.

---

## 🎯 Objective
This module is designed to:

- explain how SQL Injection works
- demonstrate common attack patterns
- show why certain payloads succeed
- highlight prevention and defensive thinking

---

## 🧠 Core Concept

Applications often build database queries using input from users.

A vulnerable example:

```sql
SELECT * FROM users WHERE username = 'input' AND password = 'input';
```

If the application directly inserts the input into the query, an attacker may break out of the intended logic and inject SQL syntax.

---

## 🧠 Types of SQL Injection

### 1. In-Band SQL Injection
The attacker receives results through the same channel used to deliver the request.

#### a. Error-Based SQLi
Database errors reveal information about the query structure, table names, or columns.

#### b. Union-Based SQLi
The attacker combines the original query with another query using `UNION SELECT`.

---

### 2. Blind SQL Injection
The application does not directly reveal database output, so the attacker infers results indirectly.

#### a. Boolean-Based Blind SQLi
Different responses appear depending on whether a condition is true or false.

#### b. Time-Based Blind SQLi
The attacker triggers a delay to confirm whether a condition is true.

---

## ⚠️ Possible Impact

- authentication bypass
- disclosure of usernames and passwords
- exposure of sensitive business data
- modification or deletion of records
- in some cases, full compromise of the application backend

---

## 🔬 Real-World Relevance
SQL Injection remains one of the most important web security issues because it targets the trust boundary between user input and database execution.

Even when modern frameworks reduce risk, poorly written code, legacy applications, and weak filtering can still make systems vulnerable.

---

## 🛡️ Defender Perspective
From a defensive point of view, SQLi exists because the application treats untrusted input as executable database logic.

The main defensive goal is simple:

- keep user input as data
- never allow it to become part of SQL syntax

---

## 🧾 Key Takeaways

- SQLi happens when input changes query logic
- simple payloads can lead to serious impact
- prevention depends on secure query design, not blacklists alone
