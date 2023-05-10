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

<h2>Prerequisites</h2>

<p>

<img src="https://i.imgur.com/L7azQHL.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>

<p>
<p>

- The first step you would need to take is to create a resource group in Azure




<img src="https://i.imgur.com/39HMPgb.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>

- Next, you will go to your Azure portal in search of virtal machine. When creating the VM, allow it to create a new Virtual Network (Vnet)
- Create an Azure Virtual Machine Windows 10, 4 vCPUs
Once you have created your VM give it a name ex:Vm-osticket. Next, you will want tp create a Username Password of whatever you chose




<img src="https://i.imgur.com/BC3MyNv.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>

- Download Microsoft Remote Desktop to your computer or what is copatiable with your computer the one listed and shown above is compatable for Mac users.









<h2>Installation Steps</h2>

<p>
<img src="https://i.imgur.com/r2GAKhi.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>


<img src="https://i.imgur.com/gOsxCW4.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>

Now that you have created the virtual machine it is time to installation. Go into the virtual machine you just created and copy the IP address to the Microsoft Remote Desktop. Please remember your username and password you created. This will kbe needed to login.
</p>
<br />

<p>
<img src="https://i.imgur.com/jv6BL2L.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
After logging in go to the Microsoft Edge. Click on start without data. Levae this tab open and come back later after installs. 
</p>
<br />

<p>
<img src="https://i.imgur.com/eClDo4u.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
Now you will go to the controll panle and go to programms to Install / Enable IIS in Windows WITH CGI. Next, World Wide Web Services -> Application Development Features -> [X] CGI
<p>

<img src="https://i.imgur.com/mCPvKF6.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Download and install PHP Manager for IIS (PHPManagerForIIS_V1.5.0.msi)

</p>


<img src="https://i.imgur.com/q3Q8q5S.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>

</p>
<p>
Download and install the Rewrite Module (rewrite_amd64_en-US.msi)
</p>

<img src="https://i.imgur.com/DySnKoH.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Create a folder for your files being added. Then download and zip the necessary files to the folder you created.

</p>

<img src="https://i.imgur.com/rmRzpR7.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Download and install VC_redist.x86.exe.

</p>

<img src="https://i.imgur.com/JgOd27X.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
You will now need to download and install MySQL 5.5.62 (mysql-5.5.62-win32.msi)
•	Typical Setup ->
•	Launch Configuration Wizard (after install) ->
•	Standard Configuration ->
•	Create Password


</p>

<img src="https://i.imgur.com/bk2vDI6.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Go to start menu and type in IIS. Once located right click on it and run as administrator.

</p>

<img src="https://i.imgur.com/7xxYZ8h.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Register PHP from within IIS and reload IIS (Open IIS, Stop and Start the server).
</p>

<img src="https://i.imgur.com/jZY7KJ5.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Install osTicket v1.15.8
•	Download osTicket from the Installation Files Folder
•	Extract and copy “upload” folder to c:\inetpub\wwwroot
•	Within c:\inetpub\wwwroot, Rename “upload” to “osTicket”

</p>

<img src="https://i.imgur.com/0qOpLdC.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Reload IIS (Open IIS, Stop and Start the server)

</p>

<img src="https://i.imgur.com/bJ0bq40.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Go to sites -> Default -> osTicket
•	On the right, click “Browse *:80”

</p>

<img src="https://i.imgur.com/oCgeqyY.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Some extensions are not enabled and you will need to go back to do so.
•	Go back to IIS, sites -> Default -> osTicket

•	Double-click PHP Manager

•	Click “Enable or disable an extension”

•	Enable: php_imap.dll

•	Enable: php_intl.dll

•	Enable: php_opcache.dll

•	Refresh the osTicket site in your browse, observe the changes

</p>

<img src="https://i.imgur.com/lZPdTxE.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
 Now you will rename: ost-config.php
•	From: C:\inetpub\wwwroot\osTicket\include\ost-sampleconfig.php

 
•	To: C:\inetpub\wwwroot\osTicket\include\ost-config.php

</p>

<img src="https://i.imgur.com/8g5DkiU.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Now you will Assign Permissions: ost-config.php
•	Disable inheritance -> Remove All

•	New Permissions -> Everyone -> All


</p>

<img src="https://i.imgur.com/YO8Kkxt.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Now you will continue setting up osTicket in the browser (click Continue)
•	Name Helpdesk

•	Default email (receives email from customers)

</p>

<img src="https://i.imgur.com/ue4zNSj.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Congratulations, you have installed OsTicket!
•	Browse to your help desk login page: http://localhost/osTicket/scp/login.php
</p>
<br />
