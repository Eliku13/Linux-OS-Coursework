Assessment Week 4
Phase 4: Initial System Configuration & Security
Implementation
Deploy your server and implement foundational security controls.
Deliverables (Journal and Video):

---------------------------------------------------------------------------------------------------------------------------------
1. Configure SSH with key-based authentication


step 1 Generate SSH Key - ssh-keygen -t ed25519 -C "elijah"

   <img width="364" height="256" alt="image" src="https://github.com/user-attachments/assets/7ca5afa8-ffe2-4e64-bf19-e2e025cca89e" />

step 2 Copy your public key to the server - ssh-copy-id elijah@192.168.56.101


<img width="403" height="136" alt="image" src="https://github.com/user-attachments/assets/c380bb6e-9bf0-4f42-b814-f8a3093c2875" />

STEP 3 — Test SSH Login Using Your Key (NO PASSWORD)


<img width="337" height="173" alt="image" src="https://github.com/user-attachments/assets/f7419f54-cc7f-42d7-a24d-9e158662f772" />


STEP 4 — Final SSH login test


<img width="349" height="164" alt="image" src="https://github.com/user-attachments/assets/e29024ab-6206-40b6-a8fd-def4ba043556" />

------------------------------------------------------------------------------------------------------------------------------

2. Configure a firewall permitting SSH from one specific workstation only
   Step 2.1 — Enable UFW on the server

   <img width="401" height="58" alt="image" src="https://github.com/user-attachments/assets/365d29ea-937b-4388-896d-4cbd30355a57" />

   Step 2.2 — Allow SSH from ONLY your workstation IP
   
   <img width="410" height="41" alt="image" src="https://github.com/user-attachments/assets/ca7f2196-51bd-47d4-ba0c-04386c4764cb" />

Step 2.3 — Deny all other SSH

Step 2.4 — Check the ruleset

<img width="347" height="107" alt="image" src="https://github.com/user-attachments/assets/66ab2d2c-c8ce-446c-95f7-ded951ea050b" />

----------------------------------------------------------------------------------------------------------------------------
3. Manage users and implement privilege management, creating a non-root
administrative user.

Step 3.1 — Create the user



<img width="399" height="241" alt="image" src="https://github.com/user-attachments/assets/d216f6d3-7ced-4fc6-8eb9-6734c1a68b46" />

Step 3.2 — Add the user to sudo group (admin rights)



<img width="400" height="263" alt="image" src="https://github.com/user-attachments/assets/c6426971-c69d-4704-9acd-9816e0fd68b9" />

------------------------------------------------------------------------------------------------------------------------------

4. SSH Access Evidence showing successful connection screenshots

   <img width="601" height="69" alt="image" src="https://github.com/user-attachments/assets/79a5f52c-d11d-45a7-9354-fe335b616098" />


<img width="602" height="269" alt="image" src="https://github.com/user-attachments/assets/0dec9abc-d222-4b9c-b4e2-3c2f7a49088e" />

Logging in as adminuser using password + key
✔️ Running commands through SSH (like top, ls, uname -a)


<img width="401" height="71" alt="image" src="https://github.com/user-attachments/assets/b0d31e8d-25f8-4e03-9953-87f4a6fa6579" />


SSH access was successfully established for the non-root administrative user (adminuser) using key-based authentication. The user was able to connect remotely via SSH and execute privileged commands using sudo, confirming correct privilege management and secure remote administration

-----------------------------------------------------------------------------------------------------------------------------
5. Configuration Files with before and after comparisons

   5.1 SSH Configuration (Before & After)
after :

   <img width="323" height="51" alt="image" src="https://github.com/user-attachments/assets/07467914-f81f-4315-9f50-c2d1f13d8463" />


The SSH configuration file changed to disallow password authentication and root login to enhance security by enforcing key-only access. Privilege management was configured by creating a non-root user and adding it to the sudo group. These configuration changes are evident from comparison before and after.

5.2 Privilege Management (Before & After)

BEFORE
adminuser not in sudo group

AFTER:

<img width="191" height="53" alt="image" src="https://github.com/user-attachments/assets/7b55416a-7252-4f58-bf39-f2f490120d99" />


A non-root user called adminuser was added to sudo group for added privilege management. To check the group membership we used the command getent group sudo which confirmed that we have the right administrative privileges and did not require root access directly.


-----------------------------------------------------------------------------------------------------------------------------

6. Firewall Documentation showing complete ruleset

<img width="335" height="110" alt="image" src="https://github.com/user-attachments/assets/a0c25da3-998f-41bb-a443-eb9c09e37110" />

I have set the Firewall (UFW) to allow SSH only from a trusted workstation IP. All remaining ssh connections are denied to reduce attack surface. The entire firewall ruleset verifies active functionality and proper enforcement of access control.

-----------------------------------------------------------------------------------------------------------------------------

7. Remote Administration Evidence demonstrating commands executed via SSH

Step 1 — SSH into the server as adminuser


Step 2 — Run administration commands


<img width="410" height="200" alt="image" src="https://github.com/user-attachments/assets/35374c70-2b14-4757-8f3e-ecbd6e938a92" />


The Workstation is using SSH to do remote administration of the Server. Commands like “uname -a” , “free -h” , “df -h” for system monitoring and service management were executed remotely without local console access indicating secure administration. This shows that everything is managed via SSH as required.

