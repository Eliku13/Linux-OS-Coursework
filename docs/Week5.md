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


























