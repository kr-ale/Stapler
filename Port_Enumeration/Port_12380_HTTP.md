Port 12380 (Unknown - HTTP)

Nmap identified an unknown port running Apache 2.4.18 (Ubuntu).
Confirmed with curl.

Vulnerabilities include:
CVE-2024-38475 - remote attacker could compromise the system.
Apache 2.4.17 < 2.4.38 exposes a privilege escalation via apache2ctl graceful + logrotate.

Summary:
Date: 14.11.2025
Port: 12380
Service: HTTP
Version: Apache 2.4.18
Impact: Local privilege escalation
Recommendation: Upgrade to Apache 2.4.65 or disable service until update
