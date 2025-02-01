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

Now that IIS is enabled, from the installation files, download and install PHP Manager from IIS. Go through the install wizard and complete the install.

Next from the installation files, download and install the Rewrite Module. (rewrite_amd64_en-US.msi)

Then create a folder in the C drive called PHP.

From Installation Files, download PHP 7.3.8 (php-7.3.88-nts-Win32-VC15-x866.zip) and unzip the contents into C:\PHP

Once you have downloaded and extracted the zip file into the PHP on the C drive, download and install the VC_redist.x86.exe from the installation files. Go through the setup wizard to finish setting up and installing the VC_redist.x86.exe.

Download and install MySQL 5.5.62 (mysql-5.5.62-win32.msi) Run the setup wizard: Typical setup  -> launch -> Configuration Wizard (after install) -> Standard Configuration ->

Make the new root password: Password1

![image](https://github.com/user-attachments/assets/d32daaf1-bc83-488b-9b30-7da34def6aa2)

Execute the process on the next page.

![image](https://github.com/user-attachments/assets/2b199fb7-1471-4a16-bb87-40d3c5d9a46c)

Now that you have the files downloaded and installed, search for IIS in the Windows search bar. Open IIS as administrator.

![image](https://github.com/user-attachments/assets/3ef4011c-4d01-4599-b1a8-963b53979887)

Now register PHP from within IIS. Click on PHP Manager.

![image](https://github.com/user-attachments/assets/d6f0c01d-7d45-4553-8cad-68583e5f6848)

Register new PHP version.

![image](https://github.com/user-attachments/assets/5c20aa55-99e5-4564-a3f3-891290a620d3)

Provide a path to the php executable file (php-cgi.exe), Go to C drive -> PHP -> click on php-cgi file.

![image](https://github.com/user-attachments/assets/a63472ce-708d-4617-aa8a-b753f256ef1f)

Restart IIS server.

![image](https://github.com/user-attachments/assets/6117a1aa-79ae-4643-a844-74f1e43fdece)

Install osTicket v.1.15.8, download osTicket from the installation files folder, extract and copy the "upload" folder to c:\inetpub\wwwroot, within c:\inetpub\root, rename "upload" to "osTicket".

Reload IIS again.

On IIS go to sites -> Default -> osTicket -> on the right, click "Browse *:80"

![image](https://github.com/user-attachments/assets/47ac6587-a61a-41f3-a015-1ca01444f8dd)

Some extensions are not enabled on the osTicket browser.

![image](https://github.com/user-attachments/assets/19a80a56-40b5-4ddb-8b8c-bccb7d4e49fd)

To enable the extensions: Go back to IIS, sites -> Default -> osTicket, then double click PHP manager, then click "Enable or disable an extension"

![image](https://github.com/user-attachments/assets/84576135-4ae1-4be8-8271-847705700c9e)











</p>
<br />

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.
</p>
<br />
