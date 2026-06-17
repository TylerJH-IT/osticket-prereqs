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
- Link to downloads: https://drive.google.com/drive/u/0/folders/1APMfNyfNzcxZC6EzdaNfdZsUwxWYChf6

<h2>Installation Steps</h2>

1.) First off you'll need to set up an Azure Resource Group and a Virtual Machine (VM). For this I'll be using Windows 10 Enterprise version 22H2 x64 Gen2.
</p>
<br />

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="100%" width="100%" alt="Disk Sanitization Steps"/>
</p>
<p>
<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="100%" width="100%" alt="Disk Sanitization Steps"/>
</p>
<p>
<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="100%" width="100%" alt="Disk Sanitization Steps"/>
</p>
<p>

2.) Once your Resource group and then your VM have been created you'll need to login to the VM.

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="100%" width="100%" alt="Disk Sanitization Steps"/>
</p>
<p>
<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="100%" width="100%" alt="Disk Sanitization Steps"/>
</p>
<p>
<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="100%" width="100%" alt="Disk Sanitization Steps"/>
</p>
<p>

3.) Now that your in the VM you'll want to open control panel, go to programs, turn Windows features on or off, and then enable Internet Information Services, Web Management Tools, World Wide Web Services.

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="100%" width="100%" alt="Disk Sanitization Steps"/>
</p>
<p>
<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="100%" width="100%" alt="Disk Sanitization Steps"/>
</p>
<p>
<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="100%" width="100%" alt="Disk Sanitization Steps"/>
</p>
<p>

4.) Next up open World Wide Web Services and enable Application Development Features, Common HTTP Features (Make sure everything within this is checked), Health and Diagnostics, Performance Features, and Security.

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="100%" width="100%" alt="Disk Sanitization Steps"/>
</p>
<p>
<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="100%" width="100%" alt="Disk Sanitization Steps"/>
</p>
<p>
<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="100%" width="100%" alt="Disk Sanitization Steps"/>
</p>
<p>

whatever.) And finally open up Application Development Features and turn on CGI. Now hit okay and wait for the changes to happen, if everything is installed and enabled correctly then if you go to your browser of choice and search for 127.0.0.1 it should open up to this page.

<p>
<img src="https://i.imgur.com/BDOAyNQ.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
<p>
<img src="https://i.imgur.com/jjtgm6V.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>

<p></p>

whatever.) Now that Internet Information Services, or IIS for short, is enabled we'll be downloading and installing everything we need from within the Google Drive. When you download the files from the google drive extract the contents into a folder.

<p>
<img src="https://i.imgur.com/G2AaKnO.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>

whatever.) First off you'll download and install PHP Manager for IIS and go through the install wizard.

<p>
<img src="https://i.imgur.com/Gcbhz5B.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>

whatever.) Now that we're done with that, next up we'll be installing the Rewrite Module and go through it's installation.

<p>
<img src="https://i.imgur.com/r1NBZKk.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>

whatever.) Now create a folder in the C drive called PHP and from the installation files extract PHP 7.3.8 and unzip it's contents into C:\PHP

<p>
<img src="https://i.imgur.com/KAMjQUy.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
<p>
<img src="https://i.imgur.com/6xMProl.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
<img src="https://i.imgur.com/CbthUQ8.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
<img src="https://i.imgur.com/Ca2VBpV.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
<img src="https://i.imgur.com/M3E46sw.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
<img src="https://i.imgur.com/XrrQp6J.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>

whatever.) Once you have extracted the zip file into the PHP folder on the C drive, download and install the VC_redist.x86.exe and go through the install wizard for it.

<p>
<img src="https://i.imgur.com/dJqUfUD.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>

whatever.) And finally download and install MySQL 5.5.62 and run the setup wizard. Select Typical Setup, Make sure the Launch the Configuartion Wizard is checked, then Standard Configuration.
  - As for the root password, just type in root. And finally click execute on it's all done.

<p>
<img src="https://i.imgur.com/AVpqb85.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
<p>
<img src="https://i.imgur.com/3hyNay0.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
<p>
<img src="https://i.imgur.com/vRBe7iv.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
<p>
<img src="https://i.imgur.com/DqMJ8Vs.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
<img src="https://i.imgur.com/zgk1o9w.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>

whatever.) Now that we have the files downloaded and installed we will want to search for IIS in the windows search bar and then open it AS AN ADMINISTRATOR.

<p>
<img src="https://i.imgur.com/BixG41H.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
<p>


whatever.) Next click on PHP Manager and register new PHP version. We'll want to provide a path to the php executable file to we'll be going to C drive, Php, and click on the php-cgi file.
  - Once that's done we'll restart the IIS server.

