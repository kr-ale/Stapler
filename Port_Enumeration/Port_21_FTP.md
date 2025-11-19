Port 21 (FTP)

Nmap suggests the service is vsFTPd 3.0.3.
![Scan](../Images/Port21nmap.png)
Tried verifying with netcat, but it didn’t reveal more information.
![Scan](../Images/Port21netcat.png)
Performed a deeper nmap scan, also not very helpful.
![Scan](../Images/Port21IndepthNmap.png)

Possible exploit:
https://www.exploit-db.com/exploits/49719 (DoS)

Summary:

Host: 192.168.197.139

Port: 21

Service: FTP

Version: vsFTPd 3.0.3

Exploit: Possible Denial of Service

