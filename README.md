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

- [Installation Files](https://drive.google.com/drive/u/1/folders/1APMfNyfNzcxZC6EzdaNfdZsUwxWYChf6)
- HeidiSQL
- IIS (Internet Information Services)
- PHP Manager for IIS
- Rewrite Module 
- PHP 7.3.8
- VC_redist.x86.exe
- MySQL 5.5.62

<h2>Installation Steps</h2>

<h2>1. Setup a Virtual Machine in Azure</h2>
<p>
<img src="https://i.imgur.com/2SWur0M.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
  <ol>
    <li>Create an Azure Virtual Machine Windows 10, 4 vCPUs</li>
    <li>Name: Vm-osticket</li>
    <li>Username: labuser (for example/whatever you chose)</li>
    <li>Password: osTicketPassword1! (for example/whatever you chose)</li>
</ol>
</p>
<br />

<h2>2. Open: Installation Files</h2>

<p>
<img src="https://i.imgur.com/aKtK8rU.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
We will use these files to install osTicket and some of the dependencies. <a href="https://drive.google.com/drive/u/0/folders/1APMfNyfNzcxZC6EzdaNfdZsUwxWYChf6">Installation Files</a></h1>
</p>
<br />

<h2>3. Install / Enable IIS in Windows WITH CGI</h2>

<p>
<img src="https://i.imgur.com/l3NRQpZ.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
  <ol>
    <li>Right click windows start menu and click run.</li>
    <li>Type in "control"</li>
    <li>Click "Programs"</li>
    <li>Click "Turn Windows features on/off"</li>
    <li>Check the "Internet Information Services" box</li>
    <li>World Wide Web Services-></li>
    <li>Application Development Features-></li>
    <li>Checke the "CGI" box</li>
  </ol>
</p>
<br />



<h2>4. Download and install PHP Manager for IIS.</h2>

<p>
<img src="https://i.imgur.com/SHLFJIB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
From the <a href="https://drive.google.com/drive/u/0/folders/1APMfNyfNzcxZC6EzdaNfdZsUwxWYChf6">Installation Files</a>, download and install PHP Manager for IIS (PHPManagerForIIS_V1.5.0.msi)
</p>
<br />


<h2>5. Download and install the Rewrite Module</h2>

<p>
<img src="https://i.imgur.com/wCTZBbb.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p> From the <a href="https://drive.google.com/drive/u/0/folders/1APMfNyfNzcxZC6EzdaNfdZsUwxWYChf6">Installation Files</a>, download and install the Rewrite Module </p>
<br />



<h2>6. Create the directory C:\PHP </h2>

<p>
<img src="https://i.imgur.com/oLo9qVi.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
  <ol>
    <li>Click File Explorer</li>
    <li>Type "C:" in the search bar.</li>  
    <li>Right click in the empty area and click "New"</li>  
    <li>Click "Folder" and name "PHP"</li>  
  </ol>
</p>
<br />


<h2>7. Download PHP 7.3.8 (php-7.3.8-nts-Win32-VC15-x86.zip) and unzip the contents into C:\PHP</h2>

<p>
<img src="https://i.imgur.com/h9YUZBz.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
  <ol>
    <li>Download PHP 7.3.8</li>
    <li>On the zip file, right click and click "extract all" </li>  
    <li>Click "Browse"</li>  
    <li>Click "This PC"</li>
    <li>Select the "C:" drive</li> 
    <li>Select the "PHP" folder</li>
    <li>Click Extract</li>
  </ol>
</p>
<br />


<h2>8. Download and install VC_redist.x86.exe</h2>

<p>
<img src="https://i.imgur.com/ItPlTGK.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
  <ol>
    <li>From the <a href="https://drive.google.com/drive/u/0/folders/1APMfNyfNzcxZC6EzdaNfdZsUwxWYChf6">Installation Files</a>, download and install VC_redist.x86.exe.</li>
  </ol>
</p>
<br />



<h2>9. Download and install MySQL 5.5.62 (mysql-5.5.62-win32.msi)</h2>

<p>
<img src="https://i.imgur.com/3sPWViF.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
  <ol>
    <li>From the <a href="https://drive.google.com/drive/u/0/folders/1APMfNyfNzcxZC6EzdaNfdZsUwxWYChf6">Installation Files</a>, download and install MySQL 5.5.62 (mysql-5.5.62-win32.msi)</li>
    <li>Typical Setup -></li>
    <li>Launch Configuration Wizard (after install) -></li>
    <li>Standard Configuration -></li>
    <li>Password1</li>
  </ol>
</p>
<br />



<h2>10. Open IIS as an Admin</h2>

<p>
<img src="https://i.imgur.com/IvHYvRf.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
  <ol>
    <li>Click the "Windows" Key</li>
    <li>Type in "IIS"</li>
    <li>Run as an administrator</li>
  </ol>
</p>
<br />



<h2>11. Register PHP from within IIS</h2>

<p>
<img src="https://i.imgur.com/AlcUwLt.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
   <ol>
    <li>Double click PHP Manager</li>
    <li>Click "Register New PHP version"</li>
    <li>Click "Browse Folder" or "..."</li>
    <li>Select "C:" drive</li>
    <li>Select "PHP"</li>
    <li>Select "PHP CGI"</li>
  </ol>
</p>
<br />


<h2>12. Reload IIS (Open IIS, Stop and Start the server)</h2>

<p>
<img src="https://i.imgur.com/FJf2Tov.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
   <ol>
    <li>Click on the name of the server (vmosticket)</li>
    <li>On the right hand side, click "Restart"</li>
  </ol>
</p>
<br />


<h2>13. Install osTicket v1.15.8</h2>

<p>
<img src="https://i.imgur.com/MiEW3Qm.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
   <ol>
    <li>Download osTicket from the Installation Files Folder</li>
    <li>Double click osTicket zip file</li>
    <li>In a seperate window for File Explorer, select "This PC" and select the "C:" folder</li>
    <li>Select the "inetpub" folder</li>
    <li>Select the "wwwroot" folder</li>
    <li>In the first file explorer window, drag the upload folder into the "wwwroot" folder</li>
    <li>Within c:\inetpub\wwwroot folder, Rename “upload” to “osTicket”</li>
    <li>Reload IIS (Open IIS, Stop and Start the server)</li>
  </ol>
</p>
<br />


<h2>14. Go to “Browse *:80”</h2>

<p>
<img src="https://i.imgur.com/oDQKPPr.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
  <ol>
    <li>In IIS, go to sites</li>
    <li>Select "Default"</li>
    <li>Select osTicket</li>
    <li>On the right, click “Browse *:80”</li>
  </ol>
</p>
<br />



<h2>15. Enable Extenstions</h2>

<p>
<img src="https://i.imgur.com/n0lzywH.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
  <ol>
    <li>Go back to IIS, sites -> Default -> osTicket</li>
    <li>Double-click PHP Manager</li>
    <li>Under "PHP Extenstions" Click “Enable or disable an extension”</li>
    <li>Enable: php_imap.dll</li>
    <li>Enable: php_intl.dll</li>
    <li>Enable: php_opcache.dll</li>
  </ol>
</p>
<br />


<h2>16. Rename: ost-config.php</h2>

<p>
<img src="https://i.imgur.com/vNQQ8hw.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
  <ol>
    <li>From: C:\inetpub\wwwroot\osTicket\include\ost-sampleconfig.php</li>
    <li>To: C:\inetpub\wwwroot\osTicket\include\ost-config.php</li>
  </ol>
</p>
<br />



<h2>17. Assign Permissions: ost-config.php</h2>

<p>
<img src="https://i.imgur.com/nU5GbUn.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
  <ol>
    <li>Right click "ost-config.php" and click properties</li>
    <li>Click the "Security" tab</li>
    <li>Click "Advanced"</li>
    <li>Click disable inheritance -> Remove All</li>
    <li>Add permisions -> select principals</li>
    <li>Enter the object name "everyone"</li>
    <li>Click check names and click "ok"</li>
    <li>Under "Basic Permissons", check "Full Control"</li>
  </ol>
</p>
<br />



<h2>18. Continue Setting up osticket in the browser (click Continue)</h2>

<p>
<img src="https://i.imgur.com/8ViDP8f.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
  <ol>
    <li>Name Helpdesk</li>
    <li>Default email (receives email from customers)</li>
  </ol>
</p>
<br />


<h2>19. HeidiSQL.</h2>

<p>
<img src="https://i.imgur.com/ZxG51uE.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
  <ol>
    <li>From the <a href="https://drive.google.com/drive/u/0/folders/1APMfNyfNzcxZC6EzdaNfdZsUwxWYChf6">Installation Files</a>, Download and install HeidiSQL.</li>
    <li>Open Heidi SQL</li>
    <li>Connect to the session</li>
    <li>Right Click "unamed"</li>
    <li>Click "create new" and click database</li>
    <li>Create a database called “osTicket”</li>
  </ol>
</p>
<br />


<h2>20. Continue Setting up osticket in the browser</h2>

<p>
<img src="https://i.imgur.com/JWW2Q7A.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
  <ol>
    <li>MySQL Database: osTicket</li>
    <li>MySQL Username: root</li>
    <li>MySQL Password: Password1</li>
    <li>Click “Install Now!”</li>
  </ol>
</p>
<br />



<h2>21. Clean up</h2>

<p>
<img src="https://i.imgur.com/T5WCyIh.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
  <ol>
    <li>Delete the setup folder: C:\inetpub\wwwroot\osTicket\setup</li>
    <li>Go to the ost-config.php folder: C:\inetpub\wwwroot\osTicket\include\ost-config.php</li>
    <li>Right the folder and select "properties"</li>
    <li>Select the "security" tab</li>
    <li>Click "Advanced"</li>
    <li>Click on "Everyone" and select "Edit"</li>
    <li>Under basic permissions, leave only "Read" and "Read and execute" checked</li>
  </ol>
</p>
<br />


<h2>Congratulations, hopefully it is installed with no errors!</h2>

<p>
<img src="https://i.imgur.com/8phnp5n.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
  <ol>
    <li>Browse to your help desk login page: http://localhost/osTicket/scp/login.php</li>
    <li>End Users osTicket URL:http://localhost/osTicket/</li>
  </ol>
</p>
<br />
