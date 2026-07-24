<p align="center">
<img src="https://i.imgur.com/Clzj7Xs.png" alt="osTicket logo"/>
</p>

<h1>osTicket - Prerequisites and Installation</h1>
This tutorial outlines the prerequisites and installation of the open-source help desk ticketing system osTicket for users on Windows.<br />

<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Internet Information Services (IIS)
- A computer running Windows

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
- osTicket 1.15.8
- Link to downloads:
- PHP: https://downloads.php.net/~windows/releases/archives/
- HeidiSQL: https://www.heidisql.com/download.php
- MySQL: https://downloads.mysql.com/archives/community/  
- OsTicket: https://github.com/osTicket/osTicket/releases/tag/v1.15.8
- PHP Manager: https://github.com/RonaldCarter/PHPManager
- Rewrite AMD: https://www.iis.net/downloads/microsoft/url-rewrite
- VC-redist: https://www.microsoft.com/en-us/download/details.aspx?id=48145 (BIG MAYBE REMOVE THIS TEXT LATER)

<h2>Installation Steps</h2>

<h3> 1.) First off you'll need to set up an Azure Resource Group. </h3>

<p>
<img src="https://i.imgur.com/5SvbcoP.png" height="100%" width="100%" alt="Disk Sanitization Steps"/>
</p>
<p>
<p>
<img src="https://i.imgur.com/EaOGVdH.png" height="100%" width="100%" alt="Disk Sanitization Steps"/>
</p>
<p>
<p>
<img src="https://i.imgur.com/3QNGFDN.png" height="100%" width="100%" alt="Disk Sanitization Steps"/>
</p>
<p>

<h3> 2.) Next you'll need a Virtual Machine (VM). For this I'll be using Windows 10 Enterprise version 22H2 x64 Gen2. <h3>

  - Clicking create will open a menu, click on Virtual Machine.

<h3>                                  </h3>

<p>
<img src="https://i.imgur.com/Ft2S7ru.png" height="100%" width="100%" alt="Disk Sanitization Steps"/>
</p>
<p>
<p>
<img src="https://i.imgur.com/1iXwm4r.png" height="100%" width="100%" alt="Disk Sanitization Steps"/>
</p>
<p>

<h3> 3.) Now that your creating a Virtual Machine, you'll need to select these settings.</h3>

  - You can find what Virtual Machine image you need by clicking "See all images"
  - Next you'll want to click "I confirm I have an eligible Windows 10/11 license with multi-tenant hosting rights."
  - Once your done with that you'll want to head towards Networking so that the Virtual Network, the Subnet, and the Public IP are made

<p>
<img src="https://i.imgur.com/1FIXZJR.png" height="100%" width="100%" alt="Disk Sanitization Steps"/>
</p>
<p>
<p>
<img src="https://i.imgur.com/UoELUhA.png" height="100%" width="100%" alt="Disk Sanitization Steps"/>
</p>
<p>

<h3>                                  </h3>

<h3> 4.) Once your Resource group and then your VM have been created you'll need to login to the VM. <h3>

  - If your on Windows press your Windows key and R key to open up the run command, then type in mstsc so that you can open the Remote Desktop Connection
  - Next you'll need to go back to Azure, click on your VM, then connect. Once your in the Connect page, you'll want to copy the VM IP Address.
  - Once you have the VM IP Address, copy it into the computer space and hit connect. Make sure you use your Azure username if it's different from your computer's username.

<h3>                                  </h3>

<p>
<img src="https://i.imgur.com/A9mbI87.png" height="100%" width="100%" alt="Disk Sanitization Steps"/>
</p>
<p>
<p>
<img src="https://i.imgur.com/SwJICiW.png" height="100%" width="100%" alt="Disk Sanitization Steps"/>
</p>
<p>
<p>
<img src="https://i.imgur.com/mGtDw5Z.png" height="100%" width="100%" alt="Disk Sanitization Steps"/>
</p>
<p>

<h2> Enabling features</h2>

<h3> 5.) Now that your in the VM you'll want to open control panel, go to programs, turn Windows features on or off, and then enable Internet Information Services, Web Management Tools, World Wide Web Services. <h3>

  - Press the Windows key and the R key inside the VM to open run, then type in control panel so you can access it. 

<h3>                                  </h3>

<p>
<img src="https://i.imgur.com/sZ3Brcx.png" height="100%" width="100%" alt="Disk Sanitization Steps"/>
</p>
<p>
<p>
<img src="https://i.imgur.com/WARk3XX.png" height="100%" width="100%" alt="Disk Sanitization Steps"/>
</p>
<p>
<p>
<img src="https://i.imgur.com/ISPtCq0.png" height="100%" width="100%" alt="Disk Sanitization Steps"/>
</p>
<p>
<p>
<img src="https://i.imgur.com/VcGg2aG.png" height="100%" width="100%" alt="Disk Sanitization Steps"/>
</p>
<p>

