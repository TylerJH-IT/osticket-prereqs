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

- Windows 10</b> (22H2)

<h2>List of Prerequisites</h2>

- Azure Virtual Machine
- Internet Information Services (IIS)
- PHP Manager
- Rewrite Module
- VC Redist
- MySQL
- Heidi SQL
- osTicket v1.15.8
- Link to downloads:
- PHP: https://www.php.net/downloads.php
- HeidiSQL: https://www.heidisql.com/installers/HeidiSQL_12.3.0.6589_Setup.exe
- MySQL: https://downloads.mysql.com/archives/community/  
- OsTicket: https://osticket.com/download/
- PHP Manager: https://www.iis.net/downloads/community/2018/05/php-manager-150-for-iis-10
- Rewrite AMD: https://www.iis.net/downloads/microsoft/url-rewrite
- VC-redist.x86 https://www.microsoft.com/en-us/download/details.aspx?id=48145 (BIG MAYBE REMOVE THIS TEXT LATER)

<h2>Installation Steps</h2>

<h3> 1.) First off you'll need to set up an Azure Resource Group. </h3>

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

<h3> 2.) Next you'll need a Virtual Machine (VM). For this I'll be using Windows 10 Enterprise version 22H2 x64 Gen2. <h3>

<h3>                                  </h3>

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

<h3> 3.) Now that your creating a Virtual Machine, you'll need to select these settings.</h3>

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

<h3>                                  </h3>

<h3> 4.) Once your Resource group and then your VM have been created you'll need to login to the VM. <h3>

<h3>                                  </h3>

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

<h2> Enabling features</h2>

<h3> 5.) Now that your in the VM you'll want to open control panel, go to programs, turn Windows features on or off, and then enable Internet Information Services, Web Management Tools, World Wide Web Services. <h3>

<h3>                                  </h3>

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

<h3> 6.) Next up open World Wide Web Services and enable Application Development Features, Common HTTP Features and make sure everything within this is checked. <h3>

<h3>                                  </h3>

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

<h3> 7.) Now check enable Health and Diagnostics, Performance Features, and Security. <h3>

<h3>                                  </h3>

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

<h3> 8.) And finally open up Application Development Features and turn on CGI. Now hit okay and wait for the changes to happen, if everything is installed and enabled correctly then if you go to your browser of choice and search for 127.0.0.1 it should open up to this page. <h3>

<h3>                                  </h3>

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="100%" width="100%" alt="Disk Sanitization Steps"/>
</p>
<p>
<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="100%" width="100%" alt="Disk Sanitization Steps"/>
</p>
<p>

<h2> Downloading and installing needed applications</h2>

<h3> 9.) Now that Internet Information Services, or IIS for short, is enabled we'll be downloading and installing everything we need for this. First off you'll want to download and install PHP Manager for IIS and go through the install wizard. <h3>

<h3>                                  </h3>

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

<h3> 10.) Now that we're done with that, next up we'll be installing the Rewrite Module and go through it's installation. <h3>

<h3>                                  </h3>

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

<h3> 11.) Now create a folder in the C drive called PHP and from the installation files extract PHP 7.3.8 and unzip it's contents into C:\PHP <h3>

<h3>                                  </h3>

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

<h3> 12.) Once you have extracted the zip file into the PHP folder on the C drive, download and install the VC_redist.x86.exe and go through the install wizard for it. <h3>

<h3>                                  </h3>

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="100%" width="100%" alt="Disk Sanitization Steps"/>
</p>
<p>
<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="100%" width="100%" alt="Disk Sanitization Steps"/>
</p>
<p>

<h3> 13.) And finally download and install MySQL 5.5.62 and run the setup wizard. <h3>

<h3>                                  </h3>

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

<h3> 14.) Select Typical Setup, Make sure the Launch the Configuartion Wizard is checked, then Standard Configuration. <h3>
<h3> - As for the root password, just type in root. And finally click execute on it's all done. <h3>

<h3>                                  </h3>

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

<h3> 15.) Now that we have the files downloaded and installed we will want to search for IIS in the windows search bar and then open it AS AN ADMINISTRATOR. <h3>

