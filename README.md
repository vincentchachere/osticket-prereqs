<p align="center">
<img src="https://i.imgur.com/Clzj7Xs.png" alt="osTicket logo"/>
</p>

# osTicket - Prerequisites and Installation
This tutorial outlines the prerequisites and installation of the open-source help desk ticketing system osTicket.<br />

## Environments and Technologies Used

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop (macOS)
- Internet Information Services (IIS)

## Operating Systems Used

- Windows 10</b> (21H2)

## List of Prerequisites

- Connect Virtual Machine with Remote Desktop
- Install/Enable IIS in Windows
- Install Web Platform Installer
- Install osTicket v1.15.8
- Download & Install HeidiSQL
- Create a database for 'osTicket'
- Clean Up Resources
- Change File Permissions

__________________________________________________________________________________________<br>

## Installation Files

- https://drive.google.com/drive/u/1/folders/1APMfNyfNzcxZC6EzdaNfdZsUwxWYChf6

  - Open link in seperate tab to save for later use in this lab.

__________________________________________________________________________________________<br>

## 📝 Installation Steps - Part A: Create a 'Resource Group'

### 1. ) Starting at the 'Home' screen in your Microsoft Azure Portal

- Click: the `Resource Groups` icon that's already on your home screen

- or..

- Search: `Resource Groups` and click that one (They do the same thing)

<img width="1511" alt="isolated" src="https://github.com/vincentchachere/osticket-prereqs/assets/161680745/d273a110-a34c-4707-8a06-058d12c11cc5"><br>

***

<br>

### 2. ) Click `Create` to start your Resource Group

- Or..

- You can click the blue 'Create' in the middle of the screen as well, and it will take you to the same place.

<img width="1511" alt="isolated" src="https://github.com/vincentchachere/osticket-prereqs/assets/161680745/56fec2c9-0ba3-4e35-8c26-6bc6e7e6313b"><br>

***

<br>

### 3. ) Next, we'll input the following:

- Resource Group Name: `RG-osTicket`

- Region: `(US) West US 3`

- *Scroll Down*

 >**ATTENTION: Double check spelling when creating anything (resource groups, virtual machines, etc.) or you will have to delete all your work and start over, because the information you input will NOT be able to be able to be edited once it's created (name, region, etc.)**

<img width="1511" alt="E2C30B0C-FA81-4329-8F23-DBB018C41018" src="https://github.com/vincentchachere/osticket-prereqs/assets/161680745/4829d10a-d483-4c28-93a1-64034a6e0cf3"><br>

***

<br>

## 4. ) Now, let's click `Review + Create`

- Dont worry about the 'Tags' section, we don't need that part for this lab.

- The 'Tags' section is used for organizational purposes.

<img width="1511" alt="F462BC66-31ED-444E-A61B-CD02C75151FD" src="https://github.com/vincentchachere/osticket-prereqs/assets/161680745/22252a11-ece8-4e38-873c-f6faf00efe29"><br>

 >**NOTE: We have NOT finished creating the resource group yet by clicking 'Review + Create'. Microsoft Azure let's you double check (review) the information you input before finalizing (creating) your resource group. It also does this for virtual machines, so make it a habit to double check the information you type in, so that you don't have to erase everything you end up creating, because of one wrong letter.**

***

<br>

## 5. ) Finally, we review and create!

- Look over the resource rroup rnformation.

- `Verify` your `Information`

- Click `Create` to bring alive your first resource group!

<img width="1511" alt="6353AD56-C708-4D3D-ABEB-7C29A8E42E5F" src="https://github.com/vincentchachere/osticket-prereqs/assets/161680745/2f2d3265-2f3f-457f-a710-1be04c7d9545"><br>

***

<br>

## Congrats!

### 6. ) You're done creating you're Resource Group!

- You should see the 'Successfully Ceated Resource Group Notification' in the top right corner of your screen.

- Click: `Refresh` if you dont see your Resource Group, then..

