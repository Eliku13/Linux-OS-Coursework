Assessment Week 3
Phase 3: Application Selection for Performance Testing
1.	

Workload Type	Application Selected	Description	Justification
CPU-Intensive	stress / stress-ng	Generates high CPU load for benchmarking.	Allows controlled CPU stress testing to measure system performance under load.
RAM-Intensive	stress-ng (memory test)	Allocates and stresses system RAM.	Helps observe memory pressure and how the VM handles low-memory scenarios.
I/O-Intensive	fio	Disk workload generator for read/write tests.	Provides realistic disk benchmarking and helps analyse I/O bottlenecks.
Network-Intensive	iperf3	Tool for bandwidth and throughput testing.	Allows testing VirtualBox network performance (NAT vs Host-Only).
Server Application	Apache Web Server	A lightweight HTTP server.	A real server application that lets you measure load handling and responsiveness.

Summary 
These applications were chosen due to them covering every main type of operating system workload. All of the tools are commonly used in Linux performance testing and normally work in virtual machines like Oracle VirtualBox. By using these apps, I can test how much CPU is used, how much pressure memory is facing, what is the disk I/O, network throughput and behaviour of the server.

------------------------------------------------------------------------------------------------------------------------------
2.	Installation Documentation with exact commands for SSH-based installation
ssh elijah@192.168.56.10 



sudo apt update





f


sudo apt install stress-ng -y



j








sudo apt install fio -y







sudo apt install iperf3 -y
 
sudo apt install apache2 -y
 
All performance testing applications were installed on the Ubuntu Server using an SSH connection from my workstation on a virtual machine. I connected to the server remotely and used apt commands to install the respective workloads for stress-ng, fio, iperf3, and the Apache web server. As you can see from the screenshots above, the commands and installation output were all as required using SSH.

------------------------------------------------------------------------------------------------------------------------------
3.	Expected Resource Profiles documenting anticipated resource usage
Different applications put different types of loads on the Ubuntu Server. It is anticipated CPU tests (stress-ng) will pull the processor up to high usage. Simultaneously, memory tests will use a lot of RAM. Fio will utilize most of the disk bandwidth and iperf3 will use most of the network bandwidth. Depending on the amount of the web requests, CPU, RAM, and network resources will be used by Apache. The expectations set the benchmark for performance testing in Week 6.
Application	Workload Type	Expected CPU Usage	Expected RAM Usage	Expected Disk I/O	Expected Network Usage	Reasoning
stress-ng (CPU test)	CPU-Intensive	Very High (80–100% on all cores)	Low	Very Low	None	Designed to max out CPU cores during stress tests.
stress-ng (memory test)	RAM-Intensive	Low–Moderate	Very High (based on memory allocated e.g., 1–2GB)	Very Low	None	Consumes large amounts of RAM to test memory pressure.
fio	I/O-Intensive	Low–Moderate	Low	Very High (frequent reads/writes)	None	Simulates heavy disk activity, stressing storage I/O.
iperf3	Network-Intensive	Low	Low	Very Low	Very High (bandwidth testing)	Measures bandwidth and throughput between systems.
Apache Web Server	Server Application	Moderate during load	Moderate	Low–Moderate	Moderate–High (HTTP traffic)	Handles multiple HTTP requests, using CPU, RAM, and network resources.

