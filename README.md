# Hacking# 🛡️ Cybersecurity & System Administration Full Command Wiki

## 📌 Educational Defensive Guide (Windows • Linux • PowerShell • Networking)

---

# 🖥️ WINDOWS CMD FULL COMMAND SET

## 🔹 System Info
hostname → PC নাম দেখায়  
ver → Windows version  
systeminfo → full system details  
whoami → current user  
whoami /all → permission details  

---

## 🔹 Network (Full)
ipconfig → IP দেখায়  
ipconfig /all → full network info  
ipconfig /flushdns → DNS cache clear  
ipconfig /release → IP release  
ipconfig /renew → new IP নেয়  
getmac → MAC address  
arp -a → connected devices  
route print → routing table  

---

## 🔹 Network Testing
ping google.com → connection test  
tracert google.com → path tracking  
pathping google.com → delay analysis  
nslookup google.com → DNS lookup  

---

## 🔹 Active Network
netstat → connections  
netstat -ano → process with port  
netstat -r → route info  

---

## 🔹 User System
net user → users list  
net localgroup → groups  
net accounts → password policy  

---

## 🔹 Process Control
tasklist → running apps  
taskkill /IM app.exe /F → force close  
taskkill /PID 1234 /F → process kill  

---

## 🔹 File System
dir → file list  
cd → folder change  
mkdir → folder create  
rmdir → folder delete  
copy → copy file  
move → move file  
del → delete file  
rename → rename file  
tree → folder structure  

---

## 🔹 System Tools
chkdsk → disk check  
sfc /scannow → system repair  
diskpart → disk management  
driverquery → drivers list  
gpresult /r → policy info  

---

## 🔹 Logs
eventvwr → event viewer  
wevtutil qe System → system logs  

---

# ⚡ POWERSHELL FULL COMMAND SET

Get-ComputerInfo → system info  
Get-Date → time/date  
Get-Process → running apps  
Get-Service → services  
Stop-Process → stop app  
Restart-Service → restart service  

Get-NetIPAddress → IP  
Get-NetAdapter → network card  
Get-NetTCPConnection → active connections  
Get-NetRoute → routing  

Get-LocalUser → users  
Get-LocalGroup → groups  

Get-WinEvent → logs  
Get-EventLog → old logs  

Get-HotFix → updates  

Get-FileHash file → file integrity check  

---

# 🐧 LINUX FULL COMMAND SET

## 🔹 System
uname -a → OS info  
hostname → system name  
uptime → system running time  
whoami → current user  
id → user details  

---

## 🔹 File System
ls → file list  
pwd → current directory  
cd → change folder  
mkdir → create folder  
rmdir → delete folder  
cp → copy file  
mv → move file  
rm → delete file  
touch → create file  

---

## 🔹 File Content
cat → full file  
less → scroll file  
more → page view  
head → top lines  
tail → last lines  
grep → search text  

---

## 🔹 Process
ps → process list  
top → live monitoring  
htop → advanced monitor  
kill → stop process  
pkill → kill by name  

---

## 🔹 Network
ping → test  
ip a → IP info  
ip r → routing  
ss -tulpn → ports & services  

---

## 🔹 Logs
journalctl → system logs  
dmesg → kernel logs  

---

# 🌐 NETWORKING FULL COMMANDS

ping → connectivity  
nslookup → DNS  
dig → advanced DNS  
host → hostname lookup  

traceroute → path tracking  
tracert → Windows path  

netstat → connections  
ss → socket status  

arp -a → device list  
route print → routing table  

---

# 🔒 SECURITY ADMIN (DEFENSIVE)

netsh advfirewall show allprofiles → firewall  
gpresult /r → policy  
wevtutil qe System → logs  
eventvwr → GUI logs  
driverquery → drivers  

cipher /w:C:\ → delete space wipe  

---

# 🧪 INCIDENT RESPONSE

tasklist → process check  
netstat -ano → suspicious port  
systeminfo → system info  

ps aux → linux processes  
ss -tulpn → open ports  
last → login history  
lastlog → login log  

---

# 💾 DISK MANAGEMENT

chkdsk → disk error check  
diskpart → disk control  
wmic logicaldisk → disk info  

lsblk → linux disk  
fdisk -l → partition  
blkid → disk ID  

---

# 👥 USER AUDIT

net user → users  
net localgroup administrators → admin users  

cat /etc/passwd → linux users  
cat /etc/shadow → password info (admin only)  

---

# 🧠 FILE FORENSICS

Get-FileHash file → hash check  
sha256sum file → linux hash  
md5sum file → md5 hash  
diff file1 file2 → compare  

---

# 🛡️ BEST PRACTICES

✔ VM ব্যবহার করো  
✔ firewall ON রাখো  
✔ update নিয়মিত করো  
✔ strong password ব্যবহার করো  
✔ logs monitor করো  
✔ MFA ব্যবহার করো  

❌ unauthorized access না  
❌ malware না  
❌ hacking tools misuse না  

---

# 🚀 LEARNING PATH

1. Computer Basics  
2. Networking  
3. Windows Admin  
4. Linux Admin  
5. Security Basics  
6. Log Analysis  
7. Incident Response  
8. SOC Skills  
9. Cloud Security  
10. Ethical Hacking (Defensive only)  

---

# 📌 END
This is a complete defensive cybersecurity command reference.
