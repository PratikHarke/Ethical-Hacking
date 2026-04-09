# ⚡ Cross-Site Scripting (XSS)

## 📌 Overview
Cross-Site Scripting (XSS) is a web vulnerability that allows attackers to inject malicious scripts into web pages viewed by other users.

Unlike server-side attacks, XSS executes in the **victim’s browser**, making it dangerous for session theft and user impersonation.

---

## 🎯 Objective
- Understand how XSS works
- Learn different types of XSS
- Analyze attack execution
- Explore prevention techniques

---

## 🧠 Core Concept

Applications that reflect user input without proper sanitization allow attackers to inject JavaScript.

Example:

```html
<input value="user_input">
```

If not encoded, attacker-controlled input becomes executable.

---

## 🧠 Types of XSS

### 1. Reflected XSS
- Input is reflected immediately in response
- Common in search forms

---

### 2. Stored XSS
- Payload is stored in database
- Executes when users view affected page

---

### 3. DOM-Based XSS
- Happens in client-side JavaScript
- No server involvement

---

## ⚠️ Impact

- session hijacking  
- cookie theft  
- account takeover  
- malicious redirects  

---

## 🔬 Real-World Relevance
XSS is widely found in modern web apps, especially where input is dynamically rendered.

---

## 🧠 Defender Perspective

XSS occurs when applications fail to treat user input as **untrusted data**.

Goal:
- never allow input to become executable code

---

## 🧾 Key Takeaways

- XSS executes in the browser  
- depends on poor input/output handling  
- can lead to full account compromise  
