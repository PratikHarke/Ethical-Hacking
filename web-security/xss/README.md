# ⚡ Cross-Site Scripting (XSS)

## 📌 Overview
Cross-Site Scripting (XSS) is a vulnerability that allows attackers to inject malicious scripts into web pages viewed by other users.

---

## 🎯 Objective
- Understand XSS attacks
- Learn how scripts are injected
- Explore prevention techniques

---

## 🧠 How It Works

A web app reflects user input without sanitization:

```html
<input value="user_input">
```

If input is not escaped, attacker can inject JavaScript.

---

## 🧠 Types of XSS

### 1. Reflected XSS
- Input reflected immediately in response

### 2. Stored XSS
- Payload stored in database
- Executes when users view it

### 3. DOM-based XSS
- Occurs in client-side JavaScript

---

## ⚠️ Impact
- Session hijacking
- Cookie theft
- Account takeover
- Defacement

---

## 🔬 Real-World Relevance
XSS is one of the most common vulnerabilities in web applications.

---

## 🧾 Key Takeaways
- Happens due to lack of input/output sanitization
- Can execute arbitrary JavaScript
