
 Assessment week 2
Phase 2: Security Planning and Testing Methodology (Week 2)

1.	Create a performance testing plan describing your remote monitoring methodology and testing approach
The Ubuntu server is running on Oracle VirtualBox for this project. The performance testing will be done by a local and remote monitor. I will log into the VirtualBox-virtualized Ubuntu VM from a separate workstation VM via SSH. This lets me see system performance as commands and tasks all run on the server at the same time To create a performance testing, I will execute commands to check the performance of the VM when it is idle (not having any workloads) with top, free -h, and df -h (CPU usage, available memory, and disk space respectively). I will also use ping to check the network responsiveness between workstation vm and the server vm. Once the baseline is established, I will stress the system by installing packages or running updates to see if there is any changes via SSH. The strategy enables me to monitor the desktop performance level of Ubuntu VM on Oracle VirtualBox and keep the server responsive during regular and remote monitoring.
------------------------------------------------------------------------------------------------------------------------------
2.	Security Configuration Checklist for SSH hardening, firewall configuration, MAC, auto update, user privilege, and network security.
In the SSH server configuration, root login is disabled. Used keys for authentication in place of passwords. Changed SSH port from 22 to a custom port (Optional). I restarted the SSH service to apply changes (sudo systemctl restart sshd).

To enable the firewall, use the command: sudo ufw enable. Did you make sure to allow only the ports required (eg. SSH and web service if needed Allow SSH on UFW firewall – sudo ufw allow 22. Deny all other incoming connections by default I checked the rules using sudo ufw status.

✓ Mandatory Access Control (MAC) – AppArmor Check AppArmor is active on Ubuntu (sudo aa-status). I made sure that the important components SSH and system applications were in enforce mode.  AppArmor profiles modified through system updates.

Automatic Updates . Installed and enabled unattended upgrades: sudo apt install unattended-upgrades sudo dpkg-reconfigure unattended-upgrades Ensured security updates are applied to your server automatically in the background.

User access control to restrict this important feature. Used ‘sudo’ for admin commands. Users only have the minimum rights they require. I checked the sudoers file for escalations. 

I disabled all the services which are not in use.  It helped me to reduce attack surface significantly.   I also made use of sudo netstat -tuln or ss -tuln to check for open ports.  Finally, limited VirtualBox adapters to only essential network traffic.  I enabled the firewall logging to catch any suspicious traffic. 

------------------------------------------------------------------------------------------------------------------------------
3.	Threat Model identifying at least 3 specific security threats with mitigation strategies

Threat 1: Unauthorized SSH Access (Brute-Force Attacks)
Description.
-	Attackers may try guessing usernames and passwords by repeatedly logging in via SSH.
Mitigation Strategy.
-	Disable remote root login
-	Use SSH key-based authentication.
-	Optionally change SSH port.
-	Limit SSH access using UFW firewall.

Threat 2: Exploitation Through Outdated Software
Description.
-	Unpatched software can have vulnerabilities that can be exploited.
Mitigation Strategy.
-	Enable automatic security updates.
-	Regularly run sudo apt update && sudo apt upgrade.
-	Keep AppArmor profiles updated.

Threat 3: Privilege Escalation by Local Users
Description.
-	Regular user may try to obtain unauthorized admin access.
Mitigation Strategy.
-	Follow least-privilege principles in sudo.
-	Disable root login.
-	Review /etc/sudoers regularly.
-	Use strong passwords.

Threat 4 (Optional): Denial of Service (DoS)
Description:
High traffic or excessive processes can overload the VM.
Mitigation Strategy:
-	Use UFW connection limits
-	Disable unused services
-	Monitor system load during use
Summary. 
This threat model shows how a virtual Ubuntu server could be attacked through SSH, by outdated software or privilege misuse, and how to secure it.

