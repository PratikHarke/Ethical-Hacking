# 💉 SQL Injection

## 📌 Overview
SQL Injection (SQLi) is a web security vulnerability that allows attackers to manipulate SQL queries by injecting malicious input into application fields.

---

## 🎯 Objective
- Understand how SQL Injection works
- Perform basic exploitation
- Learn prevention techniques

---

## 🧠 How It Works

A vulnerable query:

```sql
SELECT * FROM users WHERE username = 'input';
```

If user input is not sanitized, an attacker can inject SQL code.

---

## 🧠 Types of SQL Injection

### 1. In-Band SQLi
- Error-based
- Union-based

### 2. Blind SQLi
- Boolean-based
- Time-based

---

## ⚠️ Impact
- Authentication bypass
- Data leakage
- Database manipulation
- Full system compromise

---

## 🔬 Real-World Relevance
SQL Injection is part of the OWASP Top 10 vulnerabilities and is still widely exploited.

---

## 🧾 Key Takeaways
- Occurs due to improper input handling
- Easy to exploit
- Critical impact
