# FTP Brute Force Lab – Metasploitable

## Objective
Simulate an FTP brute force attack against a vulnerable machine and observe network traffic generated during the attack.

## Lab Environment
- Kali Linux VM
- Metasploitable VM
- VirtualBox
- Nmap
- Hydra
- Wireshark

## Steps Performed

### 1. Target Discovery
Identified Metasploitable IP address on host-only network.

### 2. Port Scanning
Used Nmap to enumerate open ports on the target.

Example:
nmap -sV 192.168.56.101

Findings:
Multiple open ports discovered including FTP.

### 3. FTP Brute Force
Used Hydra to attempt login against FTP service.

Example:
hydra -l msfadmin -P passwords.txt ftp://192.168.56.101

Observed active login attempts against FTP service.

### 4. Traffic Analysis
Captured attack traffic using Wireshark.

Filters used:
ftp
tcp.port == 21

Observed authentication traffic during brute force attempts.

## Screenshots
See screenshots folder.

## Security Lessons
- Weak passwords are dangerous
- FTP is insecure because credentials may be exposed
- Attack traffic can be monitored through packet analysis

## Next Improvements
- SSH brute force lab
- Web enumeration
- Privilege escalation
