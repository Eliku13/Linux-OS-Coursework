
Assessment Week 1
Phase 1: System Planning and Distribution Selection (Week 1)

1.	Create a System Architecture Diagram showing both systems and network connections
2.	<img width="653" height="863" alt="image" src="https://github.com/user-attachments/assets/3418241a-89c3-4861-aca4-116e4742b02a" />


-------------------------------------------------------------------------------------------------------------------------------
3.	Distribution Selection Justification comparing your chosen server distribution with alternatives.

For this course work I used the Oracle VirtualBox to run my Ubuntu Server. Ubuntu was used because it is stable , user- friendly and it work efficiently in virtual environments which I love about it. Its LTS (Long-Term Support) version provides five years of security and maintenance updates, making sure it is reliable throughout the project. It also uses the APT (Advanced Package Tool)  package manager, allowing software installation and updates simple, and has alit of community support with easy and understanding documentation that is ideal for learning and trouble shooting.

Compared to the others like CentOS Stream and Debian, Ubuntu offers a better balance between usability and stability, CentOS Stream is very business orientated and follows a rolling- release module, which can be very unpredictable with unpredictable updates, while Debian, although very stable, tents to use older software which then leads to needing more manual setup. Overall, Ubuntu Server was chosen for its strong support on the user, ease of configuration, and an excellent compatibility with Oracle VirtualBox, Making it the most suitable option for the coursework.

----------------------------------------------------------------------------------------------------------------------------
3. 	Workstation configuration decision justifying your choice of workstation option
For this project I used Oracle VirtualBox to run my Ubuntu Desktop Workstation. The VirtualBox was chosen because it is free so it is available for me to use ,its open source and it provides an efficient way to create and manage virtual machines for testing and configuration. It allows an easy assemble of network adapters, shared folders, and snapshots which are helpful for the course work and the system administration practice.
Ubuntu was selected because it is reliable and easy to use which the users would love and it also integrates smoothly with VirtualBox. Its nice graphical interface makes it simple to carry out tasks such as managing files, testing connections, and installing software. Ubuntu also supports VirtualBox Guest Additions, this enables different features like screening resizing, clipboard sharing, and drag-and-drop between systems. Despite other distributions such as Fedora Workstation or Debian Desktop were considered, Ubuntu Desktop was picked for its strong community support, frequent updates, and amazing compatibility with Oracle VirtualBox, leading it to be ideal for virtual learning and testing environment,
------------------------------------------------------------------------------------------------------------------------------
4.	Network configuration documentation covering VirtualBox settings and IP addressing
In Oracle VirtualBox, the Ubuntu virtual machine was configured with NAT(Network Address Translation) adapter.This setting allows the VM to access the internet through the host computers connection, eneabling system updates, software downloads, and remote package installations.the screen shot I will show under will show the configurations under the Netwok section , where Adapter 1 is listed in intel PRO/1000 MT Desktop(NAT). This validates that the virtual machine can communicate externally while remaining isolated from the host network. If additional virtual machines were used, a Host-Only Adapter could also be added to create a private internal network for server-to-workstation communication within VirtualBox.

------------------------------------------------------------------------------------------------------------------------------


5.	Using a CLI, document system specifications using `uname`, `free`, `df -h`, `ip addr`, and `lsb_release
uname -a
<img width="838" height="79" alt="image" src="https://github.com/user-attachments/assets/75bfe04f-f935-40fa-a71f-f38928f24a86" />
------------------------------------------------------------------------------------------------------------------------------

free -h

<img width="842" height="95" alt="image" src="https://github.com/user-attachments/assets/41beb7a2-6a30-4650-b268-26ee54c50297" />

------------------------------------------------------------------------------------------------------------------------------

df -h

<img width="830" height="178" alt="image" src="https://github.com/user-attachments/assets/cc4f69bf-4490-4c1e-a94a-ee19e71a20c3" />


------------------------------------------------------------------------------------------------------------------------------


lsb_release

<img width="783" height="254" alt="image" src="https://github.com/user-attachments/assets/894d941b-4ca2-4ab7-ab50-2ac2c7c49f2b" />

------------------------------------------------------------------------------------------------------------------------------
ip addr
<img width="931" height="442" alt="image" src="https://github.com/user-attachments/assets/22ccd2d0-f89a-4f86-9b4c-51b8b9be1509" />








ip addr



