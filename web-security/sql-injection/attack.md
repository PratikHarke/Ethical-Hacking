# ⚔️ SQL Injection Attack Analysis

## 🧠 Scenario

Assume an application has a login form with two fields:

- username
- password

The backend uses a query like this:

```sql
SELECT * FROM users WHERE username = 'input' AND password = 'input';
```

This becomes dangerous if the application directly concatenates input into the SQL query.

---

## 🚀 Step 1: Identify a Potential Injection Point

Typical places to test:

- login forms
- search bars
- URL parameters
- filters and sort inputs
- hidden request parameters

A tester first looks for places where user input affects database-backed functionality.

---

## 🚀 Step 2: Send a Simple Test Character

A common first test is a single quote:

```sql
'
```

### Why this matters
A single quote may break the query syntax if the input is placed inside a string.

### What the tester looks for
- SQL errors
- unusual response differences
- changed application behavior

This helps confirm whether input is reaching the database layer unsafely.

---

## 🚀 Step 3: Test Authentication Bypass

A classic payload:

```sql
' OR 1=1 --
```

If placed in the username field, the query may become:

```sql
SELECT * FROM users WHERE username = '' OR 1=1 -- ' AND password = 'anything';
```

---

## 🧠 Why This Works

This works because:

1. the original string is closed with `'`
2. `OR 1=1` adds a condition that is always true
3. `--` comments out the rest of the query in many SQL dialects

As a result, the database may evaluate the WHERE clause as true and return rows without validating the password correctly.

---

## 🧪 Example

### Input
```text
username: ' OR 1=1 --
password: anything
```

### Possible Outcome
```text
Login successful
```

---

## 🚀 Step 4: Explore for Data Extraction

After confirming injection, the attacker may try to understand the query structure.

Example:

```sql
' ORDER BY 1 --
' ORDER BY 2 --
' ORDER BY 3 --
```

### Goal
Find how many columns are returned by the original query.

Then test:

```sql
' UNION SELECT NULL,NULL --
```

### Goal
Match the original query shape and inject attacker-controlled output.

---

## 🧠 Attacker Thinking

At this stage, the attacker is asking:

- Can I break the query syntax?
- Can I influence the WHERE clause?
- Can I discover the number of columns?
- Can I make the server return database data?
- Can I identify the backend database from errors or behavior?

This is what separates random payload testing from methodical exploitation.

---

## ❌ When This Fails

This attack may fail when:

- prepared statements are used
- the application sanitizes or parameterizes input correctly
- a WAF blocks obvious payloads
- the database user has restricted privileges
- response differences are hidden and require blind techniques

---

## 🛡️ Defensive Insight

The correct fix is not to block `' OR 1=1 --` specifically.

Attackers can modify payloads in many ways.

The real fix is:

- parameterized queries
- strict input handling
- least-privileged database accounts
- secure error handling

---

## 🧾 Key Takeaways

- successful SQLi usually begins with small syntax tests
- authentication bypass is often just the first stage
- real understanding comes from knowing why the query changes
