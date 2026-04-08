# 🛡️ XSS Prevention

## 🔐 1. Input Sanitization
- Remove dangerous characters
- Validate user input

---

## 🔐 2. Output Encoding
- Encode HTML entities

Example:
```html
&lt;script&gt;
```

---

## 🔐 3. Content Security Policy (CSP)
- Restrict script execution

---

## 🔐 4. Use Framework Security Features
- React, Angular auto-escape output

---

## 🔐 5. HTTPOnly Cookies
- Prevent JavaScript access to cookies

---

## 🧠 Key Takeaways
- Never trust user input
- Always sanitize and encode output
