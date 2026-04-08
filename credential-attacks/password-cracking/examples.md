# 🧪 Practical Examples

## Example 1: Cracking MD5 Hash

Hash:
```
5f4dcc3b5aa765d61d8327deb882cf99
```

Using Hashcat:

```bash
hashcat -m 0 hash.txt rockyou.txt
```

Output:
```
password
```

---

## Example 2: Weak Password Scenario

Password:
```
admin123
```

Cracked using:
- dictionary attack
- common password lists

---

## 🧠 Lesson Learned
- Weak passwords are easily cracked
- Use strong + unique passwords
- Always use hashing + salting
