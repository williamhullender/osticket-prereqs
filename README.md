<p align="center">
<img src="https://i.imgur.com/Clzj7Xs.png" alt="osTicket logo"/>
</p>

<h1>osTicket - Prerequisites and Installation</h1>
This tutorial outlines the prerequisites and installation of the open-source help desk ticketing system osTicket.<br />



<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Internet Information Services (IIS)

<h2>Operating Systems Used </h2>

- Windows 10</b> (21H2)

<h2>List of Prerequisites</h2>

- Azure Virtual Machine
- Internet Information Services (IIS)
- PHP Manager
- Rewrite Module
- VC Redist
- MySQL
- Heidi SQL
- osTicket v1.15.8
- https://drive.google.com/uc?export=download&id=1b3RBkXTLNGXbibeMuAynkfzdBC1NnqaD


<h2>Installation Steps</h2>

</p>
<br />

<p>

![image](https://github.com/user-attachments/assets/41a29d95-27d5-4a43-9ac1-47a201cec5b5)

The first thing you want to do is go to https://portal.azure.com/ and create a virtual machine. When setting up your virtual machine use Windows 10 Pro, and select a VM with at least 2 vcpus and 8 GB memory.

Once your VM is created, connect to it by using the remote desktop connection app. When prompted input the VM's public IPv4 address.
</p>
<br />

![image](https://github.com/user-attachments/assets/e2daf46f-9faf-4912-b39e-658adfd1d8f3)

![image](https://github.com/user-attachments/assets/d8e6b8b1-7051-45a0-b451-eab41c1e2dbf)


Once you have loaded into your VM, go into control panel, then click -> programs, under "programs and features" select "Turn Windows features on or off". Then scroll down and check the box for "Internet Information Services". Then make sure to click the "+" sign beside "Internet Information Services", then click the "+" sign beside "World Wide Web Services", then click "+" sign beside "Application Development Features", then click the box for "CGI", then click ok. Your VM should make changes and tell you when it's done.

![image](https://github.com/user-attachments/assets/e5f9ad3d-045b-4cdd-9e0d-671902b17d95)



</p>
<br />

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.
</p>
<br />
