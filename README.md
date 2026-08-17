# 👋 Hi, I'm Rahat

<div align="center">

<img src="https://readme-typing-svg.herokuapp.com?color=00FF00&size=22&center=true&vCenter=true&width=800&lines=Full+Stack+Developer;Cyber+Security+Learner;DevOps+Engineer;Ethical+Hacking+Lab+Engineer"/>

</div>

---

# ⚠️ ETHICAL NOTICE

This project is ONLY for:
✔ Cyber Security Learning  
✔ SOC / Blue Team Training  
✔ Authorized Lab Testing (VM, Kali, Windows Sandbox)  

❌ No illegal access  
❌ No unauthorized scanning or hacking  

---

# 🧠 ABOUT ME

I build systems in:
- 🌐 Web & Mobile Apps  
- 🔐 Cyber Security (Defense + Lab Testing)  
- ☁️ Cloud & DevOps  
- 🤖 AI Automation  
- 🧩 System Architecture  

---

# 🌐 NETWORK RECON (ETHICAL LAB)

## 📌 Basic Network Info

```bash
ipconfig /all
```
👉 Bangla: আপনার device এর IP, DNS, MAC info দেখায়

```bash
ip a
```
👉 Linux: network interface info

---

## 📌 Connectivity Check

```bash
ping google.com
```
👉 Internet working কিনা test

```bash
traceroute google.com
```
👉 Data কোন route দিয়ে যাচ্ছে

---

## 📌 DNS Analysis

```bash
nslookup example.com
```
👉 Domain → IP convert

```bash
dig example.com
```
👉 Advanced DNS record analysis

---

# 🔎 PORT & SERVICE DISCOVERY (LAB ONLY)

```bash
nmap -sV 192.168.1.1
```

👉 Bangla:
- কোন port open
- কোন service running

📘 Example Use:
- Server auditing
- Network security check

---

```bash
ss -tulpn
```

👉 Bangla:
- কোন port কোন app use করছে

---

# 🖥️ SYSTEM ANALYSIS (FORENSIC STYLE)

```bash
tasklist
```
👉 Windows: running apps

```bash
ps aux
```
👉 Linux: running processes

```bash
netstat -ano
```
👉 Bangla:
- কোন app internet use করছে
- কোন port open

---

# 🔐 SECURITY ANALYSIS (BLUE TEAM)

## 📌 File Integrity Check

```bash
sha256sum file
```
👉 file change detect

```bash
certutil -hashfile file SHA256
```

---

## 📌 System Logs

```bash
Get-WinEvent -LogName Security
```
👉 Bangla:
- login history
- failed login detect

```bash
journalctl -xe
```

---

# 🧠 WEB SECURITY (EDUCATIONAL ONLY)

## 📌 Website Technology Scan

```bash
whatweb example.com
```

👉 Bangla:
- website কোন tech use করছে

---

## 📌 Header / Info Check

```bash
curl -I https://example.com
```

---

## 📌 WHOIS DOMAIN INFO

```bash
whois example.com
```

👉 Bangla:
- domain owner info
- registration details

---

# 🧪 SQL / WEB SECURITY (SAFE THEORY + LAB)

## 📌 SQL Injection Understanding (NOT EXPLOIT USE)

👉 Concept:
- User input যদি sanitize না হয় → database query manipulate হতে পারে

📘 Example (Educational):

```
' OR '1'='1
```

👉 Bangla:
- এটা authentication bypass concept বোঝায় (শেখার জন্য)

---

## 📌 Prevention (IMPORTANT)

✔ Use Prepared Statements  
✔ Input Validation  
✔ ORM (Laravel / Prisma / Sequelize)  
✔ WAF Protection  

---

# 🔐 ADVANCED CYBER SECURITY TOOLS (LEGAL LAB)

```bash
nmap -sS -sV target.com
```

👉 Bangla:
- stealth port scanning (lab only)

---

```bash
whatweb target.com
```

👉 website fingerprinting

---

```bash
nikto -h https://target.com
```

