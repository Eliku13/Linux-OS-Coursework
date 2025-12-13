Phase 6: Performance Evaluation and Analysis (Week 6)

A variety of workloads were evaluated in performance testing on the server operating system. Baseline measurements were captured while idle, and load testing was done on the CPU, memory, disk I/O, and network. We used monitoring tools to log resource use, find bottlenecks, and measure optimisation effectiveness.

Step 2 — Baseline performance testing (idle system)


<img width="446" height="44" alt="image" src="https://github.com/user-attachments/assets/a792924d-5af4-4181-bb35-99495edc9a50" />



<img width="317" height="91" alt="image" src="https://github.com/user-attachments/assets/99b859a8-e742-4941-b0c1-3f32e1bc28d3" />




<img width="371" height="28" alt="image" src="https://github.com/user-attachments/assets/8a79ecbc-9f08-405e-8be3-f6cd1743c5e7" />


Step 3 — CPU & Memory Load Testing

Install stress:
sudo apt install stress -y

CPU test:
stress --cpu 4 --timeout 60

Memory test:
stress --vm 2 --vm-bytes 512M --timeout 60


<img width="370" height="44" alt="image" src="https://github.com/user-attachments/assets/ef83f1f7-1427-49f0-9d5b-68bc3ca7c078" />


Monitor during test (in another SSH window):
free -h



<img width="440" height="59" alt="image" src="https://github.com/user-attachments/assets/ab1561cd-9255-4481-bb88-86d4f6b0a110" />



Step 4 — Disk I/O Testing

dd if=/dev/zero of=testfile bs=1G count=1 oflag=direct


<img width="371" height="78" alt="image" src="https://github.com/user-attachments/assets/26e53432-28f6-48c8-888a-6977a5130c86" />


Clean up:

rm testfile



Step 5 — Network Performance Testing

Install iperf3 on BOTH machines:
sudo apt install iperf3 -y



On server:
iperf3 -s


<img width="517" height="43" alt="image" src="https://github.com/user-attachments/assets/13ab9dd1-c68c-462b-98fa-5dd8e66aa87e" />

On workstation:
iperf3 -c 192.168.56.101



<img width="502" height="226" alt="image" src="https://github.com/user-attachments/assets/77d29a66-9466-429f-8f75-2f7e49cd938a" />


Step 6 — Service Response Time

Option A (Apache):
sudo apt install apache2 -y
time curl http:// localhost


<img width="357" height="102" alt="image" src="https://github.com/user-attachments/assets/79ebb71e-f036-4932-bc8a-497828c3cded" />



Step 7 — Performance Data Table (Deliverable 2)



<img width="497" height="210" alt="image" src="https://github.com/user-attachments/assets/ffa94e1d-0664-4daf-8016-e4368599cee6" />



Step 8 — Performance Visualisations (Deliverable 3)


Chart 1 — CPU Usage (Baseline vs Under Load)

Baseline CPU ≈ 31%

CPU under stress ≈ 100%

What this shows:
CPU-intensive workloads fully utilise processor resources and significantly increase load.

✅ Chart 2 — Memory Usage (Baseline vs Under Load)

Baseline memory used ≈ 2.4 GiB

Memory under stress ≈ 2.8 GiB

What this shows:
Memory-intensive workloads increase RAM usage but system remains stable (no swap).

✅ Chart 3 — Network Performance

Throughput ≈ 11.6 Gbps

What this shows:
High-performance host-only networking between VMs with minimal latency.






<img width="400" height="262" alt="image" src="https://github.com/user-attachments/assets/bb562f6f-11b9-44d0-b33f-b9955eac418c" />





<img width="370" height="252" alt="image" src="https://github.com/user-attachments/assets/5fbe8331-ca9b-4eb5-969b-650d43a8ad6e" />






<img width="398" height="251" alt="image" src="https://github.com/user-attachments/assets/38bb5f53-7852-40f4-8f7a-b71318741390" />




Baseline and load conditions for CPU, memory and network workloads were comared with performance visualisations. The load testing forced the CPU utilization high. But the memory consumption remained under control. There was no swapping. The workstation and server exhibited very high throughput, confirmed by the network testing.

Step 9 — Optimisation

Optimisation 2 — Stop unnecessary services
systemctl list-unit-files --type=service
sudo systemctl stop apache2




<img width="353" height="328" alt="image" src="https://github.com/user-attachments/assets/7a1925e8-6d98-440a-8583-12866fdb14ed" />



Step 10 — Optimisation Analysis

To enhance performance, we lowered memory swappiness and disabled unnecessary services. As a result of these changes, memory pressure was less and CPU usage was less under load. Quantitative results show improved system responsiveness and less resource contention.




-----------------------------------------------------------------------------------------------------------------------------





