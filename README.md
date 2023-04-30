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
<img src="" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
   <ol>
    <li>Double click PHP Manager</li>
    <li>Click "Register New PHP version"</li>
    <li></li>
  </ol>
</p>
<br />