<h3> 6.) Next up open World Wide Web Services and enable Application Development Features, Common HTTP Features and make sure everything within this is checked. <h3>

<h3>                                  </h3>

<p>
<img src="https://i.imgur.com/2nNdmz8.png" height="100%" width="100%" alt="Disk Sanitization Steps"/>
</p>
<p>

<h3> 7.) Now check enable Health and Diagnostics, Performance Features, and Security. <h3>

<h3>                                  </h3>

<p>
<img src="https://i.imgur.com/gkIlGO5.png" height="100%" width="100%" alt="Disk Sanitization Steps"/>
</p>
<p>

<h3> 8.) And finally open up Application Development Features and turn on CGI. Now hit okay and wait for the changes to happen, if everything is installed and enabled correctly then if you go to your browser of choice and search for 127.0.0.1 it should open up to this page. <h3>

<h3>                                  </h3>

<p>
<img src="https://i.imgur.com/v4rsRvn.png" height="100%" width="100%" alt="Disk Sanitization Steps"/>
</p>
<p>
<p>
<img src="https://i.imgur.com/60jTcP9.png" height="100%" width="100%" alt="Disk Sanitization Steps"/>
</p>
<p>

<h2> Downloading and installing needed applications</h2>

<h3> 9.) Now that Internet Information Services, or IIS for short, is enabled we'll be downloading and installing everything we need for this. First off you'll want to download and install PHP Manager for IIS and go through the install wizard. <h3>

  - You'll find the installer in PHPManager-Master > bin > release

<h3>                                  </h3>

<p>
<img src="https://i.imgur.com/tkws0Ob.png" height="100%" width="100%" alt="Disk Sanitization Steps"/>
</p>
<p>
<p>
<img src="https://i.imgur.com/3as7HYo.png" height="100%" width="100%" alt="Disk Sanitization Steps"/>
</p>
<p>

<h3> 10.) Now that we're done with that, next up we'll be installing the Rewrite Module and go through it's installation. <h3>

<h3>                                  </h3>

<p>
<img src="https://i.imgur.com/h8SLVn8.png" height="100%" width="100%" alt="Disk Sanitization Steps"/>
</p>
<p>
<p>
<img src="https://i.imgur.com/i0OrXyW.png" height="100%" width="100%" alt="Disk Sanitization Steps"/>
</p>
<p>

<h3> 11.) We will now download PHP for extracting later</h3>

<p>
<img src="https://i.imgur.com/AjwPhz5.png" height="100%" width="100%" alt="Disk Sanitization Steps"/>
</p>
<p>
<p>
<img src="https://i.imgur.com/UFLSkPK.png" height="100%" width="100%" alt="Disk Sanitization Steps"/>
</p>
<p>

<h3>                                  </h3>

<h3> 12.) Now create a folder in the C drive called PHP and from the installation files extract PHP and unzip it's contents into C:\PHP <h3>

<h3>                                  </h3>

<p>
<img src="https://i.imgur.com/sbKW6fy.png" height="100%" width="100%" alt="Disk Sanitization Steps"/>
</p>
<p>
<p>
<img src="https://i.imgur.com/pK6rM2y.png" height="100%" width="100%" alt="Disk Sanitization Steps"/>
</p>
<p>
<p>
<img src="https://i.imgur.com/ZIhjZ7U.png" height="100%" width="100%" alt="Disk Sanitization Steps"/>
</p>
<p>

<h3> 13.) Once you have extracted the zip file into the PHP folder on the C drive, download and install the VC_redist.exe and go through the install wizard for it. <h3>

<h3>                                  </h3>

<p>
<img src="https://i.imgur.com/Ng9l0v8.png" height="100%" width="100%" alt="Disk Sanitization Steps"/>
</p>
<p>
<p>
<img src="https://i.imgur.com/7UYMFmW.png" height="100%" width="100%" alt="Disk Sanitization Steps"/>
</p>
<p>
<p>
<img src="https://i.imgur.com/wwInhJ1.png" height="100%" width="100%" alt="Disk Sanitization Steps"/>
</p>
<p>

<h3> 14.) And finally download and install MySQL 5.5.62 and run the setup wizard. <h3>

  - You'll need to select the dropdown menu and scroll down to 5.5.62
  - Make sure to Select Typical Setup

<h3>                                  </h3>

