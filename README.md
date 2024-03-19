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

<img width="1511" alt="isolated" src="https://github.com/vincentchachere/osticket-prereqs/assets/161680745/d273a110-a34c-4707-8a06-058d12c11cc5"><br>

***

### 2. ) Create a Resurce Group

- Click `Create` to start your Resource Group

- Or..

- You can click the blue 'Create' in the middle of the screen as well, and it will take you to the same place.

<img width="1511" alt="isolated" src="https://github.com/vincentchachere/osticket-prereqs/assets/161680745/56fec2c9-0ba3-4e35-8c26-6bc6e7e6313b"><br>

***

### 3. ) Create a Resurce Group

<ins>Next, we'll input the following</ins>:

- Resource Group Name: `RG-osTicket`

- Region: `(US) West US 3`

- *Scroll Down*

 >**ATTENTION: Double check spelling when creating anything (resource groups, virtual machines, etc.) or you will have to delete all your work and start over, because the information you input will NOT be able to be able to be edited once it's created (name, region, etc.)**

<img width="1511" alt="E2C30B0C-FA81-4329-8F23-DBB018C41018" src="https://github.com/vincentchachere/osticket-prereqs/assets/161680745/4829d10a-d483-4c28-93a1-64034a6e0cf3"><br>

***

## 4. ) Create a Resurce Group

- Click `Review + Create`

- Dont worry about the 'Tags' section, we don't need that part for this lab.

- The 'Tags' section is used for organizational purposes.

<img width="1511" alt="F462BC66-31ED-444E-A61B-CD02C75151FD" src="https://github.com/vincentchachere/osticket-prereqs/assets/161680745/22252a11-ece8-4e38-873c-f6faf00efe29"><br>

 >**NOTE: We have NOT finished creating the resource group yet by clicking 'Review + Create'. Microsoft Azure let's you double check (review) the information you input before finalizing (creating) your resource group. It also does this for virtual machines, so make it a habit to double check the information you type in, so that you don't have to erase everything you end up creating, because of one wrong letter.**

***

## 5. ) Review and Create!

- *Verify Your Resource Group Information Before Continuing*

- Click `Create` to awaken your resource group!

<img width="1511" alt="6353AD56-C708-4D3D-ABEB-7C29A8E42E5F" src="https://github.com/vincentchachere/osticket-prereqs/assets/161680745/2f2d3265-2f3f-457f-a710-1be04c7d9545"><br>

***

## Congrats!

### 6. ) You're done creating you're Resource Group!

- You should see the 'Successfully Ceated Resource Group Notification' in the top right corner of your screen.

- Click: `Refresh` if you dont see your Resource Group, then..

- Click your resource group `RG-osTicket` to enter into the next part of this lab.

