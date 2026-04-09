# 🛡️ XSS Prevention

## 🎯 Goal
Ensure user input is never executed as code in the browser.

---

## 🔐 1. Output Encoding

Convert special characters:

```html
&lt;script&gt;
```

---

## 🔐 2. Input Validation

- restrict unexpected characters
- validate formats

---

## 🔐 3. Content Security Policy (CSP)

Restrict script execution:

```
Content-Security-Policy: default-src 'self'
```

---

## 🔐 4. HTTPOnly Cookies

Prevent JavaScript access:

```
Set-Cookie: session=xyz; HttpOnly
```

---

## 🔐 5. Use Secure Frameworks

Frameworks like React escape output by default.

---

## ❌ What Not to Do

- blocking only `<script>`
- relying only on filtering
- trusting client-side validation

---

## 🧠 Defender Thinking

- where is user input rendered?
- is it encoded?
- can scripts execute?

---

## 🧾 Key Takeaways

- encoding is critical
- CSP adds strong protection
- prevention requires layered defense
