Port 22 (SSH)

Nmap shows: OpenSSH 7.2p2 Ubuntu 4
![Scan](../Images/Port22nmap.png)
Confirmed with netcat.
![Scan](../Images/Port22netcat.png)

Findings:
CVE-2023-51385 - possible OS command injection in specific hostname/username expansion situations.
