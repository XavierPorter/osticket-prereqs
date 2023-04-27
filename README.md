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

<h1>1. Setup a Virtual Machine in Azure</h1>
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

<h1>2. Open: Installation Files</h1>

<p>
<img src="https://i.imgur.com/aKtK8rU.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
We will use these files to install osTicket and some of the dependencies
</p>
<br />

<h1>3. Install / Enable IIS in Windows WITH CGI</h1>

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
World Wide Web Services -> Application Development Features -> [X] CGI
</p>
<br />



<h1>4. Install / Enable IIS in Windows WITH CGI</h1>

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
World Wide Web Services -> Application Development Features -> [X] CGI
</p>
<br />