<img width="1509" alt="3C89D03C-0D84-4484-BFD6-79D2FBDF9012" src="https://github.com/vincentchachere/osticket-prereqs/assets/161680745/e2981d35-3f56-4b35-a47d-d2dafd1600a6"><br>

 >**NOTE: Whenever you create a resource group or virtual machine and DO NOT see it in your Azure Portal in its correct location, there's two solutions to this:**

 >**First, refresh your Resource Group Default Directory (Search: Resource Group and you'll be in that section), and if that's unsuccessful..**

 >**Go through the steps again in this lab and if it doesn't let you create a resource group with the name 'RG-osTicket' (the name you originally typed in for the resurce group), then that's how you know the Resource Group is created, you will just have to wait a little longer and refresh your Resource Group Default Directory.**

***

## 📝 Installation Steps - Part B: Create a `Virtual Machine`

### 7. ) Create a Virtual Machine inside the Resource Group

- `Search:` Virtual Machine

- `Click:` Virtual Machine

<img width="1511" alt="isolated" src="https://github.com/vincentchachere/osticket-prereqs/assets/161680745/f81d1869-9805-40b1-b4b9-76aa85c0f751"><br>

***

### 8. ) Create a Virtual Machine inside the Resource Group

- Click one of the `Create` buttons to start creating your Virtual Machine

<img width="1509" alt="3C89D03C-0D84-4484-BFD6-79D2FBDF9012" src="https://github.com/vincentchachere/osticket-prereqs/assets/161680745/d2a8f586-58ac-4bea-99e8-919410d8d839"><br>

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

<img width="1511" alt="isolated" src="https://github.com/vincentchachere/osticket-prereqs/assets/161680745/0f114991-5378-4dfa-ac2d-cbded1d74006"><br>

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

<img width="1511" alt="isolated" src="https://github.com/vincentchachere/osticket-prereqs/assets/161680745/d25401ce-e384-4511-a592-9747b8bc9be9"><br>

***

### 11. ) Create a Virtual Machine inside the Resource Group

- `Review` your information and `Create` your Virtual Machine!

<img width="1511" alt="isolated" src="https://github.com/vincentchachere/osticket-prereqs/assets/161680745/bd8c8d4b-ab9f-4c50-98bc-813db9816512"><br>

***

<img width="1728" alt="7089B374-E68C-4593-A778-2A53F8D60FB4" src="https://github.com/vincentchachere/osticket-prereqs/assets/161680745/f58cd4a0-9004-40c1-9a3a-e7d4a9338641"><br>

***

<img width="1511" alt="isolated" src="https://github.com/vincentchachere/osticket-prereqs/assets/161680745/64898c62-a446-44ba-8b8f-a49278c26c64"><br>

***

### 12. ) Create a Virtual Machine inside the Resource Group

<ins>Wait for your resources to load then</ins>:

- Click: `Go to Resources`

<img width="1511" alt="isolated" src="https://github.com/vincentchachere/osticket-prereqs/assets/161680745/1bd4eec6-f4e9-4329-9b97-722ee8a58024"><br>

***

### 13. ) Create a Virtual Machine inside the Resource Group

<ins>Now we are at our Virtual Machine's 'Overview Page' that is inside our Azure Portal</ins>

- (we are not inside the VM yet)

- This is where you can navigate your VM's information.

- This concludes Part B!

<img width="1511" alt="isolated" src="https://github.com/vincentchachere/osticket-prereqs/assets/161680745/d95f8b93-98e5-4448-89c7-a4e263b349b0"><br>

***

## 📝 Installation Steps - Part C: Remote Desktop into VM, Install Prerequisites, and Install osTicket


### 14.A ) Connect your Virtual Machine to Remote Desktop

- `Copy` your VM's (vm-osticket) `Public IP Address`

- `Verify` your `VM is running` before continuing

- *Scroll down in between images for the next few instructions for Step 14*

<img width="1511" alt="isolated" src="https://github.com/vincentchachere/osticket-prereqs/assets/161680745/c4aa663f-dba3-47cf-8239-255404bd541c"><br>

***

### 14.B ) Connect your Virtual Machine to Remote Desktop

- Press: `Command + Space Bar` at the same time to open up the Spotlight Search, then..

- Type In: `Remote Desktop`

- Now Click: `Microsoft Remote Desktop`

<img width="1511" alt="isolated" src="https://github.com/vincentchachere/osticket-prereqs/assets/161680745/84202fbf-d46c-43f7-a126-837f4b32e1fa"><br>

***

### 14.C ) Connect your Virtual Machine to Remote Desktop

- Click: `Add PC`

<img width="1511" alt="isolated" src="https://github.com/vincentchachere/osticket-prereqs/assets/161680745/013afe59-3d68-4628-b0f3-723c0fc36ad2"><br>

***

### 14.D ) Connect your Virtual Machine to Remote Desktop

- Paste: `vm-osticket's Public IP Address`

- Click: `Add`

<img width="1511" alt="isolated" src="https://github.com/vincentchachere/osticket-prereqs/assets/161680745/1e86b149-9600-4237-8eb8-9fbed507411b"><br>

***

### 15.A ) Connect your Virtual Machine to Remote Desktop

- Righ-Click: Your Remote Desktop Account

- Click: `Connect`

<img width="1511" alt="isolated" src="https://github.com/vincentchachere/osticket-prereqs/assets/161680745/bf3e054f-aa7f-496a-8152-f1159710c834"><br>

***

### 15.B ) Connect your Virtual Machine to Remote Desktop

- `Username:` vincentchachere (whatever you typed in at the beginnning of Part B: Step 9)

- `Password:` *YourPassword* (whatever you typed in at the beginnning of Part B: Step 9)

- Click: `Continue`
 
<img width="1511" alt="isolated" src="https://github.com/vincentchachere/osticket-prereqs/assets/161680745/78160742-2f17-4dc1-be20-d5a70c546110"><br>

***

### 15.C ) Connect your Virtual Machine to Remote Desktop

- *Uncheck: `All Boxes`*

- *Click: `Accept`*

<img width="1511" alt="isolated" src="https://github.com/vincentchachere/osticket-prereqs/assets/161680745/f59877e2-da56-4767-8cef-54cb4d0fdbe9"><br>

***

### 16.A ) Install/Enable IIS in Windows

- Once connected and inside your Virtual Machine we'll need to install IIS by doing the following:

  - Right-Click: `Start` in the bottom left of your screen

  - Select: `Run`

<img width="1511" alt="isolated" src="https://github.com/vincentchachere/osticket-prereqs/assets/161680745/6f279019-c2f3-4446-b4f1-76e5cf798e2b"><br>

***

### 16.B ) Install/Enable IIS in Windows

- Type In: `Control`

- Press: `Enter` or Click: `Ok`

<img width="1511" alt="isolated" src="https://github.com/vincentchachere/osticket-prereqs/assets/161680745/87a7e808-6441-42db-859b-aa78c565d8a1"><br>

***

### 16.C ) Install/Enable IIS in Windows

  - Click: `Programs`

<img width="1511" alt="isolated" src="https://github.com/vincentchachere/osticket-prereqs/assets/161680745/897bb69f-f091-4f03-8c55-3547cf3ad1f1"><br>

***

### 16.D ) Install/Enable IIS in Windows

  - Click: `Turn Windows Features On or Off`

<img width="1511" alt="isolated" src="https://github.com/vincentchachere/osticket-prereqs/assets/161680745/b9beb774-2bc5-4f35-bf61-aaf2e8c52dea"><br>

***

### 16.E ) Install/Enable IIS in Windows
                              
  - Enable: Internet Information Services (IIS)
 
  - Open & Enable: `World Wide Web Services`
    - `Check All Boxes` within this feature's folder

- *scroll down in between images for further instruction*
   
<img width="1511" alt="isolated" src="https://github.com/vincentchachere/osticket-prereqs/assets/161680745/89eb3345-1c42-416f-9ea3-6fb101a9c499"><br>

***

### 16.F ) Install/Enable IIS in Windows

-  While still inside the *World wide Web Service*:

  - Open the `Application Development Features` folder

  - Enable: `CGI`

- *Collapse Application Development Features folder*

<img width="1511" alt="isolated" src="https://github.com/vincentchachere/osticket-prereqs/assets/161680745/4a86fcb4-b2e3-4247-89fa-725b7c4d7583"><br>

***

### 16.G ) Install/Enable IIS in Windows

- Enable: Common HTTP Features

- Within the 'Common HTTP Fetures' feature folder

  - Check: `All Boxes` *(within this feature's folder)*
 
  - Click: 'Ok'

<img width="1511" alt="isolated" src="https://github.com/vincentchachere/osticket-prereqs/assets/161680745/4a756f64-9ba3-45fb-a690-0ddf5bd5b4bd"><br>

***

### 16.H ) Install/Enable IIS in Windows

- Wait for it to load...

<img width="1511" alt="isolated" src="https://github.com/vincentchachere/osticket-prereqs/assets/161680745/81b5957a-ab51-4c47-8e46-91a8d3b3f961"><br>

***

### 16.I ) Install/Enable IIS in Windows

- When that's done Loading Click: `Close`

<img width="1511" alt="isolated" src="https://github.com/vincentchachere/osticket-prereqs/assets/161680745/904c8fec-b77a-4efa-81fa-a62e801dc3fa"><br>

***

<br>

### 17.A ) Open Microsoft Edge to Test IIS

- Open: `Microsoft Edge` Internet Browser

- Click: `Start without your data`

<img width="1511" alt="isolated" src="https://github.com/vincentchachere/osticket-prereqs/assets/161680745/e7c74b77-ca58-4c36-8623-b641438aee10"><br>

***

### 17.B ) Open Microsoft Edge to Test IIS

- Uncheck the Box

- Click: `Continue and Conirm`

<img width="1511" alt="isolated" src="https://github.com/vincentchachere/osticket-prereqs/assets/161680745/80a538a2-5fca-4ffb-b416-85f369c8c3df"><br>

***

### 17.C ) Open Microsoft Edge to Test IIS

- Click: `Continue without this data`

<img width="1511" alt="isolated" src="https://github.com/vincentchachere/osticket-prereqs/assets/161680745/2a8021d3-6634-45de-b25f-d2f63ad50ae7"><br>

***

### 17.D ) Open Microsoft Edge to Test IIS

- Uncheck the Box

- Click: `Confirm and start browsing`

<img width="1511" alt="isolated" src="https://github.com/vincentchachere/osticket-prereqs/assets/161680745/1e5c7aa4-97dd-4c8d-a09d-c9cafddda685"><br>

***

### 17.E ) Open Microsoft Edge to Test IIS

- Type: `127.0.0.1` into the browser

  - If you do not see the image displayed below then try uninstalling and reinstalling IIS

  - *The `How To Uninstall and Reinstall Instructions` are directly underneath the image below.* 

<img width="1511" alt="isolated" src="https://github.com/vincentchachere/osticket-prereqs/assets/161680745/7c2dae78-f8bb-40ba-9f73-b24d60b25c91"><br>

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

<img width="1511" alt="isolated" src="https://github.com/vincentchachere/osticket-prereqs/assets/161680745/7c65e858-f02e-4a8f-91e3-961c718d1956"><br>

***

### 18.B ) Download PHP Manager for IIS

- Click: `Download anyway`

- <ins>Now you can Either:</ins>

  - Wait for it to pop up when its done loading or.. &darr;

  - Click: The `...` Dots in the upper left corner of your screen and Click: `Downloads`

>**Sometimes when the file downloads it does not pop up, so I wanted to show you both ways.**

>**You can also simply go to your `File Explorer` > `Downaloads` > Double-Click: `PHPManagerforIIS_V1.5.0`**

<img width="1511" alt="isolated" src="https://github.com/vincentchachere/osticket-prereqs/assets/161680745/e55e776c-9ea1-491a-9d10-3cd0bc79db5e"><br>

***

### 18.C ) Download PHP Manager for IIS

- Click :`Next`

<img width="1511" alt="isolated" src="https://github.com/vincentchachere/osticket-prereqs/assets/161680745/d259bf88-439b-42cc-9375-166f003d8808"><br>

***

### 18.D ) Download PHP Manager for IIS

- Select: `I Agree`

- Click: `Next`

<img width="1511" alt="isolated" src="https://github.com/vincentchachere/osticket-prereqs/assets/161680745/9199a0ea-972d-455c-9408-5365677ed221"><br>

***

### 18.E ) Download PHP Manager for IIS

- Click: `Close`

<img width="1511" alt="isolated" src="https://github.com/vincentchachere/osticket-prereqs/assets/161680745/ac09a285-6c4a-4ae0-8c33-2098d337d6f6"><br>

***

### 19.A ) Download Rewrite Module

- Double-Click: `rewrite_amd64_en-US.msi`

- Open: The `rewrite_amd64_en-US.msi` file when it pops up

- Check: The Box *'I accpet the terms in the License Agreement'*

- Click: `Install`

<img width="1511" alt="isolated" src="https://github.com/vincentchachere/osticket-prereqs/assets/161680745/3cc3863b-44d7-4b20-b781-71830ae56f1d"><br>

***

### 19.B ) Download Rewrite Module

- Click: `Finish`

<img width="1511" alt="isolated" src="https://github.com/vincentchachere/osticket-prereqs/assets/161680745/f8035ed7-c04b-4425-9044-8a20529b8a89"><br>

***

### 20.A ) Create Directory C:\PHP

- Go To: `File Explorer` > `This PC` > `Windows (C:)` > 

<img width="1511" alt="isolated" src="https://github.com/vincentchachere/osticket-prereqs/assets/161680745/42973b96-7bf7-4e37-b824-6c46ee8d7bdf"><br>

***

### 20.B ) Create Directory C:\PHP

- Right-Click: The `empty space under the files`

- Go To: `New`

- Click: `Folder`

<img width="1511" alt="isolated" src="https://github.com/vincentchachere/osticket-prereqs/assets/161680745/a45390d8-3afe-4c32-b5a6-2a9e939e322f"><br>

***

### 20.C ) Create Directory C:\PHP

- Type In: `PHP`

- Press: `Enter`

<img width="1511" alt="isolated" src="https://github.com/vincentchachere/osticket-prereqs/assets/161680745/166f8e04-71ff-44ef-b2cf-3b9acf3160ea"><br>

***

### 21.A ) Download php-7.3.8 and Unzip it into the Directory (C:\PHP) you just created

- Double-Click: `PHP 7.3.8`

<img width="1511" alt="isolated" src="https://github.com/vincentchachere/osticket-prereqs/assets/161680745/2c5679a1-839f-4ac8-b33a-5e619ca409ba"><br>

***

### 21.B ) Download php-7.3.8 and Unzip it into the Directory (C:\PHP) you just created

- Click : The Download (&darr;) Arrow in the upper right corner

<img width="1511" alt="isolated" src="https://github.com/vincentchachere/osticket-prereqs/assets/161680745/99d3d799-3810-41ba-a13a-546836651291"><br>

***

### 21.C ) Download php-7.3.8 and Unzip it into the Directory (C:\PHP) you just created

- Click: `Download anyway`

- Open: `php.7.3.8`

<img width="1511" alt="isolated" src="https://github.com/vincentchachere/osticket-prereqs/assets/161680745/95210981-7d56-4657-9d4f-9fe10429d6d4"><br>

***

### 21.D ) Download php-7.3.8 and Unzip it into the Directory (C:\PHP) you just created

- Right-Click: `php.7.3.8`

- Click: `Extract All`

<img width="1511" alt="isolated" src="https://github.com/vincentchachere/osticket-prereqs/assets/161680745/fa92591b-55db-4434-a0fc-4cc8823763c8"><br>

***

### 21.E ) Download php-7.3.8 and Unzip it into the Directory (C:\PHP) you just created

- Click: `Browse`

<img width="1511" alt="isolated" src="https://github.com/vincentchachere/osticket-prereqs/assets/161680745/7f688b04-f510-4f57-9749-f8bae9e0a3f3"><br>

***

### 21.F ) Download php-7.3.8 and Unzip it into the Directory (C:\PHP) you just created

- Go To: `This PC` > `Windows (C:)` > `PHP`

<img width="1511" alt="isolated" src="https://github.com/vincentchachere/osticket-prereqs/assets/161680745/fad328b2-3d4e-4668-ad14-920de414b310"><br>

***

### 21.G ) Download php-7.3.8 and Unzip it into the Directory (C:\PHP) you just created

- Click: `select Folder` (*PHP*)

<img width="1511" alt="isolated" src="https://github.com/vincentchachere/osticket-prereqs/assets/161680745/f673ed81-b6f4-4a26-910c-17726df34ec2"><br>

***

### 21.H ) Download php-7.3.8 and Unzip it into the Directory (C:\PHP) you just created

- Click: `Extract`

<img width="1511" alt="isolated" src="https://github.com/vincentchachere/osticket-prereqs/assets/161680745/514000ee-6a7c-4575-b7c6-591381562314"><br>

***

### 22.A ) Check to see the php-7.3.8 made it into the PHP Directory

- Go Back To: `This PC` > `Windows (C:)` > `PHP`

- Double-Click: `PHP`

<img width="1511" alt="isolated" src="https://github.com/vincentchachere/osticket-prereqs/assets/161680745/020501bb-8112-464b-b9ef-7ecb823913f4"><br>

***

### 22.C ) Check to see the php 7.3.8 made it into the PHP Directory

- Now you will see the php.7.3.8 file inside the PHP directory, as seen in the image below.

<img width="1511" alt="isolated" src="https://github.com/vincentchachere/osticket-prereqs/assets/161680745/c6511b61-033a-46ff-9714-50b664e19c73"><br>

***

<br>

### 23.A ) Download VC_redist.x86.exe

- Go To: [Installation Files](https://drive.google.com/drive/u/1/folders/1APMfNyfNzcxZC6EzdaNfdZsUwxWYChf6) and download VC_redist.x86.exe

  - *I will let you do the <ins>downloading</ins> steps on your own now, so that you can learn. Refer to previous steps for instruction (You got this! I believe in you!😁)*

- Check: The `I agree to the license terms and conditions` Box

- Click: `Install`

<img width="1511" alt="isolated" src="https://github.com/vincentchachere/osticket-prereqs/assets/161680745/170a61c1-fe3c-419f-8059-269bf6a5455c"><br>

***

<br>

### 23.B ) Download VC_redist.x86.exe

- Click: `Close` when it is done installing

<img width="1511" alt="isolated" src="https://github.com/vincentchachere/osticket-prereqs/assets/161680745/57eb8907-d6da-4abc-b39b-5d945d62c55f"><br>

***

### 24.A ) Download MySQL 5.5.62

- Go To: [Installation Files](https://drive.google.com/drive/u/1/folders/1APMfNyfNzcxZC6EzdaNfdZsUwxWYChf6) and download MySQL 5.5.62

- <ins>When the pop-up below shows up</ins>:

  - Click: `Next`

<img width="1511" alt="isolated" src="https://github.com/vincentchachere/osticket-prereqs/assets/161680745/44a36637-43cc-4fcb-9d9b-6eb64c4315a4"><br>

***

### 24.B ) Download MySQL 5.5.62

- <ins>When the pop-up below shows up</ins>:

  - Check: The `I accept the terms in the License Agreement` Box

  - Click: `Next`

<img width="1511" alt="isolated" src="https://github.com/vincentchachere/osticket-prereqs/assets/161680745/1a768122-511d-44ef-a428-8a4dce09c2f9"><br>

***

### 24.C ) Download MySQL 5.5.62

- Select: `Typical Setup`

- Click: `Next`

<img width="1511" alt="isolated" src="https://github.com/vincentchachere/osticket-prereqs/assets/161680745/14c18df3-e9ee-4cf9-a0e7-d2631f3beedf"><br>

***

### 24.D ) Download MySQL 5.5.62

- Click: `Install`

<img width="1511" alt="isolated" src="https://github.com/vincentchachere/osticket-prereqs/assets/161680745/f09cc5cc-9262-4951-b2ef-82d39e43ab70"><br>

***

### 24.E ) Download MySQL 5.5.62

- Check: The `Lanuch the MySQL Instance Configuration Wizard` Box

- Click: `Finish`

<img width="1511" alt="isolated" src="https://github.com/vincentchachere/osticket-prereqs/assets/161680745/110fd673-4225-4d28-968b-d4f0535e39b2"><br>

***

### 24.F ) Download MySQL 5.5.62

- Click: `Next`

<img width="1511" alt="isolated" src="https://github.com/vincentchachere/osticket-prereqs/assets/161680745/61f88e18-96bf-4991-9ad1-1222abf6cd00"><br>

***

### 24.G ) Download MySQL 5.5.62

- Select: `Standard Confirguration`

- Click: `Next`

<img width="1511" alt="isolated" src="https://github.com/vincentchachere/osticket-prereqs/assets/161680745/16837f9b-9535-4306-8b45-93a1c984e611"><br>

***

### 24.H ) Download MySQL 5.5.62

- Make sure your screen matches the image below and once you verify that it does..&darr;

- Click: `Next`

<img width="1511" alt="isolated" src="https://github.com/vincentchachere/osticket-prereqs/assets/161680745/bcf52378-fb29-4fe8-8d2a-7ce1657bf457"><br>

***

### 24.I ) Download MySQL 5.5.62

- Type In: `The password you used to log into remote desktop.`

  - Click: `Next`

<img width="1511" alt="isolated" src="https://github.com/vincentchachere/osticket-prereqs/assets/161680745/cec6d46c-46d7-4db1-a897-deee162df7c8"><br>

***

### 24.J ) Download MySQL 5.5.62

- Click : `Finish`

<img width="1511" alt="isolated" src="https://github.com/vincentchachere/osticket-prereqs/assets/161680745/bccc6a00-de77-4266-a7f3-e5c12eb30c1b"><br>

***

### 25.A )  Open IIS as an Administrator and Register PHP from within IIS

- Type: `IIS` into search bar at bottom left of your screen

- Right-Click: `IIS`

- Select: `Run as Administrator`

<img width="1511" alt="isolated" src="https://github.com/vincentchachere/osticket-prereqs/assets/161680745/d41680a0-721e-4b3c-96ce-5310df21da38"><br>

***

### 25.B )  Open IIS as an Administrator and Register PHP from within IIS

- Double-Click: `PHP Manager`

<img width="1511" alt="isolated" src="https://github.com/vincentchachere/osticket-prereqs/assets/161680745/eb75fbaa-0d3c-45f1-b064-d965ecc36fd9"><br>

***

### 25.C )  Open IIS as an Administrator and Register PHP from within IIS

- Click: `Register vew PHP version`

- Click: the `'...' Box` (three dots box) that is next to the search bar

<img width="1511" alt="isolated" src="https://github.com/vincentchachere/osticket-prereqs/assets/161680745/b91fd8b3-f3d3-4aa4-b651-ddefd79c1200"><br>

***

### 25.D )  Open IIS as an Administrator and Register PHP from within IIS

- Go To: `This PC` > `Windows (C:)` > `PHP` > `php-cgi` > `Open`

<img width="1511" alt="isolated" src="https://github.com/vincentchachere/osticket-prereqs/assets/161680745/595705b3-fb62-4838-bfa2-a017cf9e3587"><br>

***

### 25.E )  Open IIS as an Administrator and Register PHP from within IIS

- Click: `Ok`

<img width="1511" alt="isolated" src="https://github.com/vincentchachere/osticket-prereqs/assets/161680745/de874438-082d-4249-8aec-b33890da7f7a"><br>

***

### 26.A )  Go To: `Home` screen of <ins>PHP Manager</ins> and Restart IIS

- Click: The `Home` icon in the upper right corner of IIS Window

<img width="1511" alt="isolated" src="https://github.com/vincentchachere/osticket-prereqs/assets/161680745/7b3dff50-a9bc-4a8f-a42e-a06219848b34"><br>

***

### 26.B )  Go To: `Home` screen of IIS Manager and Restart IIS

- Click: `Restart`

<img width="1511" alt="isolated" src="https://github.com/vincentchachere/osticket-prereqs/assets/161680745/51ba028c-76de-49ca-b469-d4f4a1e1af4b"><br>

***

### 27.A ) Install osTicket v1.15.8

- Go To: [Installation Files](https://drive.google.com/drive/u/1/folders/1APMfNyfNzcxZC6EzdaNfdZsUwxWYChf6)

- Download: `osTicket`

- <ins>Once osTicket downloads do the following</ins>:

  - Go To: `Downloads` inside of `File Explorer`

  - Double-Click: `osTicket`

<img width="1511" alt="isolated" src="https://github.com/vincentchachere/osticket-prereqs/assets/161680745/0dc37056-7f73-48c3-b59a-9fecf35ccf85"><br>

***

### 27.B ) Install osTicket v1.15.8

- <ins>Open a second `File Explorer` by</ins>:

  - Right-Click: `File Explorer` Icon
 
  - Select: `File Explorer`

<img width="1511" alt="isolated" src="https://github.com/vincentchachere/osticket-prereqs/assets/161680745/4d13e47a-cc82-40c1-84ed-a974ebd35c9f"><br>

***

### 27.C ) Install osTicket v1.15.8

- When you open the second File Explorer:

 - Go To: 'This PC' > 'Windows (C:)' > 'inetpub' > `wwwroot`

- <ins>Drag and Drop `upload` into</ins>:

  - 'This PC' > 'Windows (C:)' > 'inetpub' > `wwwroot`

<img width="1511" alt="isolated" src="https://github.com/vincentchachere/osticket-prereqs/assets/161680745/26103641-5c8b-421a-9b6b-9e50408a1e7b"><br>

***

### 27.D ) Install osTicket v1.15.8

- Right-Click: `upload` *(the 'upload' that is in the new File Explorer you just opened)*

- Click: `Rename`

<img width="1511" alt="isolated" src="https://github.com/vincentchachere/osticket-prereqs/assets/161680745/f110c0e8-4cbd-47d3-9b93-a1c3bfecc5c6"><br>

***

### 27.E ) Install osTicket v1.15.8

- Type In: `osTicket`

- Press: `Enter`

  - *Spell it exactly like: `osTicket` (with a capital `T` and lowercase everything else)*

<img width="1511" alt="isolated" src="https://github.com/vincentchachere/osticket-prereqs/assets/161680745/ff11a56c-aebd-4743-8b14-9827ae363ae7"><br>

***

### 28.A ) Refresh the osTicket site in your browser and observe the changes

- Open: `IIS` *as an Administrator*

<img width="1511" alt="isolated" src="https://github.com/vincentchachere/osticket-prereqs/assets/161680745/6f65cdff-c286-44e0-91fe-6d788c6fc734"><br>

***

### 28.B ) Refresh the osTicket site in your browser and observe the changes

- Click: `Restart`

<img width="1511" alt="isolated" src="https://github.com/vincentchachere/osticket-prereqs/assets/161680745/da2870cf-1b2e-496f-9694-16f041454aed"><br>

***

### 28.C ) Refresh the osTicket site in your browser and observe the changes

- Go to: `sites` > `Default` > `osTicket`

- On the Right, Click: `Browse*: 80`

<img width="1511" alt="isolated" src="https://github.com/vincentchachere/osticket-prereqs/assets/161680745/085d2c71-60cb-48ff-a816-acf9553a9d6f"><br>

***

### 29.A ) Enable Extensions for osTicket

- Go to: `sites` > `Default` > `osTicket`

- Double-Click: `PHP Manager`

<img width="1511" alt="isolated" src="https://github.com/vincentchachere/osticket-prereqs/assets/161680745/44cb93d6-1662-40a1-ad77-ccd7b721b46b"><br>

***

### 29.B ) Enable Extensions for osTicket

- Click: `Enable or Disable Extensions`

<img width="1511" alt="isolated" src="https://github.com/vincentchachere/osticket-prereqs/assets/161680745/fd5e93a8-cae4-4f2f-accb-1d39c99d1aef"><br>

***

### 29.C ) Enable Extensions for osTicket

- Right-Click: `php_imap.dll`

- Click: `Enable`

<img width="1511" alt="isolated" src="https://github.com/vincentchachere/osticket-prereqs/assets/161680745/b85f7116-d50e-4593-a8d8-0a9f7fd2fb69"><br>

***

### 29.D ) Enable Extensions for osTicket

- Right-Click: `php_intel.dll`

- Click: `Enable`

<img width="1511" alt="isolated" src="https://github.com/vincentchachere/osticket-prereqs/assets/161680745/97575f63-2d21-4113-8012-852224fe0ffb"><br>

***

### 29.E ) Enable Extensions for osTicket

- Right-Click: `php_opache.dll`

- Click: `Enable`

<img width="1511" alt="isolated" src="https://github.com/vincentchachere/osticket-prereqs/assets/161680745/748526b0-3631-4115-8b09-2fbe5c796a23"><br>

### 29.F ) Enable Extensions for osTicket

<ins>Verify all your extensions were enabled</ins>

- You should see the 3 following extensions in the 'enabled' section:

  - php_imap.dll
 
  - php_intel.dll

  - php_opache.dll

- Click: The `osTicket` folder to the left in your 'Connections' section.

<img width="1511" alt="isolated" src="https://github.com/vincentchachere/osticket-prereqs/assets/161680745/d08c24c3-9f19-44bc-a6e7-aebecb62886a"><br>

***

### 30. ) Enable Extensions for osTicket

<ins>Restart the osTicket in your browser and observe the changes</ins>

- Click: `Refresh` that is in your `IIS Manager`

- Click: `Browse*:80 (http)`

- *observe the changes*

<img width="1511" alt="isolated" src="https://github.com/vincentchachere/osticket-prereqs/assets/161680745/1ae36821-513d-49e6-84ec-ab5f87b4b0a4"><br>

***

### 31.A ) Rename: ost-config.php

- Open: `File Explorer`

- Go To: `This PC` > `Windows (C:)` > `inetpub` > `wwwroot`

- Double-Click: `osTicket`

<img width="1511" alt="isolated" src="https://github.com/vincentchachere/osticket-prereqs/assets/161680745/0c3e6b54-eeeb-4a51-8707-90e7c4b824fa"><br>

***

### 31.B ) Rename: ost-config.php

- Double-Click: `include`

<img width="1511" alt="isolated" src="https://github.com/vincentchachere/osticket-prereqs/assets/161680745/84575042-8a22-469d-b642-587861c163e8"><br>

***

### 31.C ) Rename: ost-config.php

- Scroll: *`all the way down`*

- Right-Click: `ost-sampleconfig.php`

  - Click: `Rename`

  - Rename: `ost-sampleconfig.php`
 
  - To: `ost-config.php`
 
  - Press: `Enter` when done typing in the name

<img width="1511" alt="isolated" src="https://github.com/vincentchachere/osticket-prereqs/assets/161680745/8531889f-57a2-4d19-8a6b-67c650e109e4">

***

### 32.A ) Assign Permissions To: ost-config.php

- Right-Click: `ost-config.php`

- Click: `Properties`

<img width="1511" alt="isolated" src="https://github.com/vincentchachere/osticket-prereqs/assets/161680745/6775fcf0-4d0c-45e1-a724-9dc414d29311"><br>

***

### 32.B ) Assign Permissions To: ost-config.php

- Click: `Security`

- Click: `Advanced`

- Select: `Disable Inheritance`

- Click: `Remove all inherited permissions from this object.`

<img width="1511" alt="isolated" src="https://github.com/vincentchachere/osticket-prereqs/assets/161680745/164837d4-9e9d-4f02-8daf-185919f56422"><br>

***

### 32.C ) Assign Permissions To: ost-config.php

- Click: `Add` > `Select a principal` > Type In: `Everyone` > Click: `Check Names`

  - *It should be underlined after you click 'Check Names'*

- Click: `Ok`

<img width="1511" alt="isolated" src="https://github.com/vincentchachere/osticket-prereqs/assets/161680745/3986865e-f77e-4134-98bb-1dea6c6a690b"><br>

***

### 32.C ) Assign Permissions To: ost-config.php

- Select: `Full Control` *(make sure all boxes are checked as seen in the image below)*

- Click: `Ok`

- Click: `Ok`

<img width="1511" alt="isolated" src="https://github.com/vincentchachere/osticket-prereqs/assets/161680745/843fd85c-e38b-43b5-b66e-24e5e14ae378"><br>

***

### 33. ) Restart IIS Manager and Continue Setting Up osTicket in the Browser

- Click: `Restart`

- Click: `Continue` 

<img width="1511" alt="isolated" src="https://github.com/vincentchachere/osticket-prereqs/assets/161680745/45d6f331-16d8-4199-9b81-e03dc41b38e2"><br>

***

### 34.A ) Continue Setting up osTicket in the browser

- Helpdesk Name: `Helpdesk`

- Default Email: `yourfirstname@helper.com`

- First Name: *AnythingYouWant* *(just remember it)*

- Last Name: *AnythingYouWant* *(just remember it)*

- Email Address: `yourfirstname@gmail.com`
  - *AnythingYouWant* *(just remember it)*

- Username: *AnythingYouWant* *(just remember it)*

- Password: *AnythingYouWant* *(just remember it)*

<img width="1511" alt="isolated" src="https://github.com/vincentchachere/osticket-prereqs/assets/161680745/861e533c-76c0-43b3-b1c7-5ea17d1be6f8"><br>

***

### 35.A ) Download and Install HeidiSQL

- Go To: [Installation Files](https://drive.google.com/drive/u/1/folders/1APMfNyfNzcxZC6EzdaNfdZsUwxWYChf6)

- Download and Install: `HiediSQL`

- Open: `HiediSQL`

- Select: The `I accept the agreement` Circle

- Click: `Next`

<img width="1511" alt="isolated" src="https://github.com/vincentchachere/osticket-prereqs/assets/161680745/4ed4fec3-24b4-4e5c-9b0a-90308fef3a65"><br>

***

### 35.B ) Download and Install HeidiSQL

- Click: `Next`

<img width="1511" alt="isolated" src="https://github.com/vincentchachere/osticket-prereqs/assets/161680745/5496fa65-221c-40cf-b54f-47d21dc7a73c"><br>

***

### 35.C ) Download and Install HeidiSQL

- Click: `Next`

<img width="1511" alt="isolated" src="https://github.com/vincentchachere/osticket-prereqs/assets/161680745/7474f214-7c07-400a-835c-fd9818e144b9"><br>

***

### 35.D ) Download and Install HeidiSQL

- Click: `Next`

<img width="1511" alt="isolated" src="https://github.com/vincentchachere/osticket-prereqs/assets/161680745/6db50674-e510-42ea-9be7-f8536b58c51e"><br>

***

### 35.E ) Download and Install HeidiSQL

- Click: `Install`

<img width="1511" alt="isolated" src="https://github.com/vincentchachere/osticket-prereqs/assets/161680745/df2466bc-7fa9-4d01-b963-ea5f82a285a5"><br>

***

### 35.F ) Download and Install HeidiSQL

- Click: `Finish`

<img width="1511" alt="isolated" src="https://github.com/vincentchachere/osticket-prereqs/assets/161680745/2e10c9ca-7ae5-4ba3-8d1e-2df63eb17c28"><br>

***

### 35.G ) Download and Install HeidiSQL

- Click: `Skip`

<img width="1511" alt="isolated" src="https://github.com/vincentchachere/osticket-prereqs/assets/161680745/fc4d90e6-dce0-4855-9083-e5eb1635214b"><br>

***

### 35.H ) Download and Install HeidiSQL

- User: `root`

- Password: `The one you created at Step 34.A`

- Click: `Open` to connect to session

<img width="1511" alt="isolated" src="https://github.com/vincentchachere/osticket-prereqs/assets/161680745/24c03e10-8937-4a5d-b964-d56c2450975b"><br>

***

### 35.I ) Create a Database for osTicket called `osTicket`

- Right-Click: `Unamed` > Click: `Create new` > Click: `Database`

<img width="1511" alt="isolated" src="https://github.com/vincentchachere/osticket-prereqs/assets/161680745/d70e6f94-2a42-4e7e-b380-b907fb3f964f"><br>

***

### 35.J ) Create a Database for osTicket called `osTicket`

- Type In: `osTicket`

- Click: `Ok`

<img width="1511" alt="isolated" src="https://github.com/vincentchachere/osticket-prereqs/assets/161680745/9ffb84cf-ef45-45f0-8240-a4608fb136a2"><br>

***

### 36.A ) Continue Setting up osTicket in the browser

- MySQL Database: `osTicket`

- MySQL Username: `root`

- MySQL Password: *`The one you created at Step 34.A and the one you used at Step 35.H`*

- Click: `Install`

<img width="1511" alt="isolated" src="https://github.com/vincentchachere/osticket-prereqs/assets/161680745/cc7a2b9d-b203-4bfb-a2fa-e819df565d98"><br>

***

### 36.B ) Congratulations! Hopefully it is installed with no errors, but we are not finished just yet!

- *Scroll down for further instruction*

<img width="1511" alt="isolated" src="https://github.com/vincentchachere/osticket-prereqs/assets/161680745/7f4988fb-ea09-4432-b689-dedfe5b96449"><br>

***

### 37. ) Browse to your help desk login page: http://localhost/osTicket/scp/login.php

<ins>Before logging in we need to do 2 Things</ins>:

- Clean Up Resources

  - 1st Thing - Delete: c:\inept\wwwroot\osTicket\\*`setup`*

- Change File Permissions

  - 2nd Thing - Set Permissions to `Read` <ins>only</ins> for: This PC > inetpub > wwwroot > osTicket > include > *`ost-config.php`*

  - *Scroll down for further instruction*

<img width="1511" alt="isolated" src="https://github.com/vincentchachere/osticket-prereqs/assets/161680745/94a00827-144e-435d-abaa-f2b052d6cb74"><br>

***

### 38.A ) Clean Up Resources

<ins>1st Thing - Delete: c:\inept\wwwroot\osTicket\\*'setup'*</ins>

  - ONLY DELETE THE `setup` PART - NOT THE WHOLE THING

  - *scroll down for the 2nd Thing*

<img width="1511" alt="isolated" src="https://github.com/vincentchachere/osticket-prereqs/assets/161680745/1fcc1edd-c8da-406e-aaee-495acdd2ab82"><br>

***

### 38.B ) Change File Permissions

<ins>2nd Thing - Set Permissions to 'Read' <ins>only</ins> for *'ost-config.php'*</ins>

- File Explorer: This PC > inetpub > wwwroot > osTicket > include > *`ost-config.php`*

  - Right-Click: *`ost-config.php`*
 
  - Select: `Properties`

<img width="1511" alt="isolated" src="https://github.com/vincentchachere/osticket-prereqs/assets/161680745/a532e9ec-56e1-44a6-a8e1-7e02bf41ef61"><br>

***

### 38.C ) Change File Permissions

<ins>2nd Thing - Set Permissions to 'Read' <ins>only</ins> for *'ost-config.php'*</ins>

- Go To: `Security` > `Advanced` > `Edit`

<img width="1511" alt="isolated" src="https://github.com/vincentchachere/osticket-prereqs/assets/161680745/251d87d6-5fec-4133-a470-113d61ee3905"><br>

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

<img width="1511" alt="isolated" src="https://github.com/vincentchachere/osticket-prereqs/assets/161680745/bd4424a4-45d3-4b57-8190-7c900d90c374"><br>

***

### 39.A ) Login To: http://localhost/osTicket/scp/login.php

- Username: *`The one you created at Step 34.A and the one you used at Step 35.H`*

- Password: *`The one you created at Step 34.A and the one you used at Step 35.H`*

<img width="1511" alt="isolated" src="https://github.com/vincentchachere/osticket-prereqs/assets/161680745/1b7c8e91-5375-40d9-90c2-45c2fcf7aef1"><br>

***

### 39.B ) Now you are successfully inside osTicket! Congrats!

<img width="1511" alt="isolated" src="https://github.com/vincentchachere/osticket-prereqs/assets/161680745/ef1ee657-b978-4494-acb7-7a4e3585acca"><br>

***

### 40. ) End Users osTicket URL:

- http://localhost/osTicket/ 

<img width="1511" alt="isolated" src="https://github.com/vincentchachere/osticket-prereqs/assets/161680745/e5bb86f6-de48-47f3-bcb5-97cbb620e6d8"><br>

***
