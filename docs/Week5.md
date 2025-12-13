Phase 5: Advanced Security and Monitoring
Infrastructure

1. Implement Access Control using SELinux or AppArmor, with documentation showing
how to track and report on access control settings

Step 1.1 — Check AppArmor status (via SSH)
sudo aa-status

Step 2.2 — Enable automatic updates


sudo aa-status | grep ssh
ls /etc/apparmor.d/

<img width="361" height="125" alt="image" src="https://github.com/user-attachments/assets/72de4542-d64a-4623-923b-3c75c2362ba6" />

The server was given mandatory access control with the use of AppArmor. By default, Ubuntu activates AppArmor feature which implements security profiles for applications to restrict their interaction with system. The aa-status command verified the status of AppArmor and enforced profiles confirming access control is enforced.

------------------------------------------------------------------------------------------------------------------------------

2. Configure automatic security updates with evidence of implementation

Enable automatic updates

<img width="414" height="17" alt="image" src="https://github.com/user-attachments/assets/59e4cacf-e6f9-456e-9e44-5991bea28c16" />

Step 2.3 — Verify configuration

<img width="310" height="35" alt="image" src="https://github.com/user-attachments/assets/0fce47a4-e457-417f-9be8-121edd6bce81" />

I enabled automatic security updates with unattended-upgrades. Having security update options automatically is better than manual install where security patching may be delayed.


------------------------------------------------------------------------------------------------------------------------------

3. Configure fail2ban for enhanced intrusion detection


Step 3.1 — Install fail2ban
Step 3.2 — Enable and start fail2ban

Step 3.3 — Check status

<img width="601" height="172" alt="image" src="https://github.com/user-attachments/assets/d45649ef-907f-4c62-a293-9801dc941c57" />


Step 3.4 — Verify SSH jail

<img width="361" height="116" alt="image" src="https://github.com/user-attachments/assets/972a7000-0d37-467a-bedd-89ddf33878ce" />

Monitoring SSH auth by configuring fail2ban was installed. It will restrict the access to IP addresses that seem suspicious such as failing to login repeatedly; this will prevent brute-force attacks too.



------------------------------------------------------------------------------------------------------------------------------

4. Create a security baseline verification script (`security-baseline.sh`) that runs on the
server (executed via SSH) and verifies all security configurations from Phases 4 and 5.

Step 4.1 — Create the script
#!/bin/bash

echo "=== Security Baseline Verification ==="

echo "[+] SSH Configuration"
grep -E "PasswordAuthentication no|PermitRootLogin no" /etc/ssh/sshd_config

echo "[+] Firewall Status"
ufw status

echo "[+] AppArmor Status"
aa-status

echo "[+] Automatic Updates"
grep Unattended /etc/apt/apt.conf.d/20auto-upgrades

echo "[+] fail2ban Status"
systemctl status fail2ban --no-pager


Step 4.2 — Make executable

<img width="406" height="150" alt="image" src="https://github.com/user-attachments/assets/7186f1b7-f027-44eb-8925-1b92aaf25832" />

To validate the key security configuration which were done in phases 4 and 5 a security baseline verification script is created. This script will check SSH hardening, firewall rules, AppArmor status, Automatic updates and fail2ban operation. The Baseline verification security script will provide a repeatable way to verify security.

------------------------------------------------------------------------------------------------------------------------------
5. Create a remote monitoring script (`monitor-server.sh`) that runs on your
workstation, connects via SSH, and collects performance metrics from the server

Step 5.1 — Create script on WORKSTATION
#!/bin/bash

SERVER="adminuser@192.168.56.101"

echo "=== Remote Server Monitoring ==="

ssh $SERVER << EOF
echo "Hostname:"
hostname

echo "Uptime:"
uptime

echo "CPU Load:"
top -bn1 | head -n 5

echo "Memory Usage:"
free -h

echo "Disk Usage:"
df -h
EOF

Step 5.2 — Make executable
chmod +x monitor-server.sh

Step 5.3 — Run the script

<img width="469" height="354" alt="image" src="https://github.com/user-attachments/assets/0d3e95ae-bced-496f-b020-661affb82851" />

A script for collecting performance metrics on the server through Remote SSH has been developed. This bash script can check the load of CPU, Memory, Disk use, and uptime. You can get the info without connecting to the server.










