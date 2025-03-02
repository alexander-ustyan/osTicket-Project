<p align="center">
<img src="https://i.imgur.com/Clzj7Xs.png" alt="osTicket logo"/>
</p>

<h1>osTicket - Prerequisites and Installation</h1>
This tutorial guides you through the prerequisites and step-by-step installation of osTicket, an open-source help desk ticketing system. It provides a hands-on approach to setting up and configuring osTicket for efficient support operations. By following this guide, you'll learn essential system installation, configuration, and IT support setup skills, demonstrating how to deploy a fully functional ticketing system in a cloud environment.<br />


<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Internet Information Services (IIS)

<h2>Operating Systems Used </h2>

- Windows 10</b> (21H2)

<h2>List of Prerequisites</h2>

- Microsoft Azure - Virtual Machine Setup
- osTicket System Configuration
- Install osTicket V1.15.8
  - Permission Assignments
  - Enable Key Extenstions

<h2>Installation Steps</h2>

<p>
<img src="(https://i.imgur.com/4VpzY8A.png)" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
In the Azure Portal, create a Windows 10 Pro virtual machine (osticket-vm) with 2 vCPUs. Set up user credentials (labuser / osTicketPassword1!), then deploy the VM. Once provisioned, find its public IP address under the Networking section. Use Remote Desktop (RDP) to connect by entering the public IP and logging in with the assigned credentials. Now, you're ready to configure the environment for osTicket installation.
</p>
<br />

<p>
<img src="https://i.imgur.com/k1QK8ia.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
On osticket-vm, prepare the environment for hosting osTicket by downloading and extracting the osTicket-Installation-Files.zip to the desktop. Install Internet Information Services (IIS) with CGI support, ensuring the required web server functionality. Enable World Wide Web Services → Application Development Features → [X] CGI to support osTicket’s deployment. Now, the system is ready for the next installation steps.
  
</p>
<img src="https://i.imgur.com/vzFpc4A.png"80%" width="80%" alt="Disk Sanitization Steps"/>  
</p>
<p>
From the osTicket-Installation-Files folder, install PHP Manager for IIS (PHPManagerForIIS_V1.5.0.msi) to simplify PHP configuration within Internet Information Services (IIS). Use this tool to manage PHP settings and ensure seamless integration with osTicket. Verify that the PHP environment is properly set up to support osTicket’s functionality, optimizing performance and compatibility.
</p>
<br />

<p>
<img src="https://i.imgur.com/VYTqWVC.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
From the osTicket-Installation-Files folder, install the IIS Rewrite Module (rewrite_amd64_en-US.msi) to enable URL rewriting and enhance web functionality. Configure the module within Internet Information Services (IIS) to support osTicket’s URL structure, improving accessibility and request routing. This ensures a seamless and optimized web application experience.
</p>
<br />

<p>
<img src="https://i.imgur.com/rSj3xj1.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<img src="https://i.imgur.com/k0rzmXx.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Create the C:\PHP directory as the installation path for PHP on osticket-vm. Extract PHP 7.3.8 (php-7.3.8-nts-Win32-VC15-x86.zip) from the osTicket-Installation-Files folder into C:\PHP to set up the PHP runtime environment. This configuration ensures compatibility with IIS and osTicket, enabling the web application to efficiently process PHP scripts.
</p>
<br />

<p>
<img src="https://i.imgur.com/OOtefEn.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Install VC_redist.x86.exe from the osTicket-Installation-Files folder to provide the necessary Microsoft Visual C++ runtime libraries for PHP and IIS. This ensures compatibility between the PHP environment and Windows Server, preventing runtime errors and enhancing system stability. Proper integration of the Visual C++ Redistributable is essential for the successful execution of osTicket on IIS.
</p>
<br />

<p>
<img src="https://i.imgur.com/9gNIoxl.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Install MySQL 5.5.62 (mysql-5.5.62-win32.msi) from the osTicket-Installation-Files folder using the Typical Setup option to provide database support for osTicket. After installation, launch the MySQL Configuration Wizard and select Standard Configuration to optimize database settings. Set up the root user credentials with Username: root and Password: root to ensure administrative access for database management.
</p>
<br />

<p>
<img src="https://i.imgur.com/HjtdWM3.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Open Internet Information Services (IIS) Manager as an administrator to set up the PHP environment for osTicket. Use PHP Manager to register PHP within IIS, setting the executable path to C:\PHP\php-cgi.exe for proper script processing. Apply the changes by restarting IIS (stop and start the server) to ensure seamless integration and functionality.
</p>
<br />

<p>
<img src="https://i.imgur.com/hhXzRB4.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Extract osTicket v1.15.8 (osTicket-v1.15.8.zip) from the osTicket-Installation-Files folder. Copy the upload folder into C:\inetpub\wwwroot, ensuring the web application is placed in the correct IIS directory. Rename the upload folder to osTicket within C:\inetpub\wwwroot to establish the application’s root directory.
</p>
<br />

<p>
<img src="https://i.imgur.com/U57GrB2.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<img src="https://i.imgur.com/h0oJwPC.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
In IIS Manager, navigate to Sites → Default → osTicket, then click “Browse :80” to check the osTicket installation. If required PHP extensions are missing, return to IIS Manager, open PHP Manager for osTicket, and enable the necessary extensions:

php_imap.dll
php_intl.dll
php_opcache.dll
After enabling these extensions, refresh the osTicket site in the browser to confirm the changes and ensure full functionality. This step ensures proper IIS configuration, PHP extension management, and web application troubleshooting.
</p>
<br />

<p>
<img src="https://i.imgur.com/FO0g48y.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Navigate to C:\inetpub\wwwroot\osTicket\include and rename ost-sampleconfig.php to ost-config.php. This step is crucial for osTicket to recognize and apply the correct settings during installation, ensuring proper system functionality.
</p>
<br />

<p>
<img src="https://i.imgur.com/OLpsDze.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
To enhance security and ensure proper functionality, navigate to C:\inetpub\wwwroot\osTicket\include, right-click ost-config.php, and select Properties → Security. Disable inheritance by removing all inherited permissions. Then, add a new permission entry granting Everyone full access to ost-config.php, allowing osTicket to modify the configuration as needed.
</p>
<br />

<p>
<img src="https://i.imgur.com/2ruGQE9.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
In the web browser, continue the osTicket installation by clicking "Continue", setting the Helpdesk Name, and configuring the default email for receiving customer inquiries.

Next, install HeidiSQL from the osTicket-Installation-Files folder to manage the MySQL database. Open HeidiSQL, create a new session using root/root credentials, and establish a connection. Then, create a new database named "osTicket", preparing the system for data storage and management.

This step finalizes the web application setup, database administration, and MySQL configuration for osTicket deployment.
</p>
<br />

<p>
<img src="https://i.imgur.com/6kkNncQ.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
In the web browser, finalize the osTicket setup by entering the MySQL database credentials:

Database Name: osTicket
Username: root
Password: root
Click “Install Now!” to complete the installation and establish a connection between osTicket and the MySQL database. This step finalizes the deployment, ensuring osTicket is fully integrated and ready for use.
</p>
<br />

<p>
<img src="https://i.imgur.com/kJJvDZ6.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Now osTicket is Successfully installed!
</p>
<br />

[Post-Install Configurations](https://github.com/alexander-ustyan/osTicket2-Lab)

<img src="https://i.imgur.com/UzfhvY5.png" height="80%" width="80%" alt="Done"/>
