<p align="center">
<img src="https://i.imgur.com/Clzj7Xs.png" alt="osTicket logo"/>
</p>

<h1>osTicket - Prerequisites and Installation</h1>
This tutorial outlines the prerequisites and installation of the open-source help desk ticketing system osTicket.<br />


<h2>Video Demonstration</h2>

- ### [YouTube: How To Install osTicket with Prerequisites](https://www.youtube.com)

<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Internet Information Services (IIS)

<h2>Operating Systems Used </h2>

- Windows 10</b> (21H2)

<h2>List of Prerequisites</h2>

- Create a Azure Virtual machine with windows 10 version 22H2 - x64 Gen2- Item 2
- Copy the public IP address from the Virtual machine made in Azure, open microsoft remote desktop create a PC with the public IP address
- Once microsoft remote desktop is open enter username and password then open a mirosoft edge browser install osTicket
- After the osTicket is installed you'll need to enable a few entensions, rename a file and assign permissions to everyone make sure to install heidiSQL from there finish the set up of osTicket in browser
- Congratulations, hopefully it is installed with no errors

<p>
<img width="1512" height="982" alt="Screenshot 2025-09-10 at 1 10 38 PM" src="https://github.com/user-attachments/assets/5448d481-9421-4cb9-8a46-b0e01b27e39d" />

Create an Azure Virtual Machine Windows 10, 4 vCPUs, and create your credentials. Log in to the VM with Remote Desktop

Download the osTicket Installation File .zip and unzip it onto your desktop.
Install / Enable IIS in Windows with CGI

From the osTicket Installation Files folder, install PHP Manager for IIS (PHPManagerForIIS_V1.5.0.msi)

Create the directory C:\PHP 
 
Folder osTicket Installation Files, unzip PHP 7.3.8 (php-7.3.8-nts-Win32-VC15-x86.zip) into the “C:\PHP” folder

Folder osTicket Installation Files, install VC_redist.x86.exe.

Folder osTicket Installation Files, install MySQL 5.5 62

Open IIS as an Admin

Register PHP from within IIS (PHP Manager -> C:\PHP\php-cgi.exe)

Reload IIS (Open IIS, Stop and Start the server)


<p>
<img width="1512" height="982" alt="Screenshot 2025-09-10 at 3 26 14 PM" src="https://github.com/user-attachments/assets/a5380f70-a935-449d-818f-bcf260db5afd" />
Install osTicket v1.15.8
- Folder osTicket Installation files, unzip “osTicket-v1.15.8.zip” and copy the “upload” folder into “c:\inetpub\wwwroot”
- Within “c:\inetpub\wwwroot”, rename upload to osTicket 

Reload IIS (Open IIS, Stop, and Start the server)

Note that some extensions are not enabled
- Go back to IIS, sites -> Default -> osTicket
- Double-click PHP Manager
- Click “Enable or disable an extension”
    * Enable: php_imap.dll
    * Enable: php_intl.dll
    * Enable: php_opcache.dll 

Rename: ost-config.php
- From: C:\inetpub\wwwroot\osTicket\include\ost-sampleconfig.php
- To: C:\inetpub\wwwroot\osTicket\include\ost-config.php

Assign Permissions: ost-config.php
- Disable inheritance -> Remove All
- New Permissions -> Everyone -> All

Continue setting up osTicket in the browser (click Continue)
- Name Helpdesk
- Default email (receives email from customers)

Folder osTicket Installation files install HeidiSQL 
- Open Heidi SQL
- Create a new session, root/root
- Connect to the session
- Create a database called “osTicket”

Continue setting up osTicket in the browser
- MySQL Database: osTicket
- MySQL Username: root
- MySQL Password: root
- Click “Install Now!”

<img width="1512" height="982" alt="Screenshot 2025-09-10 at 3 27 31 PM" src="https://github.com/user-attachments/assets/b7fd5fe5-ffd2-4faa-ab91-cb0dafddca9b" />

Congratulations, you should now have osTicket installed with minimal issues. Once you log in, you’ll have access to what osTicket has to offer  