👉 vulnerability scanner (defensive audit)

---

# ☁️ HOSTING / DOMAIN (LEGAL MANAGEMENT)

## 📌 DNS Lookup

```bash
dig A example.com
```

---

## 📌 Subdomain discovery (defensive audit)

```bash
subfinder -d example.com
```

👉 Bangla:
- subdomain mapping for security audit

---
# 📶 WiFi Password (Legal & Educational Guide)

> ⚠️ শুধুমাত্র নিজের PC এবং নিজের WiFi network-এর জন্য ব্যবহারযোগ্য।

---

# 🧠 Overview

Windows system আগে যেসব WiFi network-এ connect হয়েছে, সেগুলো save করে রাখে।  
এই commands দিয়ে তুমি saved WiFi list এবং password (if available) দেখতে পারো।

---

# 🖥️ Steps 1–3 (Combined)

## 📌 Step 1: Saved WiFi Profiles দেখুন
```bash
netsh wlan show profiles
```

👉 এটি দেখাবে:
- তোমার PC-তে আগে connect করা সব WiFi নাম  
- saved wireless profiles list  

---

## 📌 Step 2: Specific WiFi select করুন
```bash
netsh wlan show profile name="WiFiName"
```

👉 এটি দেখাবে:
- ওই WiFi-এর full configuration  
- security type (WPA2/WPA3)  
- connection settings  

---

## 📌 Step 3: Saved Password দেখুন (নিজের network only)
```bash
netsh wlan show profile name="WiFiName" key=clear
```

👉 Output-এর মধ্যে খুঁজুন:
```text
Key Content : your_password_here
```

✔ এখানে saved WiFi password দেখা যাবে (if stored)

---

# 🧠 How it works

- Windows WiFi profile system credentials save করে রাখে  
- `key=clear` দিলে system decrypted form show করে  
- শুধুমাত্র আগে connected network-এ কাজ করে  

---

# ⚠️ Rules

❌ অন্যের WiFi access করা যাবে না  
❌ unauthorized network usage illegal  
✔ নিজের PC / own network only  

---

# 🚀 Use Cases

✔ Forgotten WiFi password recovery  
✔ IT troubleshooting  
✔ Device reconnect setup  
```

--

# 🧠 CYBER SECURITY LEARNING PATH

### Level 1:
✔ Networking basics  
✔ Linux commands  
✔ Windows CMD  

### Level 2:
✔ Nmap scanning  
✔ DNS analysis  
✔ Log reading  

### Level 3:
✔ Web security basics  
✔ SQL injection theory  
✔ Authentication security  

### Level 4:
✔ SOC monitoring  
✔ Incident response  
✔ Threat detection  

---

# 📊 GITHUB STATS

<div align="center">

<img src="https://github-readme-stats.vercel.app/api?username=YOUR_USERNAME&show_icons=true&theme=tokyonight"/>

<img src="https://github-readme-streak-stats.herokuapp.com/?user=YOUR_USERNAME&theme=tokyonight"/>

</div>

---

# 📡 CURRENT FOCUS

- Microservices Architecture  
- Cloud Security (AWS)  
- DevSecOps Pipeline  
- AI Integration  
- SOC Monitoring System  

---

# ⚠️ FINAL ETHICAL RULE

👉 সব command ব্যবহার হবে:
✔ Lab environment  
✔ Learning purpose  
✔ Authorized systems  

❌ Unauthorized access is illegal  

---

# ⚡ MOTTO

```
Learn Security. Build Systems. Protect Technology.
```

---

<div align="center">

⭐ If you like this repo, give a star

</div>

---

## Installation

### Prerequisites
- A modern web browser
- (Optional) [Visual Studio Code](https://code.visualstudio.com/) with the Live Server extension

### Steps
1. Clone the repository:
   ```bash
   git clone https://github.com/codexvisual/Hacking.git
   cd Hacking
   ```
2. Open the project folder.
3. Open `index.html` directly in your browser, or use **Live Server** in VS Code:
   ```bash
   npx live-server
   ```
