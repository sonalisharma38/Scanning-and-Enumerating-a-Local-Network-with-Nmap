🔐 Ethical Hacking Project
Scanning and Enumerating a Local Network with Nmap
Table of Contents
Project: Simulating Real-World Network Exploitation and Defense



🎯 Project Objectives
To understand and apply techniques in:
Network scanning
Service enumeration
Vulnerability exploitation
Privilege escalation
Password cracking
Security remediation
🛠 Tools Used
Kali Linux (Attacker Machine)
Metasploitable (Target Machine)
Nmap 
Nmap (short for Network Mapper) is an open-source tool used for network discovery and security auditing.
John the Ripper
John the Ripper (often just called John) is a fast, open-source password cracker. It's primarily used for recovering weak or lost passwords by brute-force or dictionary-based attacks.
Metasploit Framework
The Metasploit Framework is one of the most powerful and widely used tools for penetration testing, vulnerability exploitation, and red teaming. It provides a modular platform to test and exploit known vulnerabilities in networks, systems, and applications.

🔍 Task 1: Basic Network Scan

Command:
nmap -v 192.168.190.0/24
Expected Output:
Nmap scan report for 192.168.190.129
Host is up (0.0010s latency).

Nmap scan report for 192.168.190.2
Host is up (0.0020s latency).

🧭 Task 2: Reconnaissance





















Command:
nmap -v 192.168.190.0/24
Expected Output:
Nmap scan report for 192.168.190.129
Host is up (0.0010s latency).

Total Hidden Ports: 7
 

2.1 Scanning for Hidden Ports
2.2 Service Version Detection
Command:
nmap -v -sV 192.168.129.0/24
Expected Output:



2.3 Operating System Detection





Command:
nmap -v -O 192.168.190.0/24

Expected Output:
MAC Address: 00:0C:29:8E:1A:27 (VMware)
Device type: general purpose
Running: Linux 2.6.X
OS CPE: cpe:/o:linux:linux\_kernel:2.6
OS details: Linux 2.6.9 - 2.6.33

📋 Task 3: Enumeration Summary
Target IP Address: 192.168.190.129
Operating System: Linux 2.6.9 - 2.6.33
MAC Address: : 00:0C:29:8E:1A:27 (VMware)
Device Type: General-purpose

Open Services (Excluding Hidden Ports)

Hidden Services
⚔️ Task 4: Exploitation of Services
 vsftpd 2.3.4: Exploited via known backdoor vulnerability.OpenSSH 4.7p1: Brute-force attack executed successfully.

Java RMI: Remote code execution achieved via Metasploit module.
👤 Task 5: Creating a Privileged User
Command:
adduser anushka
Password: hello

/etc/passwd Entry:

/etc/shadow Hash:
 anushka:$1$BYshHNAq$HeGhmInTHUfkEN/PiJbVb/

🔓 Task 6: Cracking Password Hash
Stored Hash in `anushka.txt`:
anushka:$1$BYshHNAq$HeGhmInTHUfkEN/PiJbVb/
Cracking Commands:
john anushka.txt
john anushka.txt --show
Cracked Password: hello

🛡️ Task 7: Remediation and Recommendations

Identified Vulnerabilities & Fixes:

1. vsftpd 2.3.4 – vulnerable backdoor
 Fix: Upgrade to vsftpd 3.0.5
2. OpenSSH 4.7p1 – outdated, brute-forceable
 Fix: Upgrade to OpenSSH 9.6
3. Java RMI Service – allows remote execution
 Fix: Disable or firewall restrict access
🎓 Major Learnings
- Applied Nmap for full-range scanning and OS detection.
- Understood enumeration and real-world exploitation techniques.
- Gained skills in privilege escalation and hash cracking.
- Learned how to evaluate vulnerabilities and apply proper remediation.

📘 This project simulates a real-world penetration test using open-source tools and is intended strictly for educational purposes.
