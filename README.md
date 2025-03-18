<p align="center"> <img src="https://i.imgur.com/Clzj7Xs.png" alt="osTicket logo"/> </p> <h1>osTicket - Setup Guide and Requirements</h1> This guide walks you through the essential requirements and step-by-step installation of the open-source ticketing system, osTicket.<br /> <h2>Video Walkthrough</h2>
- ### [YouTube: How To Install osTicket with Prerequisites](https://www.youtube.com)
<h2>Tools and Platforms Used</h2>
Microsoft Azure (Virtual Machines/Compute)
Remote Desktop Protocol (RDP)
Internet Information Services (IIS)
<h2>Operating System</h2>
Windows 10</b> (21H2)
<h2>Required Components</h2>
Azure Virtual Machine
osTicket installation package
HeidiSQL
<h2>Installation Process</h2> <p> <img src="https://i.imgur.com/Iu8EC4s.png" height="80%" width="80%" alt="Step Image"/> </p> <p> Start by creating a resource group in Microsoft Azure and naming it osTicket. Inside this group, deploy a virtual machine using a Windows 10 Pro image with at least 2 vCPUs. This VM will serve as your test environment. </p> <br /> <p> <img src="https://i.imgur.com/H2B3g7x.png" height="80%" width="80%" alt="Step Image"/> </p> <p> Use Remote Desktop Protocol (RDP) to connect to your virtual machine. Retrieve the Public IPv4 address from the Azure portal and use it to establish the remote connection. </p> <br /> <p> <img src="https://i.imgur.com/2VqhhFo.png" height="80%" width="80%" alt="Step Image"/> </p> <p> Once connected, enable IIS by going to the Control Panel and selecting "Turn Windows features on or off." Locate and check the box for Internet Information Services (IIS) to activate it. </p> <br /> <p> <img src="https://i.imgur.com/jdy6kVT.jpeg" height="80%" width="80%" alt="Step Image"/> </p> <p> Download all necessary files from the provided link. Open the osTicket installation folder and install PHP Manager to proceed. </p> <br /> <p> <img src="https://i.imgur.com/BraQ2Sp.jpeg" height="80%" width="80%" alt="Step Image"/> </p> <p> Install the IIS Rewrite Module from the installation folder to continue setting up the environment. </p> <br /> <p> <img src="https://i.imgur.com/3G7QEou.jpeg" height="80%" width="80%" alt="Step Image"/> <img src="https://i.imgur.com/BJ7pQXn.jpeg" height="80%" width="80%" alt="Step Image"/> </p> <p> Create the directory C:\PHP. Extract the contents of PHP 7.3.8 (php-7.3.8-nts-Win32-VC15-x86.zip) into this folder. </p> <br /> <p> <img src="https://i.imgur.com/vnapOUJ.jpeg" height="80%" width="80%" alt="Step Image"/> </p> <p> Install VC_redist.x86.exe from the installation folder to ensure the necessary Visual C++ Redistributable components are available. </p> <br /> <p> <img src="https://i.imgur.com/6Ni4PkJ.png" height="80%" width="80%" alt="Step Image"/> </p> <p> Install MySQL 5.5.62 (mysql-5.5.62-win32.msi) to set up the database server required for osTicket. </p> <br /> <p> <img src="https://i.imgur.com/HFBKqHa.png" height="80%" width="80%" alt="Step Image"/> </p> <p> Open IIS Manager as an administrator and configure PHP settings. Restart the server after completing the setup. </p> <br /> <p> <img src="https://i.imgur.com/dUEDOI2.png" height="80%" width="80%" alt="Step Image"/> </p> <p> Extract osTicket-v1.15.8.zip from the installation folder. Copy the "upload" folder to C:\inetpub\wwwroot and rename it to "osTicket." </p> <br /> <p> <img src="https://i.imgur.com/ofoOo0Z.png" height="80%" width="80%" alt="Step Image"/> </p> <p> Restart the IIS server, then enable the required PHP extensions. Navigate to Sites -> Default -> osTicket, open PHP Manager, and enable php_intl.dll, php_opcache.dll, and php_imap.dll. Refresh the osTicket web server to verify the Intl Extension is enabled. </p> <br /> <p> <img src="https://i.imgur.com/JEdBG6b.png" height="80%" width="80%" alt="Step Image"/> </p> <p> Go to C:\inetpub\wwwroot\osTicket\include and rename ost-sampleconfig.php to ost-config.php. </p> <br /> <p> <img src="https://i.imgur.com/vFIs9DL.png" height="80%" width="80%" alt="Step Image"/> </p> <p> Right-click ost-config.php, go to Properties, then navigate to the Security tab. Disable inheritance, remove existing permissions, and grant full access to "Everyone." </p> <br /> <p> <img src="https://i.imgur.com/HZnNtf2.png" height="80%" width="80%" alt="Step Image"/> </p> <p> Launch the osTicket setup in your web browser and follow the installation prompts. Assign a name to your helpdesk and configure a default email for ticket notifications. Congratulations, your osTicket system is now ready! </p> <br />
