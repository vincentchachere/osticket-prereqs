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

- macOS
- Windows 10</b> (21H2)

## List of Prerequisites

- Create a Resource Group
- Create a Virtual Machine inside the Resource Group
- Connect Virtual Machine with Remote Desktop
- Download & Install [Installation Files](https://drive.google.com/drive/u/1/folders/1APMfNyfNzcxZC6EzdaNfdZsUwxWYChf6)
- Install/Enable IIS in Windows
- Enable Extensions for osTicket
- Rename: ost-config.php
- Assign Permissions To: ost-config.php
- Create a database for 'osTicket'
- Clean Up Resources
- Change File Permissions

***

## Installation Files

- https://drive.google.com/drive/u/1/folders/1APMfNyfNzcxZC6EzdaNfdZsUwxWYChf6

***

## 📝 Installation Steps - Part A: Create a Resource Group

### 1. ) Create a Resurce Group

<ins>Starting at the 'Home' screen in your Microsoft Azure Portal:</ins>

- Click: the `Resource Groups` icon that's already on your home screen

- or..

- Search: `Resource Groups` and click that one (They do the same thing)

<p align="center">
<img width="800" alt="isolated" src="https://github.com/vincentchachere/osticket-prereqs/assets/161680745/d273a110-a34c-4707-8a06-058d12c11cc5"><br>

***

### 2. ) Create a Resurce Group

- Click `Create` to start your Resource Group

- Or..

- You can click the blue 'Create' in the middle of the screen as well, and it will take you to the same place.

<p align="center">
<img width="800" alt="isolated" src="https://github.com/vincentchachere/osticket-prereqs/assets/161680745/56fec2c9-0ba3-4e35-8c26-6bc6e7e6313b"><br>

***

### 3. ) Create a Resurce Group

<ins>Next, we'll input the following</ins>:

- Resource Group Name: `RG-osTicket`

- Region: `(US) West US 3`

- *Scroll Down*

 >**ATTENTION: Double check spelling when creating anything (resource groups, virtual machines, etc.) or you will have to delete all your work and start over, because the information you input will NOT be able to be able to be edited once it's created (name, region, etc.)**

<p align="center">
<img width="800" alt="E2C30B0C-FA81-4329-8F23-DBB018C41018" src="https://github.com/vincentchachere/osticket-prereqs/assets/161680745/4829d10a-d483-4c28-93a1-64034a6e0cf3"><br>

***

## 4. ) Create a Resurce Group

- Click `Review + Create`

- Dont worry about the 'Tags' section, we don't need that part for this lab.

- The 'Tags' section is used for organizational purposes.

<p align="center">
<img width="800" alt="F462BC66-31ED-444E-A61B-CD02C75151FD" src="https://github.com/vincentchachere/osticket-prereqs/assets/161680745/22252a11-ece8-4e38-873c-f6faf00efe29"><br>

 >**NOTE: We have NOT finished creating the resource group yet by clicking 'Review + Create'. Microsoft Azure let's you double check (review) the information you input before finalizing (creating) your resource group. It also does this for virtual machines, so make it a habit to double check the information you type in, so that you don't have to erase everything you end up creating, because of one wrong letter.**

***

## 5. ) Review and Create!

- *Verify Your Resource Group Information Before Continuing*

- Click `Create` to awaken your resource group!

<p align="center">
<img width="800" alt="6353AD56-C708-4D3D-ABEB-7C29A8E42E5F" src="https://github.com/vincentchachere/osticket-prereqs/assets/161680745/2f2d3265-2f3f-457f-a710-1be04c7d9545"><br>

***

## Congrats!

### 6. ) You're done creating you're Resource Group!

- You should see the 'Successfully Ceated Resource Group Notification' in the top right corner of your screen.

- Click: `Refresh` if you dont see your Resource Group, then..

- Click your resource group `RG-osTicket` to enter into the next part of this lab.

<p align="center">
<img width="800" alt="3C89D03C-0D84-4484-BFD6-79D2FBDF9012" src="https://github.com/vincentchachere/osticket-prereqs/assets/161680745/e2981d35-3f56-4b35-a47d-d2dafd1600a6"><br>

 >**NOTE: Whenever you create a resource group or virtual machine and DO NOT see it in your Azure Portal in its correct location, there's two solutions to this:**

 >**First, refresh your Resource Group Default Directory (Search: Resource Group and you'll be in that section), and if that's unsuccessful..**

 >**Go through the steps again in this lab and if it doesn't let you create a resource group with the name 'RG-osTicket' (the name you originally typed in for the resurce group), then that's how you know the Resource Group is created, you will just have to wait a little longer and refresh your Resource Group Default Directory.**

***

## 📝 Installation Steps - Part B: Create a `Virtual Machine`

### 7. ) Create a Virtual Machine inside the Resource Group

- `Search:` Virtual Machine

- `Click:` Virtual Machine

<p align="center">
<img width="800" alt="isolated" src="https://github.com/vincentchachere/osticket-prereqs/assets/161680745/f81d1869-9805-40b1-b4b9-76aa85c0f751"><br>

***

### 8. ) Create a Virtual Machine inside the Resource Group

- Click one of the `Create` buttons to start creating your Virtual Machine

<p align="center">
<img width="800" alt="3C89D03C-0D84-4484-BFD6-79D2FBDF9012" src="https://github.com/vincentchachere/osticket-prereqs/assets/161680745/d2a8f586-58ac-4bea-99e8-919410d8d839"><br>

 >**Note: This is called your 'Virtual Machine Default Directory'**

***

### 9. ) Create a Virtual Machine inside the Resource Group

<ins>Now we can put in key information for our Virtual Machine</ins>

- Select your subscription

- Resource Group Name: `RG-osTicket` (the one you created)

- Virtual Machine Name: `vm-osticket` (all lowercase)

- Region: `(US) West 3`

- Availability Options: `No infrastructure redundancy required`

- Security Type: `Standard`

- Image: `Windows 10 Pro, version 22H2 - ×64 Gen2`

- *Scroll Down once completed*

<p align="center">
<img width="800" alt="isolated" src="https://github.com/vincentchachere/osticket-prereqs/assets/161680745/0f114991-5378-4dfa-ac2d-cbded1d74006"><br>

>**Leave the 'VM Architecture' & 'Run with Azure Sport Discount' parts toward the bottom alone.**

***

### 10. ) Create a Virtual Machine inside the Resource Group

<ins>As before, we will fill in the following</ins>:

- Size: `Standard_D45_v3 - 4 vcpus, 16 GiB memory ($140.16/month)`

- `Username:` vincentchachere (this can be whatever your heart desires)

- `Password:` whatever-you-want (Just remember it!)

- Public Inbound Ports: `Allow Selected Ports`

- Select Inbound Ports: `RDP (3389)`

- *`Check the Box`*

- Click: `Review and Create`

<p align="center">
<img width="800" alt="isolated" src="https://github.com/vincentchachere/osticket-prereqs/assets/161680745/d25401ce-e384-4511-a592-9747b8bc9be9"><br>

***

### 11. ) Create a Virtual Machine inside the Resource Group

- `Review` your information and `Create` your Virtual Machine!

<p align="center">
<img width="800" alt="isolated" src="https://github.com/vincentchachere/osticket-prereqs/assets/161680745/bd8c8d4b-ab9f-4c50-98bc-813db9816512"><br>

***

<p align="center">
<img width="800" alt="7089B374-E68C-4593-A778-2A53F8D60FB4" src="https://github.com/vincentchachere/osticket-prereqs/assets/161680745/f58cd4a0-9004-40c1-9a3a-e7d4a9338641"><br>

***

<p align="center">
<img width="800" alt="isolated" src="https://github.com/vincentchachere/osticket-prereqs/assets/161680745/64898c62-a446-44ba-8b8f-a49278c26c64"><br>

***

### 12. ) Create a Virtual Machine inside the Resource Group

<ins>Wait for your resources to load then</ins>:

- Click: `Go to Resources`

<p align="center">
<img width="800" alt="isolated" src="https://github.com/vincentchachere/osticket-prereqs/assets/161680745/1bd4eec6-f4e9-4329-9b97-722ee8a58024"><br>

***

### 13. ) Create a Virtual Machine inside the Resource Group

<ins>Now we are at our Virtual Machine's 'Overview Page' that is inside our Azure Portal</ins>

- (we are not inside the VM yet)

- This is where you can navigate your VM's information.

- This concludes Part B!

<p align="center">
<img width="800" alt="isolated" src="https://github.com/vincentchachere/osticket-prereqs/assets/161680745/d95f8b93-98e5-4448-89c7-a4e263b349b0"><br>

***

## 📝 Installation Steps - Part C: Remote Desktop into VM, Install Prerequisites, and Install osTicket


### 14.A ) Connect your Virtual Machine to Remote Desktop

- `Copy` your VM's (vm-osticket) `Public IP Address`

- `Verify` your `VM is running` before continuing

- *Scroll down in between images for the next few instructions for Step 14*

<p align="center">
<img width="800" alt="isolated" src="https://github.com/vincentchachere/osticket-prereqs/assets/161680745/c4aa663f-dba3-47cf-8239-255404bd541c"><br>

***

### 14.B ) Connect your Virtual Machine to Remote Desktop

- Press: `Command + Space Bar` at the same time to open up the Spotlight Search, then..

- Type In: `Remote Desktop`

- Now Click: `Microsoft Remote Desktop`

<p align="center">
<img width="800" alt="isolated" src="https://github.com/vincentchachere/osticket-prereqs/assets/161680745/84202fbf-d46c-43f7-a126-837f4b32e1fa"><br>

***

### 14.C ) Connect your Virtual Machine to Remote Desktop

- Click: `Add PC`

<p align="center">
<img width="800" alt="isolated" src="https://github.com/vincentchachere/osticket-prereqs/assets/161680745/013afe59-3d68-4628-b0f3-723c0fc36ad2"><br>

***

### 14.D ) Connect your Virtual Machine to Remote Desktop

- Paste: `vm-osticket's Public IP Address`

- Click: `Add`

<p align="center">
<img width="800" alt="isolated" src="https://github.com/vincentchachere/osticket-prereqs/assets/161680745/1e86b149-9600-4237-8eb8-9fbed507411b"><br>

***

### 15.A ) Connect your Virtual Machine to Remote Desktop

- Righ-Click: Your Remote Desktop Account

- Click: `Connect`

<p align="center">
<img width="800" alt="isolated" src="https://github.com/vincentchachere/osticket-prereqs/assets/161680745/bf3e054f-aa7f-496a-8152-f1159710c834"><br>

***

### 15.B ) Connect your Virtual Machine to Remote Desktop

- `Username:` vincentchachere (whatever you typed in at the beginnning of Part B: Step 9)

- `Password:` *YourPassword* (whatever you typed in at the beginnning of Part B: Step 9)

- Click: `Continue`

<p align="center">
<img width="800" alt="isolated" src="https://github.com/vincentchachere/osticket-prereqs/assets/161680745/78160742-2f17-4dc1-be20-d5a70c546110"><br>

***

### 15.C ) Connect your Virtual Machine to Remote Desktop

- *Uncheck: `All Boxes`*

- *Click: `Accept`*

<p align="center">
<img width="800" alt="isolated" src="https://github.com/vincentchachere/osticket-prereqs/assets/161680745/f59877e2-da56-4767-8cef-54cb4d0fdbe9"><br>

***

### 16.A ) Install/Enable IIS in Windows

- Once connected and inside your Virtual Machine we'll need to install IIS by doing the following:

  - Right-Click: `Start` in the bottom left of your screen

  - Select: `Run`

<p align="center">
<img width="800" alt="isolated" src="https://github.com/vincentchachere/osticket-prereqs/assets/161680745/6f279019-c2f3-4446-b4f1-76e5cf798e2b"><br>

***

### 16.B ) Install/Enable IIS in Windows

- Type In: `Control`

- Press: `Enter` or Click: `Ok`

<p align="center">
<img width="800" alt="isolated" src="https://github.com/vincentchachere/osticket-prereqs/assets/161680745/87a7e808-6441-42db-859b-aa78c565d8a1"><br>

***

### 16.C ) Install/Enable IIS in Windows

  - Click: `Programs`

<p align="center">
<img width="800" alt="isolated" src="https://github.com/vincentchachere/osticket-prereqs/assets/161680745/897bb69f-f091-4f03-8c55-3547cf3ad1f1"><br>

***

### 16.D ) Install/Enable IIS in Windows

  - Click: `Turn Windows Features On or Off`

<p align="center">
<img width="800" alt="isolated" src="https://github.com/vincentchachere/osticket-prereqs/assets/161680745/b9beb774-2bc5-4f35-bf61-aaf2e8c52dea"><br>

***

### 16.E ) Install/Enable IIS in Windows
                              
  - Enable: Internet Information Services (IIS)
 
  - Open & Enable: `World Wide Web Services`
    - `Check All Boxes` within this feature's folder

- *scroll down in between images for further instruction*

<p align="center">
<img width="800" alt="isolated" src="https://github.com/vincentchachere/osticket-prereqs/assets/161680745/89eb3345-1c42-416f-9ea3-6fb101a9c499"><br>

***

### 16.F ) Install/Enable IIS in Windows

-  While still inside the *World wide Web Service*:

  - Open the `Application Development Features` folder

  - Enable: `CGI`

- *Collapse Application Development Features folder*

<p align="center">
<img width="800" alt="isolated" src="https://github.com/vincentchachere/osticket-prereqs/assets/161680745/4a86fcb4-b2e3-4247-89fa-725b7c4d7583"><br>

***

### 16.G ) Install/Enable IIS in Windows

- Enable: Common HTTP Features

- Within the 'Common HTTP Fetures' feature folder

  - Check: `All Boxes` *(within this feature's folder)*
 
  - Click: 'Ok'

<p align="center">
<img width="800" alt="isolated" src="https://github.com/vincentchachere/osticket-prereqs/assets/161680745/4a756f64-9ba3-45fb-a690-0ddf5bd5b4bd"><br>

***

### 16.H ) Install/Enable IIS in Windows

- Wait for it to load...

<p align="center">
<img width="800" alt="isolated" src="https://github.com/vincentchachere/osticket-prereqs/assets/161680745/81b5957a-ab51-4c47-8e46-91a8d3b3f961"><br>

***

### 16.I ) Install/Enable IIS in Windows

- When that's done Loading Click: `Close`

<p align="center">
<img width="800" alt="isolated" src="https://github.com/vincentchachere/osticket-prereqs/assets/161680745/904c8fec-b77a-4efa-81fa-a62e801dc3fa"><br>

***

<br>

### 17.A ) Open Microsoft Edge to Test IIS

- Open: `Microsoft Edge` Internet Browser

- Click: `Start without your data`

<p align="center">
<img width="800" alt="isolated" src="https://github.com/vincentchachere/osticket-prereqs/assets/161680745/e7c74b77-ca58-4c36-8623-b641438aee10"><br>

***

### 17.B ) Open Microsoft Edge to Test IIS

- Uncheck the Box

- Click: `Continue and Conirm`

<p align="center">
<img width="800" alt="isolated" src="https://github.com/vincentchachere/osticket-prereqs/assets/161680745/80a538a2-5fca-4ffb-b416-85f369c8c3df"><br>

***

### 17.C ) Open Microsoft Edge to Test IIS

- Click: `Continue without this data`

<p align="center">
<img width="800" alt="isolated" src="https://github.com/vincentchachere/osticket-prereqs/assets/161680745/2a8021d3-6634-45de-b25f-d2f63ad50ae7"><br>

***

### 17.D ) Open Microsoft Edge to Test IIS

- Uncheck the Box

- Click: `Confirm and start browsing`

<p align="center">
<img width="800" alt="isolated" src="https://github.com/vincentchachere/osticket-prereqs/assets/161680745/1e5c7aa4-97dd-4c8d-a09d-c9cafddda685"><br>

***

### 17.E ) Open Microsoft Edge to Test IIS

- Type: `127.0.0.1` into the browser

  - If you do not see the image displayed below then try uninstalling and reinstalling IIS

  - *The `How To Uninstall and Reinstall Instructions` are directly underneath the image below.* 

<p align="center">
<img width="800" alt="isolated" src="https://github.com/vincentchachere/osticket-prereqs/assets/161680745/7c2dae78-f8bb-40ba-9f73-b24d60b25c91"><br>

>**To Uninstall and Reinstall IIS do the following:**

>**Right-Click: `start` > Click: `Run` >**

>**Type In: `Control` > Click: `Programs` >**

>**Click: `Turn Windows on or off` >**

>***Uncheck:* `IIS` > *Uncheck:* `World Wide Web Services` >**

>***Uncheck:* `Application Development Features` (Inside World Wide Web Services) >**

>***Uncheck:* `CGI` (Application Development Features) >**

>***Uncheck:* `Common HTTP Feautures` (Inside World Wide Web Services) >**

>***Uncheck:* `HTTP Redirection` (Inside Common HTTP Feautures) >**

>***Uncheck:* `WebDAV Publishing` (Inside Common HTTP Feautures)**

***

### 18.A ) Download PHP Manager for IIS

- Open: [Installation Files](https://drive.google.com/drive/u/1/folders/1APMfNyfNzcxZC6EzdaNfdZsUwxWYChf6)

  - Open the Installation Files into a seperate tab or split screen as seen below, so that you can easily access them throught out this lab.

  - Double-Click: `PHP Manager`

  - Click: The `...` Dots in the upper right of your screen next to the 'Share' button

  - Click: `Open in new window`

  - *Downloading it this way is the only way I've found where it does not take so long, and it downloads the first time instead of having to do multiple attempts.* 

<p align="center">
<img width="800" alt="isolated" src="https://github.com/vincentchachere/osticket-prereqs/assets/161680745/7c65e858-f02e-4a8f-91e3-961c718d1956"><br>

***

### 18.B ) Download PHP Manager for IIS

- Click: `Download anyway`

- <ins>Now you can Either:</ins>

  - Wait for it to pop up when its done loading or.. &darr;

  - Click: The `...` Dots in the upper left corner of your screen and Click: `Downloads`

>**Sometimes when the file downloads it does not pop up, so I wanted to show you both ways.**

>**You can also simply go to your `File Explorer` > `Downaloads` > Double-Click: `PHPManagerforIIS_V1.5.0`**

<p align="center">
<img width="800" alt="isolated" src="https://github.com/vincentchachere/osticket-prereqs/assets/161680745/e55e776c-9ea1-491a-9d10-3cd0bc79db5e"><br>

***

### 18.C ) Download PHP Manager for IIS

- Click :`Next`

<p align="center">
<img width="800" alt="isolated" src="https://github.com/vincentchachere/osticket-prereqs/assets/161680745/d259bf88-439b-42cc-9375-166f003d8808"><br>

***

### 18.D ) Download PHP Manager for IIS

- Select: `I Agree`

- Click: `Next`

<p align="center">
<img width="800" alt="isolated" src="https://github.com/vincentchachere/osticket-prereqs/assets/161680745/9199a0ea-972d-455c-9408-5365677ed221"><br>

***

### 18.E ) Download PHP Manager for IIS

- Click: `Close`

<p align="center">
<img width="800" alt="isolated" src="https://github.com/vincentchachere/osticket-prereqs/assets/161680745/ac09a285-6c4a-4ae0-8c33-2098d337d6f6"><br>

***

### 19.A ) Download Rewrite Module

- Double-Click: `rewrite_amd64_en-US.msi`

- Open: The `rewrite_amd64_en-US.msi` file when it pops up

- Check: The Box *'I accpet the terms in the License Agreement'*

- Click: `Install`

<p align="center">
<img width="800" alt="isolated" src="https://github.com/vincentchachere/osticket-prereqs/assets/161680745/3cc3863b-44d7-4b20-b781-71830ae56f1d"><br>

***

### 19.B ) Download Rewrite Module

- Click: `Finish`

<p align="center">
<img width="800" alt="isolated" src="https://github.com/vincentchachere/osticket-prereqs/assets/161680745/f8035ed7-c04b-4425-9044-8a20529b8a89"><br>

***

### 20.A ) Create Directory C:\PHP

- Go To: `File Explorer` > `This PC` > `Windows (C:)` > 

<p align="center">
<img width="800" alt="isolated" src="https://github.com/vincentchachere/osticket-prereqs/assets/161680745/42973b96-7bf7-4e37-b824-6c46ee8d7bdf"><br>

***

### 20.B ) Create Directory C:\PHP

- Right-Click: The `empty space under the files`

- Go To: `New`

- Click: `Folder`

<p align="center">
<img width="800" alt="isolated" src="https://github.com/vincentchachere/osticket-prereqs/assets/161680745/a45390d8-3afe-4c32-b5a6-2a9e939e322f"><br>

***

### 20.C ) Create Directory C:\PHP

- Type In: `PHP`

- Press: `Enter`

<p align="center">
<img width="800" alt="isolated" src="https://github.com/vincentchachere/osticket-prereqs/assets/161680745/99f82c56-1dd3-4162-b83d-c50aea410ef9"><br>

***

### 21.A ) Download php-7.3.8 and Unzip it into the Directory (C:\PHP) you just created

- Double-Click: `PHP 7.3.8`

<p align="center">
<img width="800" alt="isolated" src="https://github.com/vincentchachere/osticket-prereqs/assets/161680745/447917dd-3b9c-454c-9c18-67e56cb418f2"><br>

***

### 21.B ) Download php-7.3.8 and Unzip it into the Directory (C:\PHP) you just created

- Click : The `Download (&darr;) Arrow` in the upper right corner

<p align="center">
<img width="800" alt="isolated" src="https://github.com/vincentchachere/osticket-prereqs/assets/161680745/99d3d799-3810-41ba-a13a-546836651291"><br>

***

### 21.C ) Download php-7.3.8 and Unzip it into the Directory (C:\PHP) you just created

- Click: `Download anyway`

- Open: `php.7.3.8`

<p align="center">
<img width="800" alt="isolated" src="https://github.com/vincentchachere/osticket-prereqs/assets/161680745/95210981-7d56-4657-9d4f-9fe10429d6d4"><br>

***

### 21.D ) Download php-7.3.8 and Unzip it into the Directory (C:\PHP) you just created

- Right-Click: `php.7.3.8`

- Click: `Extract All`

<p align="center">
<img width="800" alt="isolated" src="https://github.com/vincentchachere/osticket-prereqs/assets/161680745/fa92591b-55db-4434-a0fc-4cc8823763c8"><br>

***

### 21.E ) Download php-7.3.8 and Unzip it into the Directory (C:\PHP) you just created

- Click: `Browse`

<p align="center">
<img width="800" alt="isolated" src="https://github.com/vincentchachere/osticket-prereqs/assets/161680745/7f688b04-f510-4f57-9749-f8bae9e0a3f3"><br>

***

### 21.F ) Download php-7.3.8 and Unzip it into the Directory (C:\PHP) you just created

- Go To: `This PC` > `Windows (C:)` > `PHP`

<p align="center">
<img width="800" alt="isolated" src="https://github.com/vincentchachere/osticket-prereqs/assets/161680745/fad328b2-3d4e-4668-ad14-920de414b310"><br>

***

### 21.G ) Download php-7.3.8 and Unzip it into the Directory (C:\PHP) you just created

- Click: `select Folder` (*PHP*)

<p align="center">
<img width="800" alt="isolated" src="https://github.com/vincentchachere/osticket-prereqs/assets/161680745/f673ed81-b6f4-4a26-910c-17726df34ec2"><br>

***

### 21.H ) Download php-7.3.8 and Unzip it into the Directory (C:\PHP) you just created

- Click: `Extract`

<p align="center">
<img width="800" alt="isolated" src="https://github.com/vincentchachere/osticket-prereqs/assets/161680745/514000ee-6a7c-4575-b7c6-591381562314"><br>

***

### 22.A ) Check to see the php-7.3.8 made it into the PHP Directory

- Go Back To: `This PC` > `Windows (C:)` > `PHP`

- Double-Click: `PHP`

<p align="center">
<img width="800" alt="isolated" src="https://github.com/vincentchachere/osticket-prereqs/assets/161680745/020501bb-8112-464b-b9ef-7ecb823913f4"><br>

***

### 22.C ) Check to see the php 7.3.8 made it into the PHP Directory

- Now you will see the php.7.3.8 file inside the PHP directory, as seen in the image below.

<p align="center">
<img width="800" alt="isolated" src="https://github.com/vincentchachere/osticket-prereqs/assets/161680745/c6511b61-033a-46ff-9714-50b664e19c73"><br>

***

<br>

### 23.A ) Download VC_redist.x86.exe

- Go To: [Installation Files](https://drive.google.com/drive/u/1/folders/1APMfNyfNzcxZC6EzdaNfdZsUwxWYChf6) and download VC_redist.x86.exe

  - *I will let you do the <ins>downloading</ins> steps on your own now, so that you can learn. Refer to previous steps for instruction (You got this! I believe in you!😁)*

- Check: The `I agree to the license terms and conditions` Box

- Click: `Install`

<p align="center">
<img width="800" alt="isolated" src="https://github.com/vincentchachere/osticket-prereqs/assets/161680745/170a61c1-fe3c-419f-8059-269bf6a5455c"><br>

***

<br>

### 23.B ) Download VC_redist.x86.exe

- Click: `Close` when it is done installing

<p align="center">
<img width="800" alt="isolated" src="https://github.com/vincentchachere/osticket-prereqs/assets/161680745/57eb8907-d6da-4abc-b39b-5d945d62c55f"><br>

***

### 24.A ) Download MySQL 5.5.62

- Go To: [Installation Files](https://drive.google.com/drive/u/1/folders/1APMfNyfNzcxZC6EzdaNfdZsUwxWYChf6) and download MySQL 5.5.62

- <ins>When the pop-up below shows up</ins>:

  - Click: `Next`

<p align="center">
<img width="800" alt="isolated" src="https://github.com/vincentchachere/osticket-prereqs/assets/161680745/44a36637-43cc-4fcb-9d9b-6eb64c4315a4"><br>

***

### 24.B ) Download MySQL 5.5.62

- <ins>When the pop-up below shows up</ins>:

  - Check: The `I accept the terms in the License Agreement` Box

  - Click: `Next`

<p align="center">
<img width="800" alt="isolated" src="https://github.com/vincentchachere/osticket-prereqs/assets/161680745/1a768122-511d-44ef-a428-8a4dce09c2f9"><br>

***

### 24.C ) Download MySQL 5.5.62

- Select: `Typical Setup`

- Click: `Next`

<p align="center">
<img width="800" alt="isolated" src="https://github.com/vincentchachere/osticket-prereqs/assets/161680745/14c18df3-e9ee-4cf9-a0e7-d2631f3beedf"><br>

***

### 24.D ) Download MySQL 5.5.62

- Click: `Install`

<p align="center">
<img width="800" alt="isolated" src="https://github.com/vincentchachere/osticket-prereqs/assets/161680745/f09cc5cc-9262-4951-b2ef-82d39e43ab70"><br>

***

### 24.E ) Download MySQL 5.5.62

- Check: The `Lanuch the MySQL Instance Configuration Wizard` Box

- Click: `Finish`

<p align="center">
<img width="800" alt="isolated" src="https://github.com/vincentchachere/osticket-prereqs/assets/161680745/110fd673-4225-4d28-968b-d4f0535e39b2"><br>

***

### 24.F ) Download MySQL 5.5.62

- Click: `Next`

<p align="center">
<img width="800" alt="isolated" src="https://github.com/vincentchachere/osticket-prereqs/assets/161680745/61f88e18-96bf-4991-9ad1-1222abf6cd00"><br>

***

### 24.G ) Download MySQL 5.5.62

- Select: `Standard Confirguration`

- Click: `Next`

<p align="center">
<img width="800" alt="isolated" src="https://github.com/vincentchachere/osticket-prereqs/assets/161680745/16837f9b-9535-4306-8b45-93a1c984e611"><br>

***

### 24.H ) Download MySQL 5.5.62

- Make sure your screen matches the image below and once you verify that it does..&darr;

- Click: `Next`

<p align="center">
<img width="800" alt="isolated" src="https://github.com/vincentchachere/osticket-prereqs/assets/161680745/bcf52378-fb29-4fe8-8d2a-7ce1657bf457"><br>

***

### 24.I ) Download MySQL 5.5.62

- Type In: `The password you used to log into remote desktop.`

  - Click: `Next`

<p align="center">
<img width="800" alt="isolated" src="https://github.com/vincentchachere/osticket-prereqs/assets/161680745/cec6d46c-46d7-4db1-a897-deee162df7c8"><br>

***

### 24.J ) Download MySQL 5.5.62

- Click : `Finish`

<p align="center">
<img width="800" alt="isolated" src="https://github.com/vincentchachere/osticket-prereqs/assets/161680745/bccc6a00-de77-4266-a7f3-e5c12eb30c1b"><br>

***

### 25.A )  Open IIS as an Administrator and Register PHP from within IIS

- Type: `IIS` into search bar at bottom left of your screen

- Right-Click: `IIS`

- Select: `Run as Administrator`

<p align="center">
<img width="800" alt="isolated" src="https://github.com/vincentchachere/osticket-prereqs/assets/161680745/a4190c4b-6bfe-4185-91f8-a141afcc24f5"><br>

***

### 25.B )  Open IIS as an Administrator and Register PHP from within IIS

- Double-Click: `PHP Manager`

<p align="center">
<img width="800" alt="isolated" src="https://github.com/vincentchachere/osticket-prereqs/assets/161680745/44aefc87-57e7-4c5a-8087-b0d5548c57d1"><br>

***

### 25.C )  Open IIS as an Administrator and Register PHP from within IIS

- Click: `Register vew PHP version`

- Click: the `'...' Box` (three dots box) that is next to the search bar

<p align="center">
<img width="800" alt="isolated" src="https://github.com/vincentchachere/osticket-prereqs/assets/161680745/f81cb4e5-7a83-49a9-9cb0-ae2a04fa0252"><br>

***

### 25.D )  Open IIS as an Administrator and Register PHP from within IIS

- Go To: `This PC` > `Windows (C:)` > `PHP` > `php-cgi` > `Open`

<p align="center">
<img width="800" alt="isolated" src="https://github.com/vincentchachere/osticket-prereqs/assets/161680745/9e6fcda6-cd42-4adf-95af-5d7dd0ead097"><br>

***

### 25.E )  Open IIS as an Administrator and Register PHP from within IIS

- Click: `Ok`

<p align="center">
<img width="800" alt="isolated" src="https://github.com/vincentchachere/osticket-prereqs/assets/161680745/a21252a1-3b62-4a60-8aa3-3003cf90d008"><br>

***

### 26.A )  Go To: `Home` screen of <ins>PHP Manager</ins> and Restart IIS

- Click: The `Home` icon in the upper right corner of IIS Window

<p align="center">
<img width="800" alt="isolated" src="https://github.com/vincentchachere/osticket-prereqs/assets/161680745/e67ba80d-1305-4150-9d14-71c8bcadcb3e"><br>

***

### 26.B )  Go To: `Home` screen of IIS Manager and Restart IIS

- Click: `Restart`

<p align="center">
<img width="800" alt="isolated" src="https://github.com/vincentchachere/osticket-prereqs/assets/161680745/1b9c61a7-b681-4d8f-b8ae-72192c231efa"><br>

***

### 27.A ) Install osTicket v1.15.8

- Go To: [Installation Files](https://drive.google.com/drive/u/1/folders/1APMfNyfNzcxZC6EzdaNfdZsUwxWYChf6)

- Download: `osTicket`

- <ins>Once osTicket downloads do the following</ins>:

  - Go To: `Downloads` inside of `File Explorer`

  - Double-Click: `osTicket`

<p align="center">
<img width="800" alt="isolated" src="https://github.com/vincentchachere/osticket-prereqs/assets/161680745/b227dfa3-5d6e-413b-9d9d-0ecfa562a2b3"><br>

***

### 27.B ) Install osTicket v1.15.8

- <ins>Open a second `File Explorer` by</ins>:

  - Right-Click: `File Explorer` Icon
 
  - Select: `File Explorer`

<p align="center">
<img width="800" alt="isolated" src="https://github.com/vincentchachere/osticket-prereqs/assets/161680745/29a6f966-b2c9-4c49-b810-f881efb2a566"><br>

***

### 27.C ) Install osTicket v1.15.8

- When you open the second File Explorer:

 - Go To: 'This PC' > 'Windows (C:)' > 'inetpub' > `wwwroot`

- <ins>Drag and Drop `upload` into</ins>:

  - 'This PC' > 'Windows (C:)' > 'inetpub' > `wwwroot`

<p align="center">
<img width="800" alt="isolated" src="https://github.com/vincentchachere/osticket-prereqs/assets/161680745/54aa0527-e724-48f3-898c-0c1797462f43"><br>

***

### 27.D ) Install osTicket v1.15.8

- Right-Click: `upload` *(the 'upload' that is in the new File Explorer you just opened)*

- Click: `Rename`

<p align="center">
<img width="800" alt="isolated" src="https://github.com/vincentchachere/osticket-prereqs/assets/161680745/a92db299-809a-40c2-b194-9ba4b6f01f6b"><br>

***

### 27.E ) Install osTicket v1.15.8

- Type In: `osTicket`

- Press: `Enter`

  - *Spell it exactly like: `osTicket` (with a capital `T` and lowercase everything else)*

<p align="center">
<img width="800" alt="isolated" src="https://github.com/vincentchachere/osticket-prereqs/assets/161680745/2f19fba0-01d9-413c-97b3-8fc1b71c78f2"><br>

***

### 28.A ) Refresh the osTicket site in your browser and observe the changes

- Open: `IIS` *as an Administrator*

<p align="center">
<img width="800" alt="isolated" src="https://github.com/vincentchachere/osticket-prereqs/assets/161680745/c9e6f828-a8e4-4087-be9a-c257ac61efbf"><br>

***

### 28.B ) Refresh the osTicket site in your browser and observe the changes

- Click: `Restart`

<p align="center">
<img width="800" alt="isolated" src="https://github.com/vincentchachere/osticket-prereqs/assets/161680745/0bc5bda8-62d2-47d7-8db4-2de5b7be4513"><br>

***

### 28.C ) Refresh the osTicket site in your browser and observe the changes

- Go to: `sites` > `Default` > `osTicket`

- On the Right, Click: `Browse*: 80`

<p align="center">
<img width="800" alt="isolated" src="https://github.com/vincentchachere/osticket-prereqs/assets/161680745/fbad175e-01b3-4c3a-a8fb-8b2db19db2f6"><br>

***

### 29.A ) Enable Extensions for osTicket

- Go to: `sites` > `Default` > `osTicket`

- Double-Click: `PHP Manager`

<p align="center">
<img width="800" alt="isolated" src="https://github.com/vincentchachere/osticket-prereqs/assets/161680745/d8d229e0-b240-4d9e-a330-752da0a27c6e"><br>

***

### 29.B ) Enable Extensions for osTicket

- Click: `Enable or Disable Extensions`

<p align="center">
<img width="800" alt="isolated" src="https://github.com/vincentchachere/osticket-prereqs/assets/161680745/6217973d-367a-4007-8e7d-3b09419794d0"><br>

***

### 29.C ) Enable Extensions for osTicket

- Right-Click: `php_imap.dll`

- Click: `Enable`

<p align="center">
<img width="800" alt="isolated" src="https://github.com/vincentchachere/osticket-prereqs/assets/161680745/fb7ac977-81e9-41b7-a397-34b53643734c"><br>

***

### 29.D ) Enable Extensions for osTicket

- Right-Click: `php_intel.dll`

- Click: `Enable`

<p align="center">
<img width="800" alt="isolated" src="https://github.com/vincentchachere/osticket-prereqs/assets/161680745/fc6242b4-4676-4d9a-8432-8b7b728dcda4"><br>

***

### 29.E ) Enable Extensions for osTicket

- Right-Click: `php_opache.dll`

- Click: `Enable`

<p align="center">
<img width="800" alt="isolated" src="https://github.com/vincentchachere/osticket-prereqs/assets/161680745/063d7e76-b27c-454f-b2ff-eed9ed49343d"><br>

### 29.F ) Enable Extensions for osTicket

<ins>Verify all your extensions were enabled</ins>

- You should see the 3 following extensions in the 'enabled' section:

  - php_imap.dll
 
  - php_intel.dll

  - php_opache.dll

- Click: The `osTicket` folder to the left in your 'Connections' section.

<p align="center">
<img width="800" alt="isolated" src="https://github.com/vincentchachere/osticket-prereqs/assets/161680745/48fe9a8f-2512-4ed9-b094-b3e2244352b5"><br>

***

### 30. ) Enable Extensions for osTicket

<ins>Restart the osTicket in your browser and observe the changes</ins>

- Click: `Refresh` that is in your `IIS Manager`

- Click: `Browse*:80 (http)`

- *observe the changes*

<p align="center">
<img width="800" alt="isolated" src="https://github.com/vincentchachere/osticket-prereqs/assets/161680745/2efefb03-ac37-4cbd-85e4-08d88787e3de"><br>

***

### 31.A ) Rename: ost-config.php

- Open: `File Explorer`

- Go To: `This PC` > `Windows (C:)` > `inetpub` > `wwwroot`

- Double-Click: `osTicket`

<p align="center">
<img width="800" alt="isolated" src="https://github.com/vincentchachere/osticket-prereqs/assets/161680745/b38819f3-c9e7-4c11-a6e0-f39d3de4f4ee"><br>

***

### 31.B ) Rename: ost-config.php

- Double-Click: `include`

<p align="center">
<img width="800" alt="isolated" src="https://github.com/vincentchachere/osticket-prereqs/assets/161680745/3f8b1c3c-01c9-46a2-a23e-5336a441bfd3"><br>

***

### 31.C ) Rename: ost-config.php

- Scroll: *`all the way down`*

- Right-Click: `ost-sampleconfig.php`

  - Click: `Rename`

  - Rename: `ost-sampleconfig.php`
 
  - To: `ost-config.php`
 
  - Press: `Enter` when done typing in the name

<p align="center">
<img width="800" alt="isolated" src="https://github.com/vincentchachere/osticket-prereqs/assets/161680745/c0e4ab41-43ce-4591-8454-4eae38bec613">

***

### 32.A ) Assign Permissions To: ost-config.php

- Right-Click: `ost-config.php`

- Click: `Properties`

<p align="center">
<img width="800" alt="isolated" src="https://github.com/vincentchachere/osticket-prereqs/assets/161680745/1acd9457-2365-4163-9fcc-c273ae85a833"><br>

***

### 32.B ) Assign Permissions To: ost-config.php

- Click: `Security`

- Click: `Advanced`

- Select: `Disable Inheritance`

- Click: `Remove all inherited permissions from this object.`

<p align="center">
<img width="800" alt="isolated" src="https://github.com/vincentchachere/osticket-prereqs/assets/161680745/b0a950c8-51f1-48b2-b757-d0edeebfc9ab"><br>

***

### 32.C ) Assign Permissions To: ost-config.php

- Click: `Add` > `Select a principal` > Type In: `Everyone` > Click: `Check Names`

  - *It should be underlined after you click 'Check Names'*

- Click: `Ok`

<p align="center">
<img width="800" alt="isolated" src="https://github.com/vincentchachere/osticket-prereqs/assets/161680745/63e662f4-ada6-417a-81c2-d5668c39065d"><br>

***

### 32.D ) Assign Permissions To: ost-config.php

- Select: `Full Control` *(make sure all boxes are checked as seen in the image below)*

- Click: `Ok`

- Click: `Ok`

<p align="center">
<img width="800" alt="isolated" src="https://github.com/vincentchachere/osticket-prereqs/assets/161680745/c932691e-0f52-4cb3-9f75-069499a2a54b"><br>

***

### 33. ) Restart IIS Manager and Continue Setting Up osTicket in the Browser

- Click: `Restart`

- Click: `Continue` 

<p align="center">
<img width="800" alt="isolated" src="https://github.com/vincentchachere/osticket-prereqs/assets/161680745/db18a130-c73e-41f6-b15e-3acd07c1f4bf"><br>

***

### 34. ) Continue Setting up osTicket in the browser

- <ins>Insert the following information</ins>:

  - Helpdesk Name: `Helpdesk`

  - Default Email: `yourfirstname@helper.com`

  - First Name: *AnythingYouWant* *(just remember it)*

  - Last Name: *AnythingYouWant* *(just remember it)*

  - Email Address: `yourfirstname@gmail.com`
  - *AnythingYouWant* *(just remember it)*

  - Username: *AnythingYouWant* *(just remember it)*

  - Password: *AnythingYouWant* *(just remember it)*

- *Before finishing the setup we need to dwnload HiediSQL first, so go to the next step (35.A). We'll come right back to this after.*

<p align="center">
<img width="800" alt="isolated" src="https://github.com/vincentchachere/osticket-prereqs/assets/161680745/25255d72-3702-4528-9c1a-180bd627eac6"><br>

***

### 35.A ) Download and Install HeidiSQL

- Go To: [Installation Files](https://drive.google.com/drive/u/1/folders/1APMfNyfNzcxZC6EzdaNfdZsUwxWYChf6)

- Download and Install: `HiediSQL`

- Open: `HiediSQL`

- Select: The `I accept the agreement` Circle

- Click: `Next`

<p align="center">
<img width="800" alt="isolated" src="https://github.com/vincentchachere/osticket-prereqs/assets/161680745/b9122a6b-f4c2-4055-95f8-86951eab4e8b"><br>

***

### 35.B ) Download and Install HeidiSQL

- Click: `Next`

<p align="center">
<img width="800" alt="isolated" src="https://github.com/vincentchachere/osticket-prereqs/assets/161680745/9c392d33-b538-4fe4-99a8-52d60a64cd8c"><br>

***

### 35.C ) Download and Install HeidiSQL

- Click: `Next`

<p align="center">
<img width="800" alt="isolated" src="https://github.com/vincentchachere/osticket-prereqs/assets/161680745/316b780e-beeb-438d-9ca6-26dbc2296972"><br>

***

### 35.D ) Download and Install HeidiSQL

- Click: `Next`

<p align="center">
<img width="800" alt="isolated" src="https://github.com/vincentchachere/osticket-prereqs/assets/161680745/75b5fe1c-9bb3-4fff-b073-e261d51953d1"><br>

***

### 35.E ) Download and Install HeidiSQL

- Click: `Install`

<p align="center">
<img width="800" alt="isolated" src="https://github.com/vincentchachere/osticket-prereqs/assets/161680745/0411ef50-139c-47df-8316-a93dbe99e028"><br>

***

### 35.F ) Download and Install HeidiSQL

- Click: `Finish`

<p align="center">
<img width="800" alt="isolated" src="https://github.com/vincentchachere/osticket-prereqs/assets/161680745/db333d2d-2f51-4fb9-91a2-fd693a47e50b"><br>

***

### 35.G ) Download and Install HeidiSQL

- Click: `Skip`

<p align="center">
<img width="800" alt="isolated" src="https://github.com/vincentchachere/osticket-prereqs/assets/161680745/901c0dfa-d425-4c6e-b9d4-0876d34c131e"><br>

***

### 35.H ) Download and Install HeidiSQL

- User: `root`

- Password: `The one you created at Step 34.A`

- Click: `Open` to connect to session

<p align="center">
<img width="800" alt="isolated" src="https://github.com/vincentchachere/osticket-prereqs/assets/161680745/51779cfc-4be7-4a12-8a82-944298bc67bd"><br>

***

### 35.I ) Create a Database for osTicket called `osTicket`

- Right-Click: `Unamed` > Click: `Create new` > Click: `Database`

<p align="center">
<img width="800" alt="isolated" src="https://github.com/vincentchachere/osticket-prereqs/assets/161680745/1ff3b586-e13e-43e6-9bf4-35e5bc921f57"><br>

***

### 35.J ) Create a Database for osTicket called `osTicket`

- Type In: `osTicket`

- Click: `Ok`

<p align="center">
<img width="800" alt="isolated" src="https://github.com/vincentchachere/osticket-prereqs/assets/161680745/8c806266-acbb-492c-a24b-e33bee43957f"><br>

***

### 36.A ) Continue Setting up osTicket in the browser

- MySQL Database: `osTicket`

- MySQL Username: `root`

- MySQL Password: *`The one you created at Step 34.A and the one you used at Step 35.H`*

- Click: `Install`

<p align="center">
<img width="800" alt="isolated" src="https://github.com/vincentchachere/osticket-prereqs/assets/161680745/6fe660ac-3e26-4c95-aa79-ef671d26c8fe"><br>

***

### 36.B ) Congratulations! Hopefully it is installed with no errors, but we are not finished just yet!

- *Scroll down for further instruction*

<p align="center">
<img width="800" alt="isolated" src="https://github.com/vincentchachere/osticket-prereqs/assets/161680745/7f4988fb-ea09-4432-b689-dedfe5b96449"><br>

***

### 37. ) Browse to your help desk login page: http://localhost/osTicket/scp/login.php

<ins>Before logging in we need to do 2 Things</ins>:

- Clean Up Resources

  - 1st Thing - Delete: c:\inept\wwwroot\osTicket\\*`setup`*

- Change File Permissions

  - 2nd Thing - Set Permissions to `Read` <ins>only</ins> for: This PC > inetpub > wwwroot > osTicket > include > *`ost-config.php`*

  - *Scroll down for further instruction*

<p align="center">
<img width="800" alt="isolated" src="https://github.com/vincentchachere/osticket-prereqs/assets/161680745/94a00827-144e-435d-abaa-f2b052d6cb74"><br>

***

### 38.A ) Clean Up Resources

<ins>1st Thing - Delete: c:\inept\wwwroot\osTicket\\*'setup'*</ins>

  - ONLY DELETE THE `setup` PART - NOT THE WHOLE THING

  - *scroll down for the 2nd Thing*

<p align="center">
<img width="800" alt="isolated" src="https://github.com/vincentchachere/osticket-prereqs/assets/161680745/1fcc1edd-c8da-406e-aaee-495acdd2ab82"><br>

***

### 38.B ) Change File Permissions

<ins>2nd Thing - Set Permissions to 'Read' <ins>only</ins> for *'ost-config.php'*</ins>

- File Explorer: This PC > inetpub > wwwroot > osTicket > include > *`ost-config.php`*

  - Right-Click: *`ost-config.php`*
 
  - Select: `Properties`

<p align="center">
<img width="800" alt="isolated" src="https://github.com/vincentchachere/osticket-prereqs/assets/161680745/a532e9ec-56e1-44a6-a8e1-7e02bf41ef61"><br>

***

### 38.C ) Change File Permissions

<ins>2nd Thing - Set Permissions to 'Read' <ins>only</ins> for *'ost-config.php'*</ins>

- Go To: `Security` > `Advanced` > `Edit`

<p align="center">
<img width="800" alt="isolated" src="https://github.com/vincentchachere/osticket-prereqs/assets/161680745/251d87d6-5fec-4133-a470-113d61ee3905"><br>

***

### 38.D ) Change File Permissions

<ins>2nd Thing - Set Permissions to 'Read' <ins>only</ins> for *'ost-config.php'*</ins>

- Only Check: `Read` and `Read & execute` 

  - Uncheck: `Full Control`

  - Uncheck: `Modify`

  - Uncheck: `Write`

- Click: `Apply`

- Click: `Ok`

- Click: `Ok`

<p align="center">
<img width="800" alt="isolated" src="https://github.com/vincentchachere/osticket-prereqs/assets/161680745/bd4424a4-45d3-4b57-8190-7c900d90c374"><br>

***

### 39.A ) Login To: http://localhost/osTicket/scp/login.php

- Username: *`The one you created at Step 34.A and the one you used at Step 35.H`*

- Password: *`The one you created at Step 34.A and the one you used at Step 35.H`*

<p align="center">
<img width="800" alt="isolated" src="https://github.com/vincentchachere/osticket-prereqs/assets/161680745/1b7c8e91-5375-40d9-90c2-45c2fcf7aef1"><br>

***

### 39.B ) Now you are successfully inside osTicket! Congrats!

<p align="center">
<img width="800" alt="isolated" src="https://github.com/vincentchachere/osticket-prereqs/assets/161680745/ef1ee657-b978-4494-acb7-7a4e3585acca"><br>

***

### 40. ) End Users osTicket URL:

- http://localhost/osTicket/ 

<p align="center">
<img width="800" alt="isolated" src="https://github.com/vincentchachere/osticket-prereqs/assets/161680745/e5bb86f6-de48-47f3-bcb5-97cbb620e6d8"><br>

***
