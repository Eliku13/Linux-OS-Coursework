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
<img width="622" height="76" alt="image" src="https://github.com/user-attachments/assets/78d41ad9-bb98-4cd2-ab93-cecdc6c36df1" />

-----------------------------------------------------------------------------------------------------------------------------


sudo apt update

<img width="694" height="456" alt="image" src="https://github.com/user-attachments/assets/3ff09f75-9091-4413-adc8-b4edd9a1231f" />

------------------------------------------------------------------------------------------------------------------------------

f


sudo apt install stress-ng -y

<img width="864" height="535" alt="image" src="https://github.com/user-attachments/assets/c324d8d3-fecb-42a9-a18d-5ebf6a320737" />

----------------------------------------------------------------------------------------------------------------------------


j



sudo apt install fio -y



<img width="854" height="303" alt="image" src="https://github.com/user-attachments/assets/3f75674e-53b6-4211-8fd6-b6dc3ace3b73" />

----------------------------------------------------------------------------------------------------------------------------


sudo apt install iperf3 -y

<img width="851" height="260" alt="image" src="https://github.com/user-attachments/assets/f744a910-3c91-4948-81f2-c4483bbdaaa2" />

----------------------------------------------------------------------------------------------------------------------------- 
sudo apt install apache2 -y

<img width="834" height="310" alt="image" src="https://github.com/user-attachments/assets/466ed6c9-82f3-40a6-aecb-071b397c8d80" />

-----------------------------------------------------------------------------------------------------------------------------

 
All performance testing applications were installed on the Ubuntu Server using an SSH connection from my workstation on a virtual machine. I connected to the server remotely and used apt commands to install the respective workloads for stress-ng, fio, iperf3, and the Apache web server. As you can see from the screenshots above, the commands and installation output were all as required using SSH.

------------------------------------------------------------------------------------------------------------------------------
3.3.	Expected Resource Profiles documenting anticipated resource usage
Different applications put different types of loads on the Ubuntu Server. It is anticipated CPU tests (stress-ng) will pull the processor up to high usage. Simultaneously, memory tests will use a lot of RAM. Fio will utilize most of the disk bandwidth and iperf3 will use most of the network bandwidth. Depending on the amount of the web requests, CPU, RAM, and network resources will be used by Apache. The expectations set the benchmark for performance testing in Week 6.

<img width="401" height="245" alt="image" src="https://github.com/user-attachments/assets/a103d052-414a-4b3b-a410-66602c95737f" />
<img width="416" height="357" alt="image" src="https://github.com/user-attachments/assets/4d8c5e02-9910-493b-a23e-1d9ad6eec4ef" />

-----------------------------------------------------------------------------------------------------------------------------
4. Monitoring Strategy explaining measurement approach for each application

   📊 Monitoring Strategy by Application
1.For Real-Time CPU Monitoring, Use the top or htop to See CPU Usage.
 • Get the CPU percentage of each core during the test.
• Use the command vmstat 1 to check the system load averages. The CPU utilization, load average, and temperature will be measured (optional if tools installed).
________________________________________
2. Stress-ng memory test ram monitoring 7 words.
Method.
•	Make sure to run free -h both before and during the memory stress test.
•	Use top to view memory usage by stress-ng process.
Measured Metrics.
•	Complete RAM utilization.
•	Existing memory.
•	If there are any changes to swap usage.
________________________________________
3. Monitoring block device and I/O latency.
Approach.
•	iostat -x 1 provides disk read and write speeds and I/O wait.

•	Examine fio's internal performance metrics including IOPS, throughput, and latency.
•	Use df –h to collect baseline disk usage.
Metrics Evaluated.
•	Read/Write Speed
•	It measures performance quality per second.
•	Delay in disk and I/O operations.
________________________________________
4. iperf3 – A tool for monitoring network performance
Manner.
•	Use iperf3 in server mode in the Ubuntu Server and client mode in the workstation.
•	Iperf3 will directly show the results in bandwidth.
•	Use the 'iftop' command to see the flow through the network in real time (optional). 
System Characterization.

•	Speed of internet in megabits per second or gigabits per second.
•	Missing packets (if any).
•	Transfer Speed in Time.
________________________________________
5. Monitoring of mixed loads using the Apache web server.
Method.
•	Make requests with HTTP (e.g., use a browser or curl).
•	Use top to view Apache processes.
•	Utilize journalctl -u apache2 for service tracking logs.
•	Run vmstat 1 in order to view metrics.
Measured Metrics.
•	The consumption of CPU and RAM of Apache. 
•	"Active Links"
•	Time taken for response (manual testing with curl).
•	The data transmission while requesting

Summary:
By using an SSH connection, we will monitor each application with Linux CLI tools.  Processing tests exert load pressure on the CPU RAM usage is monitored by memory tests. I/O test records how well disk performs Bandwidth measurement is performed by generating load. Tests being run on the server to imitate a real-life service behaviour under load. The tool's purpose is to accurately evaluate how the Ubuntu server will respond to different kinds of workloads.
