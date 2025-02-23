<p align="center">
  <img src="https://i.imgur.com/Clzj7Xs.png" alt="osTicket logo"/>
</p>

<h1>osTicket - Prerequisites and Installation</h1>
This project outlines the prerequisites and installation of the open-source help desk ticketing system osTicket.<br />

<h2>Video Demonstration (coming soon)</h2>

- ### [YouTube: How To Install osTicket with Prerequisites](https://www.youtube.com)

<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Internet Information Services (IIS)

<h2>Operating Systems Used</h2>

- Windows 10 (21H2)

<h2>List of Prerequisites</h2>

- Windows 10 (21H2) installed on an Azure VM
- Internet Information Services (IIS) installed and configured
- PHP installed with required extensions
- MySQL server installed and running
- Administrative privileges for configuration changes

<h2>Installation Steps</h2>

<p>
  <img src="https://i.imgur.com/bPrIomW.png" height="80%" width="80%" alt="Environment Setup"/>
</p>
<p>
  <strong>Step 1: Environment Setup and Prerequisite Installation</strong><br>
  Begin by ensuring your Azure virtual machine is running Windows 10 (21H2) with Remote Desktop enabled. Verify that Internet Information Services (IIS) is installed and properly configured. Install the required PHP version and adjust settings (such as file upload limits and execution time) as specified in the osTicket documentation. Finally, install MySQL to support the osTicket database.
</p>
<br />

<p>
  <img src="https://i.imgur.com/O7OBNLr.png" height="80%" width="80%" alt="osTicket Download" />
  <img src="https://i.imgur.com/yoSKlUp.png" height="80%" width="80%" alt="Inside the VM"/>
</p>
<p>
  <strong>Step 2: Downloading and Configuring osTicket</strong><br>
  Download the latest osTicket package from the official website or GitHub repository. Extract the package into your designated directory on the IIS server. Edit the configuration file (usually named <code>ost-config.php</code> or similar) to include your MySQL database credentials and adjust other settings as needed. Ensure that all file and folder permissions are set correctly to allow the web server to read and write where necessary.
</p>
<br />

<p>
  <img src="https://i.imgur.com/dwL4FNd.png" height="80%" width="80%" alt="Database Setup and Final Installation"/>
</p>
<p>
  <strong>Step 3: Database Setup and Final Installation</strong><br>
  Create a new MySQL database and dedicated user for osTicket. Import the osTicket SQL schema using phpMyAdmin or the MySQL command line. Next, open your browser and navigate to the osTicket installation URL to launch the web-based installer. Follow the on-screen instructions to finalize the installation. If you plan to integrate with Active Directory, configure the LDAP settings within osTicket after installation to enable seamless user authentication.
</p>
<br />
