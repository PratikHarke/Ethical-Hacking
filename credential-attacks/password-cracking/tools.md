# 🛠️ Password Cracking Tools

## 🔥 Hashcat

Example command:

```bash
hashcat -m 0 hash.txt wordlist.txt
```

### Explanation
- `-m 0` → MD5 hash
- `hash.txt` → file containing hashes
- `wordlist.txt` → password list

---

## 🔥 John the Ripper

```bash
john hash.txt
```

---

## 🔥 Hydra (Online Attack)

```bash
hydra -l admin -P passwords.txt ssh://target-ip
```

---

## ⚠️ Notes
- Always use tools in legal environments
- Requires permission to test systems
