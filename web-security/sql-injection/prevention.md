# 🛡️ SQL Injection Prevention

## 🎯 Goal
The goal of prevention is to ensure that user input is always treated as data, never as part of executable SQL syntax.

---

## 🔐 1. Use Parameterized Queries

This is the most effective defense.

Example in Python:

```python
cursor.execute("SELECT * FROM users WHERE username = ? AND password = ?", (username, password))
```

### Why this works
The database separates query structure from user input values.

This prevents the input from changing the intended logic of the SQL statement.

---

## 🔐 2. Avoid Dynamic Query Concatenation

Unsafe pattern:

```python
query = "SELECT * FROM users WHERE username = '" + username + "'"
```

### Why this is dangerous
The application gives the attacker direct control over query syntax.

---

## 🔐 3. Validate Input

Input validation helps reduce unexpected input, but it is not a complete defense by itself.

Useful validation includes:

- expected data types
- length limits
- allowlists for structured values

---

## 🔐 4. Use Least Privilege for Database Accounts

The application database user should only have the permissions it actually needs.

### Example
If the app only reads data, it should not also be able to drop tables or modify administrative records.

---

## 🔐 5. Hide Detailed SQL Errors

Verbose database errors can reveal:

- table names
- column names
- SQL syntax issues
- backend database type

Attackers can use this information to refine payloads.

---

## 🔐 6. Use Secure Framework Features

ORMs and modern frameworks can reduce risk when used correctly, though misuse can still create vulnerabilities.

Examples:
- Django ORM
- SQLAlchemy
- parameterized database libraries

---

## ❌ What Not to Rely On

Do not rely only on:

- blacklisting specific keywords
- stripping single quotes
- blocking one known payload
- trusting client-side validation

Attackers can often bypass these controls.

---

## 🧠 Defender Thinking

A defender should ask:

- Where does user input touch the database?
- Are all queries parameterized?
- Can error messages leak internal structure?
- Does the database account have excessive privileges?

---

## 🧾 Key Takeaways

- parameterized queries are the strongest core defense
- prevention is about secure design, not just input filtering
- defense should assume attackers will adapt payloads
