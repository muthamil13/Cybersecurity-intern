# Nmap Scan Reports

This repository contains various **Nmap** scan outputs performed on different hosts and domains.  
The scans demonstrate the use of multiple Nmap options such as TCP SYN scan, TCP connect scan, UDP scan, OS detection, service version detection, and output saving.

---

## 📌 Scans Performed

### 1. Basic Version Check
```bash
nmap --version
Verified installed Nmap version: 7.98

Compiled with: openssl, libssh2, libz, libpcre2, Npcap, etc.

2. Host Discovery and Default Scan
bash
Copy code
nmap 192.168.1.1
Host was up

All 1000 ports were filtered

3. Domain Scan
bash
Copy code
nmap krct.ac.in
Host resolved to 207.174.215.2

Open ports: 21 (FTP), 22 (SSH), 26 (RSFTP), 53 (DNS), 80 (HTTP),
110 (POP3), 143 (IMAP), 443 (HTTPS), 465 (SMTPS), 587 (Submission),
993 (IMAPS), 995 (POP3S), 2222 (EtherNetIP-1), 3306 (MySQL)

4. TCP SYN Scan
bash
Copy code
nmap 207.174.215.2 -sS
Detected multiple open services (similar results as above)

5. TCP Connect Scan
bash
Copy code
nmap 207.174.215.2 -sT
Open ports included: 25, 26, 53, 110, 119, 143, 465, 563, 587, 993, 995, 2222

6. UDP Scan (Interrupted)
bash
Copy code
nmap 207.174.215.2 -sU
Scan was running but aborted due to long execution

7. Window Scan
bash
Copy code
nmap 207.174.215.2 -sW
Showed hundreds of open ports including common services (FTP, SSH, HTTP, HTTPS, DNS, MySQL) and rare ports

8. OS & Service Detection
bash
Copy code
nmap 207.174.215.2 -A
Services identified:

FTP: Pure-FTPd

SSH: OpenSSH 7.4

SMTP: Exim smtpd 4.98.1

DNS: ISC BIND 9.11.4-P2

HTTP(S): Apache httpd

POP3/IMAP: Dovecot

MySQL: 5.7.23-23

Host OS: Red Hat Enterprise Linux 7

Certificates showed *.webhostbox.net

9. Output Saved
bash
Copy code
nmap 207.174.215.2 -oN scan.file
Saved scan results in scan.file

⚡ Key Learnings
Different scan types (-sS, -sT, -sU, -sW, -A) reveal varying levels of information.

Filtered ports indicate firewall restrictions.

Service detection (-sV, -A) helps in identifying running software and versions.

Saving output (-oN) is useful for reporting and later analysis.

🚀 Usage
To replicate scans:

bash
Copy code
# Basic scan
nmap <target-ip>

# Service version detection
nmap -sV <target-ip>

# OS detection and full scan
nmap -A <target-ip>

# Save output to file
nmap -oN scan.file <target-ip>
⚠️ Disclaimer
These scans were performed for educational and testing purposes only.
Do not scan external systems without explicit permission as it may be considered illegal activity.

