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