<h3>                                  </h3>

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="100%" width="100%" alt="Disk Sanitization Steps"/>
</p>
<p>
<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="100%" width="100%" alt="Disk Sanitization Steps"/>
</p>
<p>

<h3> 16.) Next click on PHP Manager and register new PHP version. We'll want to provide a path to the php executable file to we'll be going to C drive, Php, and click on the php-cgi file. <h3>
<h3>  - Once that's done we'll restart the IIS server. <h3>

<h3>                                  </h3>

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
<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="100%" width="100%" alt="Disk Sanitization Steps"/>
</p>
<p>

<h2> Setting up OsTicket</h2>

<h3> 17.) We'll now want to install osTicket v1.15.8. <h3>

<h3>                                  </h3>

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

<h3> 18.) Now extract osTicket and copy the "upload' folder to C:\inetpub\wwwroot then from within this folder rename "upload" into "osTicket" and have it spelled that exact way. <h3>
<h3>  - Then we'll restart IIS again. <h3>

<h3>                                  </h3>

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

<h3> 19.) On IIS go to sites, default Web Site, osTicket, on the right, click Browse :80. This will take you to the osTicket installer page. <h3>

<h3>                                  </h3>

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

<h3> 20.) Some extensions are not enabled on the osTicket Browser so to enable said extensions go back to IIS, sites, default, osTicket, click PHP manager. <h3>

<h3>                                  </h3>

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

<h3> 21.) Then click Enable or disable an extension. We will want to enable three extensions from here. php_imap.dll, php_intl.dll, and php_opcache.dll <h3>

<h3>                                  </h3>

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

<h3> 22.) Once we have the extensions enabled in IIS we are going to want to rename one of the files in our osTicket folder. Go into the file explorer and search for C:\inetpub\wwwroot]osTicket\include\ost-sampleconfig.php <h3>

<h3>                                  </h3>

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="100%" width="100%" alt="Disk Sanitization Steps"/>
</p>
<p>
<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="100%" width="100%" alt="Disk Sanitization Steps"/>
</p>
<p>

<h3> 23.) We are going to rename the ost-sampleconfig.php to ost-config.php <h3>

<h3>                                  </h3>

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="100%" width="100%" alt="Disk Sanitization Steps"/>
</p>
<p>
<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="100%" width="100%" alt="Disk Sanitization Steps"/>
</p>
<p>

<h3> 24.) Now that we have renamed the files, right click on the file and go to properties. <h3>

<h3>                                  </h3>

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

<h3> 25.) From there click security, click on advanced, and disable the inheritance. We will select Remove all inherited permissions from this object. <h3>

<h3>                                  </h3>

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

<h3> 26.) Now we will add new permissions. <h3>
<h3>    - click add <h3>
<h3>    - select a principal <h3>
<h3>    - type "Everyone" in the box <h3>
<h3>    - Make sure full control and all the other boxes are check <h3>
<h3>    - click ok. <h3>

<h3>                                  </h3>

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

<h3> 27.) Once that is done we will continue to setup osTicket in the browser. Click continue on the osTicket browser page. Fill out the page as required except the database settings at the bottom of the page. <h3>

<h3>                                  </h3>

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="100%" width="100%" alt="Disk Sanitization Steps"/>
</p>
<p>
<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="100%" width="100%" alt="Disk Sanitization Steps"/>
</p>
<p>

<h3> 28.) For now we will want to download and install HeidiSQL from the installation files. Click skip on the update page. <h3>
<h3>    - When the program is open we will create a new session in it. <h3>
<h3>    - We want to make sure the username is root and the password is root. Then click open. <h3>

<h3>                                  </h3>

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

<h3> 29.) We will now create a new database within HeidiSQL. In Heidi right click on the left side where it says "Unnamed", select create new, and then select database. Name the new database osTicket. <h3>

<h3>                                  </h3>

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

<h3> 30. Once we are connected to the session we will go back to the browser to finish setting everything up. Under the Database settings in the browser the username will be "Root" and the password will be "root" with the database also being osTicket. And then finally click install now. <h3>

<h3>                                  </h3>

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="100%" width="100%" alt="Disk Sanitization Steps"/>
</p>
<p>
<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="100%" width="100%" alt="Disk Sanitization Steps"/>
</p>
<p>

Congratulations. You have now successfully installed osTicket.
