Port 139 (NetBIOS-SSN / SMB)

Nmap suggests Samba 4.3.9-Ubuntu.
![Scan](../Images/Port139nmap.png)
Nmap script shows SMBv1 is in use, also obvious from port 139 + NetBIOS-SSN.

This is a potential attack vector.

Potential exploit:
https://www.exploit-db.com/exploits/42084

Samba module load RCE

Related to CVE-2017-7494 (critical).

Summary:

Date: 14.11.2025

Port: 139

Service: netbios-ssn (SMBv1)

Version: Samba 4.3.9-Ubuntu

Impact: Remote code execution

Recommendation: Upgrade to Samba 4.23.3

