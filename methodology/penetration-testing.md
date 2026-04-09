# 🧠 Penetration Testing Methodology

## 📌 Overview
Penetration testing is a structured process used to identify, exploit, and report vulnerabilities in systems.

It is not random testing — it follows a **methodical approach**, where each phase builds on the previous one.

---

## 🎯 Objective
- Understand real-world pentesting workflow  
- Learn how attackers think step-by-step  
- Connect different security domains together  

---

# 🔍 Phase 1: Reconnaissance

## 📌 Goal
Gather as much information about the target as possible.

---

## 🧠 What to Look For
- domain names  
- IP addresses  
- subdomains  
- exposed services  
- technologies used  

---

## 🛠️ Common Techniques

```bash
whois example.com
nslookup example.com
theHarvester -d example.com -b google
```

---

## 🧠 Attacker Thinking
- What is exposed publicly?
- Can I map the infrastructure?
- Are there hidden subdomains?

---

# 📡 Phase 2: Scanning & Enumeration

## 📌 Goal
Identify live systems, open ports, and running services.

---

## 🛠️ Tools & Commands

```bash
nmap -sV target-ip
nmap -A target-ip
```

---

## 🧠 What to Identify
- open ports  
- service versions  
- possible vulnerabilities  

---

## 🧠 Attacker Thinking
- Which services can be exploited?
- Are there outdated versions?
- What entry points exist?

---

# 🧪 Phase 3: Vulnerability Identification

## 📌 Goal
Find weaknesses in the system.

---

## 🔍 Examples
- SQL Injection  
- XSS  
- weak authentication  
- misconfigurations  

---

## 🛠️ Tools

- Burp Suite  
- Nessus  
- manual testing  

---

## 🧠 Attacker Thinking
- Where does user input affect logic?
- Can I manipulate data flow?
- Is input validated properly?

---

# ⚔️ Phase 4: Exploitation

## 📌 Goal
Use identified vulnerabilities to gain access or extract data.

---

## 🧪 Examples

```sql
' OR 1=1 --
```

```html
<script>alert(1)</script>
```

---

## 🧠 Attacker Thinking
- Can I bypass authentication?
- Can I extract sensitive data?
- Can I execute code?

---

# 🔓 Phase 5: Post-Exploitation

## 📌 Goal
Maintain access and expand control.

---

## 🔍 Activities
- privilege escalation  
- data extraction  
- persistence  

---

## 🧠 Attacker Thinking
- Can I access more sensitive areas?
- Can I stay undetected?
- Can I escalate privileges?

---

# 📤 Phase 6: Reporting

## 📌 Goal
Document findings and recommend fixes.

---

## 📄 What to Include
- vulnerability description  
- impact assessment  
- proof of concept  
- remediation steps  

---

## 🧠 Why It Matters
- helps organizations fix issues  
- improves security posture  

---

# 🔄 Real-World Flow Summary

```
Recon → Scan → Identify → Exploit → Post-Exploit → Report
```

---

# 🧠 Common Mistakes

- skipping reconnaissance  
- relying only on automated tools  
- not understanding vulnerabilities  
- ignoring defense perspective  

---

# 🧾 Key Takeaways

- pentesting is systematic, not random  
- each phase builds on previous  
- understanding matters more than tools  

---

# ⚠️ Disclaimer

This methodology is for educational purposes only.  
Testing should be performed only in authorized environments.
