Stapler VM Enumeration and Vulnerability Research
This documentation covers the initial discovery and enumeration phase for the Stapler boot-to-root machine.
Environment SetupThe target IP address is 192.168.197.139 and the attacker IP is 192.168.197.133.
Tools utilized during this phase include arp-scan, nmap, netcat, curl, and dig.
Port Discovery and Service Enumeration
Port,Service,Version,Findings and Potential Exploits
21,FTP,vsFTPd 3.0.3,Potential DoS (Exploit-DB 49719)
22,SSH,OpenSSH 7.2p2,Vulnerable to OS Command Injection (CVE-2023-51385)
53,DNS,dnsmasq 2.75,Heap Overflow and Info Leak (CVE-2017-14491)
80,HTTP,PHP CLI Server 5.5+,Development server with potential Invalid Memory Write exploit
3306,MySQL,5.7.12-0ubuntu1,Local Privilege Escalation via root system user
12380,HTTP,Apache 2.4.18,Vulnerable to Local Privilege Escalation (CVE-2024-38475)

Main Findings
Web Services
Port 80 runs a PHP server meant only for testing.
These servers are usually not safe for normal use. 
Port 12380 uses an old version of Apache that has known flaws. 
These flaws could let someone with low access take over the whole machine.

Database
The MySQL service on port 3306 was checked and found to be version 5.7.12.
This version is very old and is missing many safety updates.
It is a main target for becoming a system admin once a foot is in the door.

System Services
The DNS service on port 53 is an old version of dnsmasq.
It has serious bugs that could allow an attacker to see private memory or crash the service.
The FTP service on port 21 is also at risk of being shut down by an attacker.

Steps to Fix
The first step is to update Apache to version 2.4.65 or a newer release.
It is also important to update MySQL to a safe version and make sure it only allows connections from the machine itself.
The DNS service should be moved to version 2.91 to fix memory bugs.
The PHP test server on port 80 should be turned off if it is not needed for work.

Author: Imran Date: 14.11.2025
