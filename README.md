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

__________________________________________________________________________________________________<br>

## Installation Files

- https://drive.google.com/drive/u/1/folders/1APMfNyfNzcxZC6EzdaNfdZsUwxWYChf6

  - Open link in seperate tab to save for later use in this lab.

__________________________________________________________________________________________________<br>

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

__________________________________________________________________________________________________<br>

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

__________________________________________________________________________________________________<br>

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

### 16. ) After that, we can now Select: `Turn Windows features on or off` 
                              
- Enable the Following:

  - Enable: Internet Information Services (IIS)
 
  - Open & Enable: `World Wide Web Services`
    - `Check All Boxes` within this feature's folder

- *scroll down in between images for further instruction*
   
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

### 17. ) When that's done go to your internet browser in Microsoft Edge

- Skip all the Pop-Ups & Uncheck all the boxes

<img width="1511" alt="isolated" src="https://github.com/vincentchachere/osticket-prereqs/assets/161680745/b360cb70-7b73-4879-bb17-614ac2dd9db8"><br>

***

<br>

<img width="1511" alt="isolated" src="https://github.com/vincentchachere/osticket-prereqs/assets/161680745/ea858b1f-37ad-43d0-985e-0a8dd73e1fd8"><br>

***

<br>

<img width="1511" alt="isolated" src="https://github.com/vincentchachere/osticket-prereqs/assets/161680745/6528279d-d330-419b-980b-9175825edb33"><br>

***

<br>

<img width="1511" alt="isolated" src="https://github.com/vincentchachere/osticket-prereqs/assets/161680745/344afc0a-86c7-4f84-89a1-e0af3e282cb1"><br>

***

<br>

<img width="1511" alt="isolated" src="https://github.com/vincentchachere/osticket-prereqs/assets/161680745/1d583dcd-b755-4aa0-b1cd-2f02970189c9"><br>

***

<br>

### 17. ) Type in 127.0.0.1 into your web browser to test that IIS works before continuing to the next step

- If you dont see the image displayed below then try uninstalling and reinstalling IIS


 >**NOTE: All you're doing when uninstalling and reinstalling IIS is undoing everything we just did in Part C: #16**

>**- To Uninstall and Reinstall IIS do the following:**

  >**Right-Click: `start` > click: `Run` > Type In: `Control` > Click: `Programs` > Click: `Turn Windows on or off` > *Uncheck:* `IIS` > *Uncheck:* `World Wide Web Services` > *Uncheck:* `Application Development Features` (Inside World Wide Web Services) > *Uncheck:* `CGI` (Application Development Features) > *Uncheck:* `Common HTTP Feautures` (Inside World Wide Web Services) > *Uncheck:* `HTTP Redirection` (Inside Common HTTP Feautures) > *Uncheck:* `WebDAV Publishing` (Inside Common HTTP Feautures)**

<img width="1511" alt="isolated" src="https://github.com/vincentchachere/osticket-prereqs/assets/161680745/b20ecb45-f3df-49b4-9a6e-34c254557dde"><br>

***

<br>

### 18. ) Download PHP Manager for IIS