<p>
<img src="https://i.imgur.com/3Rh7fRK.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
<p>
<img src="https://i.imgur.com/uEhnZOo.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
<p>
<img src="https://i.imgur.com/6JK6ZKm.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
<p>
<img src="https://i.imgur.com/pW0zfPM.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>

whatever.) We'll now want to install osTicket v1.15.8, extract osTicket and copy the "upload' folder to C:\inetpub\wwwroot then from within this folder rename "upload" into "osTicket" and have it spelled that exact way.
  - Then we'll restart IIS again.

<p>
<img src="https://i.imgur.com/gaOMFQp.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
<p>
<img src="https://i.imgur.com/ftLZBFp.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
<p>
<img src="https://i.imgur.com/ORYXZQu.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
<p>
<img src="https://i.imgur.com/NQTXKnJ.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
<img src="https://i.imgur.com/PAxUTdb.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
<img src="https://i.imgur.com/N8fPIrA.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>

whatever.) On IIS go to sites, default Web Site, osTicket, on the right, click Browse :80. This will take you to the osTicket installer page.

<p>
<img src="https://i.imgur.com/G5QBgyR.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
<p>
<img src="https://i.imgur.com/voy7SXH.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
<p>
<img src="https://i.imgur.com/8ivbtuJ.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>

whatever.) Some extensions are not enabled on the osTicket Browser so to enable said extensions go back to IIS, sites, default, osTicket, click PHP manager then click Enable or disable an extension. We will want to enable three extensions from here. php_imap.dll, php_intl.dll, and php_opcache.dll

<p>
<img src="https://i.imgur.com/ED50oaB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
<p>
<img src="https://i.imgur.com/DW6dKPI.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
<p>
<img src="https://i.imgur.com/aXMWTT9.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p><p>
<img src="https://i.imgur.com/dXIbM2N.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p><p>
<img src="https://i.imgur.com/FtS8jBR.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p><p>

whatever.) Once we have the extensions enabled in IIS we are going to want to rename one of the files in our osTicket folder. Go into the file explorer and search for C:\inetpub\wwwroot]osTicket\include\ost-sampleconfig.php

<p>
<img src="https://i.imgur.com/vtuOigD.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>

whatever.) We are going to rename the ost-sampleconfig.php to ost-config.php

<p>
<img src="https://i.imgur.com/L5Dd4my.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>

whatever.) Now that we have renamed the files, right click on the file and go to properties. From there click security, click on advanced, and disable the inheritance. We will select Remove all inherited permissions from this object.

<p>
<img src="https://i.imgur.com/NOAI31d.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
<p>
<img src="https://i.imgur.com/nHcq7Q8.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
<p>
<img src="https://i.imgur.com/phc6qAK.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p><p>
<img src="https://i.imgur.com/KQHo1h9.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>

whatever.) Now we will add new permissions.
    - click add
    - select a principal
    - type "Everyone" in the box
    - Make sure full control and all the other boxes are check
    - click ok.

<p>
<img src="https://i.imgur.com/ywQrPvO.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
<p>
<img src="https://i.imgur.com/MozJ0jl.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
<p>
<img src="https://i.imgur.com/5IPpK25.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
<p>
<img src="https://i.imgur.com/c7ng2wL.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>

whatever.) Once that is done we will continue to setup osTicket in the browser. Click continue on the osTicket browser page. Fill out the page as required except the database settings at the bottom of the page.

<p>
<img src="https://i.imgur.com/tjvNFgd.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
<p>
<img src="https://i.imgur.com/OTjAirn.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>

whatever.) For now we will want to download and install HeidiSQL from the installation files. Click skip on the update page.
    - When the program is open we will create a new session in it.
    - We want to make sure the username is root and the password is root. Then click open.

<p>
<img src="https://i.imgur.com/wIdd0uT.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
<p>
<img src="https://i.imgur.com/YC8OcsH.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
<p>
<img src="https://i.imgur.com/4gaGa4Y.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>

whatever.) We will now create a new database within HeidiSQL. In Heidi right click on the left side where it says "Unnamed", select create new, and then select database. Name the new database osTicket.

<p>
<img src="https://i.imgur.com/jWzYcxD.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
<p>
<img src="https://i.imgur.com/AR9Lxqb.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
<p>
<img src="https://i.imgur.com/zx8THOx.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>

whatever. Once we are connected to the session we will go back to the browser to finish setting everything up. Under the Database settings in the browser the username will be "Root" and the password will be "root" with the database also being osTicket. And then finally click install now.

<p>
<img src="https://i.imgur.com/0VV6v7N.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
<p>
<img src="https://i.imgur.com/IZx0lKe.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>

Congratulations. You have now successfully installed osTicket.