<p>
<img src="https://i.imgur.com/iFmKVsi.png" height="100%" width="100%" alt="Disk Sanitization Steps"/>
</p>
<p>
<p>
<img src="https://i.imgur.com/f1UF45N.png" height="100%" width="100%" alt="Disk Sanitization Steps"/>
</p>
<p>

<h3> 15.) You'll need to select Standard Configuration. <h3>
<h3> - As for the root password, just type in root as this is just for testing. And finally click execute on it's all done. <h3>

<h3>                                  </h3>

<p>
<img src="https://i.imgur.com/FDJDiQv.png" height="100%" width="100%" alt="Disk Sanitization Steps"/>
</p>
<p>
<p>
<img src="https://i.imgur.com/CnNY30Y.png" height="100%" width="100%" alt="Disk Sanitization Steps"/>
</p>
<p>
<p>
<img src="https://i.imgur.com/NjephPL.png" height="100%" width="100%" alt="Disk Sanitization Steps"/>
</p>
<p>

<h3> 16.) Now that we have the files downloaded and installed we will want to search for IIS in the windows search bar and then open it AS AN ADMINISTRATOR. <h3>

<h3>                                  </h3>

<p>
<img src="https://i.imgur.com/iq8IjIo.png" height="100%" width="100%" alt="Disk Sanitization Steps"/>
</p>
<p>

<h3> 17.) Next click on PHP Manager and register new PHP version. We'll want to provide a path to the php executable file to we'll be going to C drive, Php, and click on the php-cgi file. <h3>
<h3>  - Once that's done we'll restart the IIS server. <h3>

<h3>                                  </h3>

<p>
<img src="https://i.imgur.com/P6rHUDI.png" height="100%" width="100%" alt="Disk Sanitization Steps"/>
</p>
<p>
<p>
<img src="https://i.imgur.com/SwVJtgs.png" height="100%" width="100%" alt="Disk Sanitization Steps"/>
</p>
<p>
<p>
<img src="https://i.imgur.com/DmB3me4.png" height="100%" width="100%" alt="Disk Sanitization Steps"/>
</p>
<p>
<p>
<img src="https://i.imgur.com/hfkEIgY.png" height="100%" width="100%" alt="Disk Sanitization Steps"/>
</p>
<p>

<h2> Setting up OsTicket</h2>

<h3> 18.) We'll now want to install osTicket v1.15.8. <h3>

<h3>                                  </h3>

<p>
<img src="https://i.imgur.com/2pq2K2C.png" height="100%" width="100%" alt="Disk Sanitization Steps"/>
</p>
<p>

<h3> 19.) Now extract osTicket and copy the "upload' folder to C:\inetpub\wwwroot then from within this folder rename "upload" into "osTicket" and have it spelled that exact way. <h3>
<h3>  - Then we'll restart IIS again. <h3>

<h3>                                  </h3>

<p>
<img src="https://i.imgur.com/DQObNyF.png" height="100%" width="100%" alt="Disk Sanitization Steps"/>
</p>
<p>
<p>
<img src="https://i.imgur.com/WgssAZM.png" height="100%" width="100%" alt="Disk Sanitization Steps"/>
</p>
<p>
<p>
<img src="https://i.imgur.com/UJF6xJq.png" height="100%" width="100%" alt="Disk Sanitization Steps"/>
</p>
<p>
<p>
<img src="https://i.imgur.com/ljALkeT.png" height="100%" width="100%" alt="Disk Sanitization Steps"/>
</p>
<p>

<h3> 20.) On IIS go to sites, default Web Site, osTicket, on the right, click Browse :80. This will take you to the osTicket installer page. <h3>

<h3>                                  </h3>

<p>
<img src="https://i.imgur.com/6w7OEaG.png" height="100%" width="100%" alt="Disk Sanitization Steps"/>
</p>
<p>
<p>
<img src="https://i.imgur.com/oPQhyaH.png" height="100%" width="100%" alt="Disk Sanitization Steps"/>
</p>
<p>

<h3> 21.) Some extensions are not enabled on the osTicket Browser so to enable said extensions go back to IIS, sites, default, osTicket, click PHP manager. <h3>

<h3>                                  </h3>

<p>
<img src="https://i.imgur.com/25RMmsV.png" height="100%" width="100%" alt="Disk Sanitization Steps"/>
</p>
<p>

<h3> 22.) Then click Enable or disable an extension. We will want to enable three extensions from here. php_imap.dll, php_intl.dll, and php_opcache.dll <h3>

  - It'll be easier and quicker for you to find the extensions by typing them into the filter. Once you have found them, rightclick on them then leftclick enable.

<h3>                                  </h3>

