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

</p>
<br />

The first thing you want to do is go to https://portal.azure.com/ and create a virtual machine. When setting up your virtual machine use Windows 10 Pro, and select a VM with at least 2 vcpus and 8 GB memory.

Once your VM is created, connect to it by using the remote desktop connection app. When prompted input the VM's public IPv4 address.

</p>
<br />

![image](https://github.com/user-attachments/assets/e2daf46f-9faf-4912-b39e-658adfd1d8f3)

</p>
<br />

![image](https://github.com/user-attachments/assets/d8e6b8b1-7051-45a0-b451-eab41c1e2dbf)

</p>
<br />

Once you have loaded into your VM, go into control panel, then click -> programs, under "programs and features" select "Turn Windows features on or off". Then scroll down and check the box for "Internet Information Services". Then make sure to click the "+" sign beside "Internet Information Services", then click the "+" sign beside "World Wide Web Services", then click "+" sign beside "Application Development Features", then click the box for "CGI", then click ok. Your VM should make changes and tell you when it's done.

</p>
<br />

![image](https://github.com/user-attachments/assets/e5f9ad3d-045b-4cdd-9e0d-671902b17d95)

</p>
<br />

Now that IIS is enabled, from the installation files, download and install PHP Manager from IIS. Go through the install wizard and complete the install.

Next from the installation files, download and install the Rewrite Module. (rewrite_amd64_en-US.msi)

Then create a folder in the C drive called PHP.

From Installation Files, download PHP 7.3.8 (php-7.3.88-nts-Win32-VC15-x866.zip) and unzip the contents into C:\PHP

Once you have downloaded and extracted the zip file into the PHP on the C drive, download and install the VC_redist.x86.exe from the installation files. Go through the setup wizard to finish setting up and installing the VC_redist.x86.exe.

Download and install MySQL 5.5.62 (mysql-5.5.62-win32.msi) Run the setup wizard: Typical setup  -> launch -> Configuration Wizard (after install) -> Standard Configuration ->

Make the new root password: Password1

</p>
<br />

![image](https://github.com/user-attachments/assets/d32daaf1-bc83-488b-9b30-7da34def6aa2)

</p>
<br />

Execute the process on the next page.

</p>
<br />

![image](https://github.com/user-attachments/assets/2b199fb7-1471-4a16-bb87-40d3c5d9a46c)

</p>
<br />

Now that you have the files downloaded and installed, search for IIS in the Windows search bar. Open IIS as administrator.

</p>
<br />

![image](https://github.com/user-attachments/assets/3ef4011c-4d01-4599-b1a8-963b53979887)

</p>
<br />

Now register PHP from within IIS. Click on PHP Manager.

</p>
<br />

![image](https://github.com/user-attachments/assets/d6f0c01d-7d45-4553-8cad-68583e5f6848)

</p>
<br />

Register new PHP version.

</p>
<br />

![image](https://github.com/user-attachments/assets/5c20aa55-99e5-4564-a3f3-891290a620d3)

</p>
<br />

Provide a path to the php executable file (php-cgi.exe), Go to C drive -> PHP -> click on php-cgi file.

</p>
<br />

![image](https://github.com/user-attachments/assets/a63472ce-708d-4617-aa8a-b753f256ef1f)

</p>
<br />

Restart IIS server.

</p>
<br />

![image](https://github.com/user-attachments/assets/6117a1aa-79ae-4643-a844-74f1e43fdece)

</p>
<br />

Install osTicket v.1.15.8, download osTicket from the installation files folder, extract and copy the "upload" folder to c:\inetpub\wwwroot, within c:\inetpub\root, rename "upload" to "osTicket".

Reload IIS again.

On IIS go to sites -> Default -> osTicket -> on the right, click "Browse *:80"

</p>
<br />

![image](https://github.com/user-attachments/assets/47ac6587-a61a-41f3-a015-1ca01444f8dd)

</p>
<br />

Some extensions are not enabled on the osTicket browser.

</p>
<br />

![image](https://github.com/user-attachments/assets/19a80a56-40b5-4ddb-8b8c-bccb7d4e49fd)

</p>
<br />

To enable the extensions: Go back to IIS, sites -> Default -> osTicket, then double click PHP manager, then click "Enable or disable an extension"

</p>
<br />

![image](https://github.com/user-attachments/assets/84576135-4ae1-4be8-8271-847705700c9e)

</p>
<br />

![image](https://github.com/user-attachments/assets/236d4a48-59cf-4f0e-b7bc-c801da044c8a)

</p>
<br />

Enable three extensions:
1. php_imap.dll
2. php_intl.dll
3. php_opcache.dll

</p>
<br />

![image](https://github.com/user-attachments/assets/5c5f9da2-3426-42a4-8d37-fe9e67e9c687)

</p>
<br />

Once extensions are enabled in IIS, we need to rename one of the files in our osTicket folder. Go onto file explorer and search for 
C:\inetpub\wwwroot\osTicket\include\ost-sampleconfig.php

Rename the file from "ost-sampleconfig.php" to "ost-config.php"

Next, right-click on the file and go to properties. In properties, click security, then advance, and disable the inheritance. Then select remove all inherited permissions from this object.

Now we will add new permissions. 
Click add

</p>
<br />

![image](https://github.com/user-attachments/assets/42f5a317-7d87-4559-b4f5-4a4c64b1e97a)

</p>
<br />

select principle

</p>
<br />

![image](https://github.com/user-attachments/assets/9d46a3fc-dfce-4deb-9fec-0b630c2e4f34)

</p>
<br />

Type "Everyone" in the box

</p>
<br />

![image](https://github.com/user-attachments/assets/82fe5c7e-4382-4b22-bec4-e8aeabb4293f)

</p>
<br />

Ensure full control and all the other boxes are checked

</p>
<br />

![image](https://github.com/user-attachments/assets/4e6d6faa-8db4-4842-9009-8cd2fca27de6)

</p>
<br />

Click apply and OK

</p>
<br />

![image](https://github.com/user-attachments/assets/d11b7f4a-c7ae-4397-874a-c893eb52e1f4)

</p>
<br />

When that is done, you will continue to set up osTicket in the browser. Click continue on the osTicket browser page. Fill out the page as required except for the Database Settings at the bottom of the page.

Download and install HeidiSQL from the Installation files.

</p>
<br />

![image](https://github.com/user-attachments/assets/6b875011-cb0b-42f7-ab75-319e3d865c50)

</p>
<br />

When the program is open, click new in the bottom left.

</p>
<br />

![image](https://github.com/user-attachments/assets/38de9e60-38be-49b5-bf91-1d20162ef1d1)

</p>
<br />

Make sure to put the username as "root" and the password as "Password1"

</p>
<br />

![image](https://github.com/user-attachments/assets/cbb7ef25-2ca9-478a-b6d3-dac7150d6c8a)

</p>
<br />

Once you are connected to the session, you will go back to the browser to finish setting everything up. Under the Database settings in the browser, the username will be root and the password will be Password1

Now you will create a database within HeidiSQL. In Heidi, right-click on the left side where it says "Unnamed", select "Create new", and then select "Database". Name the new database "osTicket". When that is done go back to the osTicket browser and under MySQL Database type in "osTicket".

</p>
<br />

![image](https://github.com/user-attachments/assets/2afb7cc6-ad5f-44f8-8058-fc47dca5a24b)

</p>
<br />


<h2>The last step is optional</h2>

If you wish to do some cleanup, you would delete the setup folder in your system
Delete: C:\inetpub\wwwroot\osTicket\setup   **ONLY** delete the setup folder and nothing else. osTicket will still work if you do not delete this folder.

Then you will set the permissions back to "Read" only in the ost-config.php file.

</p>
<br />

![image](https://github.com/user-attachments/assets/ccd1a4e0-93fd-433d-a174-a5dcb429bb41)

</p>
<br />

![image](https://github.com/user-attachments/assets/ac22bde2-5c12-48cf-aa0e-4b1a602ea089)

</p>
<br />

When you see this screen you have successfully installed and set up osTicket.

</p>
<br />

![image](https://github.com/user-attachments/assets/04e2a312-dc0f-4e41-bd85-9ab32312b585)
