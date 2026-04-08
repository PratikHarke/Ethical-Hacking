# 🛡️ SQL Injection Prevention

## 🔐 1. Prepared Statements

Use parameterized queries:

```python
cursor.execute("SELECT * FROM users WHERE username = ?", (username,))
```

---

## 🔐 2. Input Validation
- Validate user input
- Restrict unexpected characters

---

## 🔐 3. ORM Usage
Use frameworks like:
- Django ORM
- SQLAlchemy

---

## 🔐 4. Least Privilege
- Database users should have limited access

---

## 🔐 5. Web Application Firewall (WAF)
- Detect and block malicious queries

---

## 🧠 Key Takeaways
- Never trust user input
- Use secure coding practices
- Prevention is simple but often ignored
