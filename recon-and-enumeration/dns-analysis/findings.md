# 🔎 DNS Findings and Analysis

## 🧠 What Can Be Discovered

### 1. IP Addresses
- Target server location

---

### 2. Subdomains
Example:
```
admin.example.com
mail.example.com
```

👉 May expose hidden services

---

### 3. Mail Servers (MX Records)
- Email infrastructure

---

### 4. Name Servers (NS Records)
- DNS hosting details

---

### 5. DNS Misconfigurations
- Open DNS zones
- Exposed internal records

---

## ⚠️ Potential Vulnerabilities

- Subdomain takeover
- Information leakage
- Misconfigured DNS records

---

## 🧾 Example Scenario

Using `dig`:

```bash
dig example.com ANY
```

👉 May reveal:
- A records
- MX records
- NS records

---

## 🧠 Key Takeaways
- DNS analysis helps map target infrastructure
- Small leaks can lead to bigger attacks