- Click your resource group `RG-osTicket` to enter into the next part of this lab.

<img width="1509" alt="3C89D03C-0D84-4484-BFD6-79D2FBDF9012" src="https://github.com/vincentchachere/osticket-prereqs/assets/161680745/e2981d35-3f56-4b35-a47d-d2dafd1600a6"><br>

 >**NOTE: Whenever you create a resource group or virtual machine and DO NOT see it in your Azure Portal in its correct location, there's two solutions to this:**

 >**First, refresh your Resource Group Default Directory (Search: Resource Group and you'll be in that section), and if that's unsuccessful..**

 >**Go through the steps again in this lab and if it doesn't let you create a resource group with the name 'RG-osTicket' (the name you originally typed in for the resurce group), then that's how you know the Resource Group is created, you will just have to wait a little longer and refresh your Resource Group Default Directory.**

_______________________________________________________________________________________________________<br>

## 📝 Installation Steps - Part B: Create a `Virtual Machine`

### 7. ) Now, for this second part we will create a 'Virtual Machine' inside the resource group we just created.

- Searh: `Virtual Machine` and click it to continue.

<img width="1511" alt="isolated" src="https://github.com/vincentchachere/osticket-prereqs/assets/161680745/f81d1869-9805-40b1-b4b9-76aa85c0f751"><br>

***

<br>

### 8. ) Click one of the `Create` buttons to start creating your Virtual Machine

<img width="1509" alt="3C89D03C-0D84-4484-BFD6-79D2FBDF9012" src="https://github.com/vincentchachere/osticket-prereqs/assets/161680745/d2a8f586-58ac-4bea-99e8-919410d8d839"><br>

 >**Note: This is called your 'Virtual Machine Default Directory'**

***

<br>

### 9. ) Now we can put in key information for our Virtual Machine

- Select your subscription

- Resource Group Name: `RG-osTicket` (the one you created)

- Virtual Machine Name: `vm-osticket` (all lowercase)

- Region: `(US) West 3`

- Availability Options: `No infrastructure redundancy required`

- Security Type: `Standard`

- Image: `Windows 10 Pro, version 22H2 - ×64 Gen2`

- *Scroll Down once completed*

<img width="1511" alt="isolated" src="https://github.com/vincentchachere/osticket-prereqs/assets/161680745/0f114991-5378-4dfa-ac2d-cbded1d74006"><br>

>**Leave the 'VM Architecture' & 'Run with Azure Sport Discount' parts toward the bottom alone.**

***

<br>

### 10. ) As before, we will fill in the following:

- Size: `Standard_D45_v3 - 4 vcpus, 16 GiB memory ($140.16/month)`

- Username: vincentchachere (this can be whatever your heart desires)

- Password: whatever-you-want (Just remember it!)

- Public Inbound Ports: `Allow Selected Ports`

- Select Inbound Ports: `RDP (3389)`

- *`Check the Box`*

- Go ahead and click `Review and Create`

<img width="1511" alt="isolated" src="https://github.com/vincentchachere/osticket-prereqs/assets/161680745/d25401ce-e384-4511-a592-9747b8bc9be9"><br>

***

<br>

### 11. ) `Review` your Information and Officially `Create` your Virtual Machine!

<br>

<img width="1511" alt="isolated" src="https://github.com/vincentchachere/osticket-prereqs/assets/161680745/bd8c8d4b-ab9f-4c50-98bc-813db9816512"><br>

<img width="1728" alt="7089B374-E68C-4593-A778-2A53F8D60FB4" src="https://github.com/vincentchachere/osticket-prereqs/assets/161680745/f58cd4a0-9004-40c1-9a3a-e7d4a9338641"><br>

<img width="1511" alt="isolated" src="https://github.com/vincentchachere/osticket-prereqs/assets/161680745/64898c62-a446-44ba-8b8f-a49278c26c64"><br>

***

<br>

### 12. ) Wait for your Virtual Machine to load and go to your new Resource group

<img width="1511" alt="isolated" src="https://github.com/vincentchachere/osticket-prereqs/assets/161680745/acdefb7f-15ac-48ae-a1d0-3229dfb68a88"><br>

>**NOTE: You can wait for your VM to be completed on the screen displayed in the image below or `Click: Go to Resource` and wait there.**

<img width="1511" alt="isolated" src="https://github.com/vincentchachere/osticket-prereqs/assets/161680745/1bd4eec6-f4e9-4329-9b97-722ee8a58024"><br>

***

<br>

### 13. ) Now we are at our Virtual Machine's 'Overview Page' that is inside our Azure Portal

- (we are not inside the VM yet)

- This is where you can navigate your VM's information.

- This concludes Part B!

<img width="1511" alt="isolated" src="https://github.com/vincentchachere/osticket-prereqs/assets/161680745/d95f8b93-98e5-4448-89c7-a4e263b349b0"><br>

__________________________________________________________________________________________<br>

## 📝 Installation Steps - Part C: Remote Desktop into VM, Install Prerequisites, and Install osTicket


### 14. ) Connect your Virtual Machine to Remote Desktop by doing the follwing:

- `Copy` your VM's (vm-osticket) Public IP Address
- `Verify` your `VM is running` before continuing
- *Scroll down in between images for the next few instructions*

<img width="1511" alt="isolated" src="https://github.com/vincentchachere/osticket-prereqs/assets/161680745/c4aa663f-dba3-47cf-8239-255404bd541c"><br>

***

<br>

- Press: `Command + Space Bar` at the same time to open up the Spotlight Search, then..
- Type In: `Remote Desktop`
- Now Click: `Microsoft Remote Desktop`

<img width="1511" alt="isolated" src="https://github.com/vincentchachere/osticket-prereqs/assets/161680745/84202fbf-d46c-43f7-a126-837f4b32e1fa"><br>

***

<br>

- Click: `Add PC` and then..

<img width="1511" alt="isolated" src="https://github.com/vincentchachere/osticket-prereqs/assets/161680745/013afe59-3d68-4628-b0f3-723c0fc36ad2"><br>

***

<br>

- Paste: `vm-osticket's Public IP Address`
- Click: `Add`

<img width="1511" alt="isolated" src="https://github.com/vincentchachere/osticket-prereqs/assets/161680745/1e86b149-9600-4237-8eb8-9fbed507411b"><br>

***

<br>

- Righ-Click: Remote Desktop Account
- Click: `Connect`

<img width="1511" alt="isolated" src="https://github.com/vincentchachere/osticket-prereqs/assets/161680745/bf3e054f-aa7f-496a-8152-f1159710c834"><br>

***

<br>

- Login
  - `Username:` vincentchachere (whatever you typed in st the beginnning of Part B: Step 9)
  - `Password:` MyPassword (whatever you typed in st the beginnning of Part B: Step 9)
 
<img width="1511" alt="isolated" src="https://github.com/vincentchachere/osticket-prereqs/assets/161680745/78160742-2f17-4dc1-be20-d5a70c546110"><br>

- *`Uncheck all` the `boxes` (we dont need any of them)*
- Click: `Accept`

<img width="1511" alt="isolated" src="https://github.com/vincentchachere/osticket-prereqs/assets/161680745/f59877e2-da56-4767-8cef-54cb4d0fdbe9"><br>

***

<br>

### 15. ) Once connected and inside your Virtual Machine we'll need to:

- Right-Click: `Start` in the bottom left of your screen
- Select: `Run`

<img width="1511" alt="isolated" src="https://github.com/vincentchachere/osticket-prereqs/assets/161680745/d0a45cc6-d839-4c06-95f2-32ae350ce719"><br>

***

<br>

- Type In: `Control`
- Press: `Enter` or Click: `Ok`

<img width="1511" alt="isolated" src="https://github.com/vincentchachere/osticket-prereqs/assets/161680745/a55cb772-6e1e-406e-b6cf-e92c24bb8742"><br>

***

<br>

- Click: `Programs`
- Click: `Turn Windows Features On or Off`

<img width="1511" alt="isolated" src="https://github.com/vincentchachere/osticket-prereqs/assets/161680745/4681b035-50c5-4d6c-92d1-348a05252dbd"><br>

***

<br>

<img width="1511" alt="isolated" src="https://github.com/vincentchachere/osticket-prereqs/assets/161680745/9df9fab4-a98c-4163-b863-4a844660e08a"><br>

***

<br>

- Enable the Following:

  - Enable: Internet Information Services (IIS)
 
  - Open & Enable: `World Wide Web Services`
    - `Check All Boxes` within this feature's folder
   
<img width="1511" alt="isolated" src="https://github.com/vincentchachere/osticket-prereqs/assets/161680745/8f66567f-2ab1-4ffe-a2b3-949d5d06bc35"><br>

***

<br>

- Now, while still inside the *World wide Web Service*:
- Open the `Application Development Features` folder
   - Enable: `CGI`
    - *Collapse World Wide Web Service feature folder*

<img width="1511" alt="isolated" src="https://github.com/vincentchachere/osticket-prereqs/assets/161680745/bf191a8d-3aef-4a00-8076-63c39a010ef7"><br>

***

<br>

 - Enable: Common HTTP Features and..
    - `Check All Boxes` within this feature's folder
   
  - Click: 'Ok'

<img width="1511" alt="isolated" src="https://github.com/vincentchachere/osticket-prereqs/assets/161680745/f815d194-ed55-4989-9663-638c95091f25"><br>

***

<br>

<img width="1511" alt="isolated" src="https://github.com/vincentchachere/osticket-prereqs/assets/161680745/94763f83-0b52-491c-927e-5f27e77a41c5"><br>

***

<br>

<img width="1511" alt="isolated" src="https://github.com/vincentchachere/osticket-prereqs/assets/161680745/b360cb70-7b73-4879-bb17-614ac2dd9db8"><br>

***

<br>

When that's done go to your internet browser in Microsoft Edge

- Skip all the 

<img width="1511" alt="isolated" src=""><br>

***

<br>

<img width="1511" alt="isolated" src=""><br>

***

<br>

<img width="1511" alt="isolated" src=""><br>

***

<br>

### 16. ) After that, we can now Select: `Turn Windows features on or off` 

- Enable: 'Internet Information Services' (IIS) from the available services.

<img width="1511" alt="isolated" src=""><br>
 
### 18. ) Once WebPI is installed:

- Add MySQL 5.5 database,
- PHP 5.6.31,
- and the various verisons of PHP (x86) 7.0 and 7.3.</p>

<p align="center">
<img src="https://i.imgur.com/SwHYmt7.png" height="650%" width="65%" alt="image of add MySql"/>
</p>
</br>
<p align="center">
<img src="https://i.imgur.com/DwQqpH8.png" height="65%" width="65%" alt="install PHP"/>
</p>
<br/>

### 19. ) MySQL 5.5 will require a name and password

- Root and Password1 respectively when you try to install
- Remember your username / password !
>**As you will need it again later on in the installation process**

<p align="center">
<img src="https://i.imgur.com/IIFCRPG.png" height="65%" width="65%" alt="password request"/>
</p>

### 20. ) If necessary, fix any failures (download from within lab files:
 
- Fix any failures in the installation by:

  - Going to `Google Drive` to <a href="https://drive.google.com/drive/u/1/folders/1APMfNyfNzcxZC6EzdaNfdZsUwxWYChf6">download </a> and..
  - Install: `PHP 7.3.8`
  - Install: 'PHP Manager' and..
  - Install : `Microsoft Visual C++ 2009 Redistributable Package`

### 21. ) From the downloaded files

- We can now install and extract the osTicket file
- Extract and copy the “upload” folder INTO c:\inetpub\wwwroot
- Within c:\inetpub\wwwroot
  - Rename “upload” to "osTicket"

<p align="center">
<img src="https://i.imgur.com/F1wPGL1.png" height="65%" width="65%" alt="exacted osTicket files."/>
 
### 22. ) Reload IIS

- Open IIS
- Restart the server
- Go to `sites`
  - `Default`
  - `osTicket`
  - On the right, Click: `Browse *:80`
 
 <p align="center">
    <img src="https://i.imgur.com/A8LBhGS.png" height="65%" width="65%" alt="IIS restart"/>
    </p>
    <p align="center"> 

<img src="https://i.imgur.com/bbcdcJo.png" height=45% width="45%" alt="browse: 80"/>
    </p> 
    </br>
    
### 23. ) Once `browse: 80` is selected;

- A browser window will open, presenting osTicket installer page..
- Along with, the recommendation/prerequisites of use.
    
 <p align="center">
    <img src="https://i.imgur.com/wcCxx5C.png" height="45%" width="45%" alt="os ticket installer"/>
    </p>
    </br>
    
### 24. ) Next we'll go back to IIS

- Select: `sites`
- Select: `Default`
- Select: `osTicket`
- Double-click: `PHP Manager`
- Click: `Enable or disable an extension`
- Enable: `php_imap.dll`
- Enable: `php_intl.dll`
- Enable: `php_opcache.dll` -

 <p align="center"<img src="https://i.imgur.com/YVjKOMp.png" height="50%" width="50%" alt="php manager"/>
 </p>
 
 <br/>
 
 <p align="center">
 <img src="https://i.imgur.com/elGuTsd.png" height="45%" width="45%" alt="php extension enabled"/>
 </p>
 
 <br/>
 
 <p align="center">
 <img src="https://i.imgur.com/cMtCuaA.png" height="45%" width="45%" alt="php extension enabled"/>
 </p>
 <br/>
 
### 25. ) `Refresh` the osTicket site in your browser

- This is to see what has changed *after enabling the PHP extensions*

<p align="center">
 <img src="https://i.imgur.com/PPNziV5.png" height="45%" width="45%" alt="refreshed osticket installer"/>
 </p>
 <br/>
 
- Rename: From: `C:\inetpub\wwwroot\osTicket\include\ost-sampleconfig.php`
- To: `C:\inetpub\wwwroot\osTicket\include\ost-config.php`
 
 <p align="center">
 <img src="https://i.imgur.com/u0bCrDC.png" height="50%" width="50%" alt="ost-sample image"/>
 </p>
<p align="center">
 <img src="https://i.imgur.com/mkBhToH.png" height="50%" width="50%" alt="ost-config image"/>
 </p>
<hr>

### 26. ) Assign Permissions: ost-config.php 

- To change the permissions: `right-click ost-config`
- Select: `properties`
- Select: `Security` tab at the top
- Select: `Advanced` button
- Click: `Disable inheritance`
- Click: `Remove All`
- ADD: `New Permissions`
- ADD: `Everyone`
- ADD: `All`
 
 <p align="center">
 <img src="https://i.imgur.com/Ds8JUvt.png" height="50%" width="50%" alt="properties selection"/>
 </p>
 <p align="center">
 <img src="https://i.imgur.com/rKhcHkW.png" height="50%" width="50%" alt="change permissions"/>
</p>
<br/>
<p align="center">
<img src="https://i.imgur.com/IxpkEaE.png" height="50%" width="50%" alt="disable inheritance"/>
 </p>
<p align="center">
<img src="https://i.imgur.com/xajjPGK.png" height="50%" width="50%" alt="remove all inherited"/>
 </p>
 
### 27. ) Then `Add New Permissions` *for everyone* and `give Full Control`

<p align="center">
 <img src="https://i.imgur.com/Q9XQLXm.png" height="50%" width="50%" alt="add permssions for everyone"/>
 </p>
 
### 28. ) After returning to the browser windows with osTicket installer and press '`Continue`', you will now see the below form to complete before continuing.  
 
 <p align="center">
 <img src="https://i.imgur.com/fjKAgGk.png" height="50%" width="50%" alt="osticket form"/>
</p>

### 29. ) Download and install HeidiSQL from: 

- <a href="https://drive.google.com/drive/folders/1APMfNyfNzcxZC6EzdaNfdZsUwxWYChf6">Google Drive</a>
  - Using the provided defaults that are available in the install wizard.

 <hr>
<p align="center">
 <img src="https://i.imgur.com/oImw5w0.png" height="50%" width="50%" alt="completion of heidisql install"/>

### 30. ) Next we will do the following in HeidiSql:

- Create a new session, username:root/password:Password1
- Connect to the session
- Create a database called `osTicket`
 
 <p align="center">
 <img src="https://i.imgur.com/D2QfMEb.png"  height="50%" width="50%" alt="create HeidiSql session"/> 
 </p>
 <p align="center">
 <img src="https://i.imgur.com/3bMHP2K.png" height="50%" width="50%" alt="create database HeidiSql"/> 
 </p>
 
### 31. ) Created database for `osTicket`:
 
 <p align="center">
 <img src="https://i.imgur.com/mLg4tOl.png" height="50%" width="50%" alt="create data base osTicket"/> 
</p>

### 32. ) After the database is created, we can now enter those details into osTicket Installer 

- MySQL Username: root
- MySQL Password: Password1
- Click <b><i>“Install Now!”

### 33. ) Congratulations, hopefully it is installed with no errors!

<p align="center">
 <img src="https://i.imgur.com/V3GSvvT.png" height="50%" width="50%" alt="congratulations of completion for osTicket"/>
</p>

>**Results below are from of choosing for "`Your Staff Control Panel`" or "`Your osTicket URL:`**
 
 <p align="center"><img src="https://i.imgur.com/LhTgI92.png" height="50%" width="50%" alt="available links to choose help desk or admin"/>
 </p>
 <p align="center">
 <img src="https://i.imgur.com/jNkPZNC.jpg" height="65%" width="65%" alt="Admin login for osTicket"/>
</p>

### 34. ) `Your osTicket URL` will direct us to the `End User` Portal

- This is where users can submit tickets for assistance from the help desk.

 <p align="center">
  <img src="https://i.imgur.com/ErvbCg6.png" height="65%" width="65%" alt="End user login page to open/check ticket status"/>
  </p>

### 35. ) Clean Up!

- Delete: C:\inetpub\wwwroot\osTicket\setup</li>
- Set Permissions to “Read” only: C:\inetpub\wwwroot\osTicket\include\ost-config.php</li> 
- Login to the osTicket Admin Panel
- ([http://localhost/osTicket/scp/login.php](http://localhost/osTicket/scp/login.php)

  <p align="center">
 <img src="https://i.imgur.com/XGHz3lx.png" height="65%" width="65%" alt="delete setup folder"/>
 </p>
 
### 36. ) Set Permission to "`Read`" 

- Only can be acheived by right-clicking `ost-config.php`
- Select: `properties`
- Select: `Security` tab near the top
- Then Click: `Advanced` button (not pictured below)
- Once `advanced settings` is selected..
- You can now Select: `Everyone` principle
- Lastly, we can Select: `Read` *only* as the preferred permission(s)

 <p align="center">
 <img src="https://i.imgur.com/AXCIeQN.png"  height="65%" width="65%" alt="read-only permissions"/>
 </p>
 
 <p align="center">
  
 <img src="https://i.imgur.com/R11rIMd.png"  height="65%" width="65%" alt="read-only allow is shown for osticketcong file"/>
 </p>
 
 <br/>
 
## Next Up osTicket Post Install Configuration (Link Coming Soon..)



                                                                                 



