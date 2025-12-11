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