- Go To: [Installation Files](https://drive.google.com/drive/u/1/folders/1APMfNyfNzcxZC6EzdaNfdZsUwxWYChf6) to down load PHP Manager

- Keep the [Installation Files](https://drive.google.com/drive/u/1/folders/1APMfNyfNzcxZC6EzdaNfdZsUwxWYChf6) in its own tab, so that you can easily access them throught out this lab, if you haven't already.

<img width="1511" alt="isolated" src=""><br>

***

<br>

### 19. ) Doanload Rewrite Module

>**Go To: [Installation Files](https://drive.google.com/drive/u/1/folders/1APMfNyfNzcxZC6EzdaNfdZsUwxWYChf6) to download MySQL 5.5.62**

<img width="1511" alt="isolated" src=""><br>

***

<br>

### 20. ) Create Directory C:\PHP

<img width="1511" alt="isolated" src=""><br>

***

<br>

### 21. ) Download PHP 7.3.8

- Unzip into the Directory (C:\PHP) you just created

>**Go To: [Installation Files](https://drive.google.com/drive/u/1/folders/1APMfNyfNzcxZC6EzdaNfdZsUwxWYChf6) to download MySQL 5.5.62**

<img width="1511" alt="isolated" src=""><br>

***

<br>

### 22. ) Download VC_redist.x86.exe

>**Go To: [Installation Files](https://drive.google.com/drive/u/1/folders/1APMfNyfNzcxZC6EzdaNfdZsUwxWYChf6) to download MySQL 5.5.62**

<img width="1511" alt="isolated" src=""><br>

***

<br>

### 23. ) Download MySQL 5.5.62

- Typical Setup
- Launch Configuration (After you download MySQL 5.5.62)
- Standard Confirguration
- Type In: *Your Password (The password you crearted when creating your VM (vm-osticket))*

>**Go To: [Installation Files](https://drive.google.com/drive/u/1/folders/1APMfNyfNzcxZC6EzdaNfdZsUwxWYChf6) to download MySQL 5.5.62**

<img width="1511" alt="isolated" src=""><br>

***

<br>

### 24. ) Open IIS as an Administrator

- 

- 

- 

<img width="1511" alt="isolated" src=""><br>

***

<br>

### 25. ) Register PHP from within IIS

<img width="1511" alt="isolated" src=""><br>

***

<br>

### 26. ) Refresh/Restart IIS

- or Start/Stop

<img width="1511" alt="isolated" src=""><br>

***

<br>

### 27. ) Install osTicket v1.15.8

- Download osTicekt from Installation File Folder
- Extract & Copy: the `upload` folder to c:\inept\wwwroot\include
- Within `c:\inept\wwwroot\include` Rename: `upload` to `osTicket` 

<img width="1511" alt="isolated" src=""><br>

***

<br>

### 28. ) Refresh/Restart IIS

- Or Stop/Start

<img width="1511" alt="isolated" src=""><br>

***

<br>

### 29. ) Inside IIS

- Go to: `sites` > `Default` > `osTicket`
- On the Right, Click: `Browse*: 80`

<img width="1511" alt="isolated" src=""><br>

***

<br>

### 30. ) Inside IIS

- Go to: `sites` > `Default` > `osTicket` > Double Click: `PHP Manager`

- Click: "Enable or Disable" an extenstion

  - Enable: imap.dll
  - Enable: intel.dll
  - Enable: opcache.dll

- Refresh/Restart the osTicket browser & observe the changes

<img width="1511" alt="isolated" src=""><br>

***

<br>

### 31. ) Rename: *ost-sample*config.php to ost-config.php

<img width="1511" alt="isolated" src=""><br>

***

<br>

### 32. ) Assign Permissions: ost-config.php

- Right-Click: `ost-config.php`
- Click: `Porperties`
- Click: `Security`
- Click: `Advanced`
- Select: `Disable Inheritance` > `Remove All`
- `New Permission` > `Everyone` > `All`
- Click: `Ok`

<img width="1511" alt="isolated" src=""><br>

***

<br>

### 33. ) Refresh PHP Manager (IIS)

<img width="1511" alt="isolated" src=""><br>

***

<br>

### 34. ) Continue Setting Up osTicket in browser

- Click: `Continue`
- Name: `Helpdesk`
- `Default Email` (recieves emails from customers)

<img width="1511" alt="isolated" src=""><br>

***

<br>

### 35. ) Go To: [Installation Files](https://drive.google.com/drive/u/1/folders/1APMfNyfNzcxZC6EzdaNfdZsUwxWYChf6)

- Install: HiediSQL
- Open: HiediSQL
- Create a *New Session*: `username/Password`
- Connect to Session
- Create a database called `osTicket`

<img width="1511" alt="isolated" src=""><br>

***

<br>

### 36. ) Continue Setting Up osTicket in Browser

- MySQL Database: `osTicket`
- MySQL Username: `vincentchachere`
- MySQL Password: `*Your Password*`
- Click: `INSTALL NOW`

<img width="1511" alt="isolated" src=""><br>

***

<br>

### 37. ) Congrats! Hopefully No Errors!

- Browse to your Helpdesk Login: http://localhost/osTicket/scp/login.php

<img width="1511" alt="isolated" src=""><br>

***

<br>

### 38. ) End Users osTicket URL:

- http://localhost/osTicket/ 

<img width="1511" alt="isolated" src=""><br>

***

<br>

### 39. ) Clean Up

- Delete: c:\inept\wwwroot\osTicket\`*setup*`

  - ONLY DELETE the `setup` part, NOT the whole thing.
 
- Delete: C:\inetpub\wwwroot\osTicket\setup

- Set Permissions to “Read” only for:

  - C:\inetpub\wwwroot\osTicket\include\ost-config.php

<img width="1511" alt="isolated" src=""><br>

>**NOTE: Browse to your help desk login page: http://localhost/osTicket/scp/login.php  
End Users osTicket URL: http://localhost/osTicket/**

***

<br>

### 40. ) 

<img width="1511" alt="isolated" src=""><br>

***

<br>

### 41. ) 

<img width="1511" alt="isolated" src=""><br>

***

<br>

### 42. ) 

<img width="1511" alt="isolated" src=""><br>

***

<br>

### 43. ) 

<img width="1511" alt="isolated" src=""><br>

***

<br>

### 44. ) 