<p>
<img src="https://i.imgur.com/WF2yYcM.png" height="100%" width="100%" alt="Disk Sanitization Steps"/>
</p>
<p>
<p>
<img src="https://i.imgur.com/YOVcEJg.png" height="100%" width="100%" alt="Disk Sanitization Steps"/>
</p>
<p>

<h3> 23.) Once we have the extensions enabled in IIS we are going to want to rename one of the files in our osTicket folder. <h3>

  - Go into the file explorer and search for C:\inetpub\wwwroot\osTicket\include\ost-sampleconfig.php
  - Once we have found the file we are going to rightclick on it, then leftclick rename and change ost-sampleconfig.php to ost-config.php

<h3>                                  </h3>

<p>
<img src="https://i.imgur.com/o1we5U5.png" height="100%" width="100%" alt="Disk Sanitization Steps"/>
</p>
<p>

<h3> 24.) Now that we have renamed the file, right click on the file and go to properties. <h3>

<h3>                                  </h3>

<p>
<img src="https://i.imgur.com/8bBhAFr.png" height="100%" width="100%" alt="Disk Sanitization Steps"/>
</p>
<p>

<h3> 25.) From there click security, click on advanced, and disable the inheritance. We will select Remove all inherited permissions from this object. <h3>

<h3>                                  </h3>

<p>
<img src="https://i.imgur.com/cZ4ubiq.png" height="100%" width="100%" alt="Disk Sanitization Steps"/>
</p>
<p>
<p>
<img src="https://i.imgur.com/KuWbcvX.png" height="100%" width="100%" alt="Disk Sanitization Steps"/>
</p>
<p>

<h3> 26.) Now we will add new permissions. <h3>
<h3>    - click add <h3>
<h3>    - select a principal <h3>
<h3>    - type "Everyone" in the box then click Check Names <h3>
<h3>    - Make sure full control and all the other boxes are check <h3>
<h3>    - click ok <h3>

<h3>                                  </h3>

<p>
<img src="https://i.imgur.com/1loEYgf.png" height="100%" width="100%" alt="Disk Sanitization Steps"/>
</p>
<p>
<p>
<img src="https://i.imgur.com/Pwovtcu.png" height="100%" width="100%" alt="Disk Sanitization Steps"/>
</p>
<p>

<h3> 27.) Once that is done we will continue to setup osTicket in the browser. Click continue on the osTicket browser page. Fill out the page as required except the database settings at the bottom of the page. <h3>

<h3>                                  </h3>

<p>
<img src="https://i.imgur.com/4xD5sS3.png" height="100%" width="100%" alt="Disk Sanitization Steps"/>
</p>
<p>
<p>
<img src="https://i.imgur.com/H6B27iK.png" height="100%" width="100%" alt="Disk Sanitization Steps"/>
</p>
<p>

<h3> 28.) For now we will want to download and install HeidiSQL from the installation files. Click skip on the update page. <h3>
<h3>    - When the program is open we will create a new session in it. <h3>
<h3>    - We want to make sure the username is root and the password is root. Then click open. <h3>

<h3>                                  </h3>

<p>
<img src="https://i.imgur.com/xnp5T02.png" height="100%" width="100%" alt="Disk Sanitization Steps"/>
</p>
<p>
<p>
<img src="https://i.imgur.com/vL1SrS9.png" height="100%" width="100%" alt="Disk Sanitization Steps"/>
</p>
<p>
<p>
<img src="https://i.imgur.com/Dhokm6L.png" height="100%" width="100%" alt="Disk Sanitization Steps"/>
</p>
<p>
<p>
<img src="https://i.imgur.com/jOoIIZh.png" height="100%" width="100%" alt="Disk Sanitization Steps"/>
</p>
<p>

<h3> 29.) We will now create a new database within HeidiSQL. In Heidi right click on the left side where it says "Unnamed", select create new, and then select database. Name the new database osTicket. <h3>

<h3>                                  </h3>

<p>
<img src="https://i.imgur.com/9rGCBuV.png" height="100%" width="100%" alt="Disk Sanitization Steps"/>
</p>
<p>
<p>
<img src="https://i.imgur.com/7g4LMyp.png" height="100%" width="100%" alt="Disk Sanitization Steps"/>
</p>
<p>

<h3> 30. Once we are connected to the session we will go back to the browser to finish setting everything up. Under the Database settings in the browser the username will be "Root" and the password will be "root" with the database also being osTicket. And then finally click install now. <h3>

<h3>                                  </h3>

<p>
<img src="https://i.imgur.com/EH3sgLc.png" height="100%" width="100%" alt="Disk Sanitization Steps"/>
</p>
<p>

Congratulations. You have now successfully installed osTicket.
