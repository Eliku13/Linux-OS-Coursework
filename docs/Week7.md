Phase 7: Security Audit and System Evaluation


Step 1 — Lynis Security Audit
Install Lynis:
sudo apt install lynis -y

Run scan:
sudo lynis audit system

Step 2 — Network Security (nmap)

From workstation:

nmap -sS 192.168.56.101





<img width="349" height="119" alt="image" src="https://github.com/user-attachments/assets/4a11def3-50a8-4768-97d7-22e3863d43da" />




Step 3 — SSH Security Verification




<img width="431" height="104" alt="image" src="https://github.com/user-attachments/assets/0c535631-6aad-49af-91e3-0b1d5e7d1e0a" />





Step 4 — Service Audit
systemctl --type=service --state=running

| Service  | Needed?  | Justification        |
| -------- | -------- | -------------------- |
| ssh      | Yes      | Remote admin         |
| fail2ban | Yes      | Intrusion prevention |
| apache2  | Optional | Testing only         |


Step 5 — Final Security Audit Report

We ran comprehensive security scans using Lynis and nmap on the subject. It assessed the system configuration as well as network exposure to attacks and access control. Security scores increased due to remediation conducted where SSH hardening, unnecessary service minimization, and firewall rule implementation were implemented. Remaining risks are documented with justification.
