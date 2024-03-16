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

__________________________________________________________________________________________________<br>

## 📝 Installation Steps - Part A: Create a Resource Group

### 1. ) Starting at the 'Home' screen in your Microsoft Azure Portal

- Click: the `Resource Groups` icon that's already on your home screen

- or..

- Search: `Resource Groups` and click that one (They do the same thing)

<img width="1511" alt="isolated" src="https://github.com/vincentchachere/osticket-prereqs/assets/161680745/d273a110-a34c-4707-8a06-058d12c11cc5"><br>

***

### 2. ) Click `Create` to start your Resource Group

- Or..

- You can click the blue 'Create' in the middle of the screen as well, and it will take you to the same place.

<img width="1511" alt="isolated" src="https://github.com/vincentchachere/osticket-prereqs/assets/161680745/56fec2c9-0ba3-4e35-8c26-6bc6e7e6313b"><br>

***

### 3. ) Next, we'll input the following:

- Resource Group Name: `RG-osTicket`

- Region: `(US) West US 3`

- *Scroll Down*

 >**ATTENTION: Double check spelling when creating anything (resource groups, virtual machines, etc.) or you will have to delete all your work and start over, because the information you input will NOT be able to be able to be edited once it's created (name, region, etc.)**

<img width="1511" alt="E2C30B0C-FA81-4329-8F23-DBB018C41018" src="https://github.com/vincentchachere/osticket-prereqs/assets/161680745/4829d10a-d483-4c28-93a1-64034a6e0cf3"><br>

***

## 4. ) Now, let's click `Review + Create`

- Dont worry about the 'Tags' section, we don't need that part for this lab.

- The 'Tags' section is used for organizational purposes.

<img width="1511" alt="F462BC66-31ED-444E-A61B-CD02C75151FD" src="https://github.com/vincentchachere/osticket-prereqs/assets/161680745/22252a11-ece8-4e38-873c-f6faf00efe29"><br>

 >**NOTE: We have NOT finished creating the resource group yet by clicking 'Review + Create'. Microsoft Azure let's you double check (review) the information you input before finalizing (creating) your resource group. It also does this for virtual machines, so make it a habit to double check the information you type in, so that you don't have to erase everything you end up creating, because of one wrong letter.**

***

## 5. ) Finally, we review and create!

- Look over the resource rroup rnformation.

- `Verify` your `Information`

- Click `Create` to bring alive your first resource group!

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

__________________________________________________________________________________________________<br>

## 📝 Installation Steps - Part B: Create a `Virtual Machine`

### 7. ) Now, for this second part we will create a 'Virtual Machine' inside the resource group we just created.

- `Search:` Virtual Machine

- `Click:` Virtual Machine

<img width="1511" alt="isolated" src="https://github.com/vincentchachere/osticket-prereqs/assets/161680745/f81d1869-9805-40b1-b4b9-76aa85c0f751"><br>

***

### 8. ) Click one of the `Create` buttons to start creating your Virtual Machine

<img width="1509" alt="3C89D03C-0D84-4484-BFD6-79D2FBDF9012" src="https://github.com/vincentchachere/osticket-prereqs/assets/161680745/d2a8f586-58ac-4bea-99e8-919410d8d839"><br>

 >**Note: This is called your 'Virtual Machine Default Directory'**

***

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

### 10. ) As before, we will fill in the following:

- Size: `Standard_D45_v3 - 4 vcpus, 16 GiB memory ($140.16/month)`

- `Username:` vincentchachere (this can be whatever your heart desires)

- `Password:` whatever-you-want (Just remember it!)

- Public Inbound Ports: `Allow Selected Ports`

- Select Inbound Ports: `RDP (3389)`

- *`Check the Box`*

- Click: `Review and Create`

<img width="1511" alt="isolated" src="https://github.com/vincentchachere/osticket-prereqs/assets/161680745/d25401ce-e384-4511-a592-9747b8bc9be9"><br>

***

### 11. ) `Review` and `Create` your Virtual Machine!

<img width="1511" alt="isolated" src="https://github.com/vincentchachere/osticket-prereqs/assets/161680745/bd8c8d4b-ab9f-4c50-98bc-813db9816512"><br>

***

<img width="1728" alt="7089B374-E68C-4593-A778-2A53F8D60FB4" src="https://github.com/vincentchachere/osticket-prereqs/assets/161680745/f58cd4a0-9004-40c1-9a3a-e7d4a9338641"><br>

***

<img width="1511" alt="isolated" src="https://github.com/vincentchachere/osticket-prereqs/assets/161680745/64898c62-a446-44ba-8b8f-a49278c26c64"><br>

***

### 12. ) Wait for your Virtual Machine to Load and Go to your New Resource group

- Wait for your resources to load then..&darr;

- Click: `Go to Resources`

<img width="1511" alt="isolated" src="https://github.com/vincentchachere/osticket-prereqs/assets/161680745/1bd4eec6-f4e9-4329-9b97-722ee8a58024"><br>

***

### 13. ) Now we are at our Virtual Machine's 'Overview Page' that is inside our Azure Portal

- (we are not inside the VM yet)

- This is where you can navigate your VM's information.

- This concludes Part B!

<img width="1511" alt="isolated" src="https://github.com/vincentchachere/osticket-prereqs/assets/161680745/d95f8b93-98e5-4448-89c7-a4e263b349b0"><br>

__________________________________________________________________________________________________<br>

## 📝 Installation Steps - Part C: Remote Desktop into VM, Install Prerequisites, and Install osTicket


### 14.A ) Connect your Virtual Machine to Remote Desktop by doing the follwing:

- `Copy` your VM's (vm-osticket) `Public IP Address`

- `Verify` your `VM is running` before continuing

- *Scroll down in between images for the next few instructions for Step 14*

<img width="1511" alt="isolated" src="https://github.com/vincentchachere/osticket-prereqs/assets/161680745/c4aa663f-dba3-47cf-8239-255404bd541c"><br>

***

### 14.B ) Connect your Virtual Machine to Remote Desktop by doing the follwing:

- Press: `Command + Space Bar` at the same time to open up the Spotlight Search, then..

- Type In: `Remote Desktop`

- Now Click: `Microsoft Remote Desktop`

<img width="1511" alt="isolated" src="https://github.com/vincentchachere/osticket-prereqs/assets/161680745/84202fbf-d46c-43f7-a126-837f4b32e1fa"><br>

***

### 14.C ) Connect your Virtual Machine to Remote Desktop by doing the follwing:

- Click: `Add PC`

<img width="1511" alt="isolated" src="https://github.com/vincentchachere/osticket-prereqs/assets/161680745/013afe59-3d68-4628-b0f3-723c0fc36ad2"><br>

***

### 14.D ) Connect your Virtual Machine to Remote Desktop by doing the follwing:

- Paste: `vm-osticket's Public IP Address`

- Click: `Add`

<img width="1511" alt="isolated" src="https://github.com/vincentchachere/osticket-prereqs/assets/161680745/1e86b149-9600-4237-8eb8-9fbed507411b"><br>

***

### 15.A ) Login into Virtual Machine

- Righ-Click: Your Remote Desktop Account

- Click: `Connect`

<img width="1511" alt="isolated" src="https://github.com/vincentchachere/osticket-prereqs/assets/161680745/bf3e054f-aa7f-496a-8152-f1159710c834"><br>

***

### 15.B ) Login into Virtual Machine

- `Username:` vincentchachere (whatever you typed in at the beginnning of Part B: Step 9)

- `Password:` *YourPassword* (whatever you typed in at the beginnning of Part B: Step 9)

- Click: `Continue`
 
<img width="1511" alt="isolated" src="https://github.com/vincentchachere/osticket-prereqs/assets/161680745/78160742-2f17-4dc1-be20-d5a70c546110"><br>

***

### 15.C ) Login into Virtual Machine

- *Uncheck: `All Boxes`*

- *Click: `Accept`*

<img width="1511" alt="isolated" src="https://github.com/vincentchachere/osticket-prereqs/assets/161680745/f59877e2-da56-4767-8cef-54cb4d0fdbe9"><br>

***

### 16.A ) Install IIS

- Once connected and inside your Virtual Machine we'll need to install IIS by doing the following:

  - Right-Click: `Start` in the bottom left of your screen

  - Select: `Run`

<img width="1511" alt="isolated" src="https://github.com/vincentchachere/osticket-prereqs/assets/161680745/d0a45cc6-d839-4c06-95f2-32ae350ce719"><br>

***

### 16.B ) Install IIS

- Type In: `Control`

- Press: `Enter` or Click: `Ok`

<img width="1511" alt="isolated" src="https://github.com/vincentchachere/osticket-prereqs/assets/161680745/a55cb772-6e1e-406e-b6cf-e92c24bb8742"><br>

***

### 16.C ) Install IIS

  - Click: `Programs`

<img width="1511" alt="isolated" src="https://github.com/vincentchachere/osticket-prereqs/assets/161680745/4681b035-50c5-4d6c-92d1-348a05252dbd"><br>

***

### 16.D ) Install IIS

  - Click: `Turn Windows Features On or Off`

<img width="1511" alt="isolated" src="https://github.com/vincentchachere/osticket-prereqs/assets/161680745/9df9fab4-a98c-4163-b863-4a844660e08a"><br>

***

### 16.E ) Install IIS
                              
  - Enable: Internet Information Services (IIS)
 
  - Open & Enable: `World Wide Web Services`
    - `Check All Boxes` within this feature's folder

- *scroll down in between images for further instruction*
   
<img width="1511" alt="isolated" src="https://github.com/vincentchachere/osticket-prereqs/assets/161680745/8f66567f-2ab1-4ffe-a2b3-949d5d06bc35"><br>

***

### 16.F ) Install IIS

-  While still inside the *World wide Web Service*:

  - Open the `Application Development Features` folder

  - Enable: `CGI`

- *Collapse Application Development Features folder*

<img width="1511" alt="isolated" src="https://github.com/vincentchachere/osticket-prereqs/assets/161680745/bf191a8d-3aef-4a00-8076-63c39a010ef7"><br>

***

### 16.G ) Install IIS

- Enable: Common HTTP Features

- Within the 'Common HTTP Fetures' feature folder

  - Check: `All Boxes` *(within this feature's folder)*
 
  - Click: 'Ok'

<img width="1511" alt="isolated" src="https://github.com/vincentchachere/osticket-prereqs/assets/161680745/f815d194-ed55-4989-9663-638c95091f25"><br>

***

### 16.H ) Install IIS

- Wait for it to load...

<img width="1511" alt="isolated" src="https://github.com/vincentchachere/osticket-prereqs/assets/161680745/94763f83-0b52-491c-927e-5f27e77a41c5"><br>

***

### 16.I ) Install IIS

- When that's done Loading Click: `Close`

<img width="1511" alt="isolated" src="https://github.com/vincentchachere/osticket-prereqs/assets/161680745/b360cb70-7b73-4879-bb17-614ac2dd9db8"><br>

***

<br>

### 17.A ) Test IIS by doing the following:

- Open: `Microsoft Edge` Internet Browser

- Click: `Start without your data`

<img width="1511" alt="isolated" src="https://github.com/vincentchachere/osticket-prereqs/assets/161680745/ea858b1f-37ad-43d0-985e-0a8dd73e1fd8"><br>

***

### 17.B ) Test IIS by doing the following:

- Uncheck the Box

- Click: `Continue and Conirm`

<img width="1511" alt="isolated" src="https://github.com/vincentchachere/osticket-prereqs/assets/161680745/6528279d-d330-419b-980b-9175825edb33"><br>

***

### 17.C ) Test IIS by doing the following:

- Click: `Continue without this data`

<img width="1511" alt="isolated" src="https://github.com/vincentchachere/osticket-prereqs/assets/161680745/344afc0a-86c7-4f84-89a1-e0af3e282cb1"><br>

***

### 17.D )Test IIS by doing the following:

- Uncheck the Box

- Click: `Confirm and start browsing`

<img width="1511" alt="isolated" src="https://github.com/vincentchachere/osticket-prereqs/assets/161680745/1d583dcd-b755-4aa0-b1cd-2f02970189c9"><br>

***

### 17.E ) Now finally, Test IIS by doing the following:

- Type: `127.0.0.1` into the browser

  - If you do not see the image displayed below then try uninstalling and reinstalling IIS

  - *The `How To Uninstall and Reinstall Instructions` are directly underneath the image below.* 

<img width="1511" alt="isolated" src="https://github.com/vincentchachere/osticket-prereqs/assets/161680745/b20ecb45-f3df-49b4-9a6e-34c254557dde"><br>

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

- Open: [Installation Files](https://drive.google.com/drive/u/1/folders/1APMfNyfNzcxZC6EzdaNfdZsUwxWYChf6) into a seperate tab, so that you can easily access them throught out this lab.

  - Double-Click: `PHP Manager`

  - Click: The `...` Dots in the upper right of your screen next to the 'Share' button

  - Click: `Open in new window`

  - *Downloading it this way is the only way I've found where it does not take so long, and it downloads the first time instead of having to do multiple attempts.* 

<img width="1511" alt="isolated" src="https://github.com/vincentchachere/osticket-prereqs/assets/161680745/7f57f0c7-69cc-4497-b21c-64e7668b48e7"><br>

***

### 18.B ) Download PHP Manager for IIS

- Click: `Download anyway`

- <ins>Now you can Either:</ins>

  - Wait for it to pop up when its done loading or.. &darr;

  - Click: The `...` Dots in the upper left corner of your screen and Click: `Downloads`

>**Sometimes when the file downloads it does not pop up, so I wanted to show you both ways.**

>**You can also simply go to your `File Explorer` > `Downaloads` > `Double-Click: `PHPManagerforIIS_V1.5.0`**

<img width="1511" alt="isolated" src="https://github.com/vincentchachere/osticket-prereqs/assets/161680745/c96e4e2a-37a3-4f90-aa29-118c9d8a468a"><br>

***

### 18.C ) Download PHP Manager for IIS

- Click :`Next`

<img width="1511" alt="isolated" src="https://github.com/vincentchachere/osticket-prereqs/assets/161680745/ccdfcdd2-6a67-453d-bfc1-fb05da1fff5f"><br>

***

### 18.D ) Download PHP Manager for IIS

- Select: `I Agree`

- Click: `Next`

<img width="1511" alt="isolated" src="https://github.com/vincentchachere/osticket-prereqs/assets/161680745/80a9a97e-28f0-4100-a02e-4542c4c4aa38"><br>

***

### 18.E ) Download PHP Manager for IIS

- Click: `Close`

<img width="1511" alt="isolated" src="https://github.com/vincentchachere/osticket-prereqs/assets/161680745/9132b29d-2fde-4197-b823-40e6d9a09235"><br>

***

### 19.A ) Download Rewrite Module

- Double-Click: `rewrite_amd64_en-US.msi`

- Open: The `rewrite_amd64_en-US.msi` file when it pops up

- Check: The Box *'I accpet the terms in the License Agreement'*

- Click: `Install`

<img width="1511" alt="isolated" src="https://github.com/vincentchachere/osticket-prereqs/assets/161680745/721490cc-e27f-4d47-a85b-97de8dc643c6"><br>

***

### 19.B ) Download Rewrite Module

- Click: `Finish`

<img width="1511" alt="isolated" src="https://github.com/vincentchachere/osticket-prereqs/assets/161680745/c71aa5ef-fc0f-4550-a18b-23afcd989151"><br>

***

### 20.A ) Create Directory C:\PHP

- Go To: `File Explorer` > `This PC` > `Windows (C:)` > 

<img width="1511" alt="isolated" src="https://github.com/vincentchachere/osticket-prereqs/assets/161680745/b5e48dce-2671-4b95-af09-fb3ea60cf82a"><br>

***

### 20.B ) Create Directory C:\PHP

- Right-Click: The `empty space under the files`

- Go To: `New`

- Click: `Folder`

<img width="1511" alt="isolated" src="https://github.com/vincentchachere/osticket-prereqs/assets/161680745/20c4cc4d-c381-48b9-bebc-cb61f5cbea52"><br>

***

### 20.B ) Create Directory C:\PHP

- Type In: `PHP`

- Press: `Enter`

<img width="1511" alt="isolated" src="https://github.com/vincentchachere/osticket-prereqs/assets/161680745/166f8e04-71ff-44ef-b2cf-3b9acf3160ea"><br>

***

### 21.A ) Download php-7.3.8 and Unzip it into the Directory (C:\PHP) you just created

- Double-Click: `PHP 7.3.8`

<img width="1511" alt="isolated" src="https://github.com/vincentchachere/osticket-prereqs/assets/161680745/8c4010c5-b21c-43a4-97e2-1f4dcd78e624"><br>

***

### 21.B ) Download php-7.3.8 and Unzip it into the Directory (C:\PHP) you just created

- Click : The Download (&darr;) Arrow in the upper right corner

<img width="1511" alt="isolated" src="https://github.com/vincentchachere/osticket-prereqs/assets/161680745/243565ac-e227-44e9-b340-d7d9b0eb8648"><br>

***

### 21.C ) Download php-7.3.8 and Unzip it into the Directory (C:\PHP) you just created

- Click: `Download anyway`

- Open: `php.7.3.8`

<img width="1511" alt="isolated" src="https://github.com/vincentchachere/osticket-prereqs/assets/161680745/64200858-d6a0-40a8-85af-7b0e4f1fb000"><br>

***

### 21.D ) Download php-7.3.8 and Unzip it into the Directory (C:\PHP) you just created

- Right-Click: `php.7.3.8`

- Click: `Extract All`

<img width="1511" alt="isolated" src="https://github.com/vincentchachere/osticket-prereqs/assets/161680745/56e6545a-48d5-45df-b861-fd6624203d5b"><br>

***

### 21.E ) Download php-7.3.8 and Unzip it into the Directory (C:\PHP) you just created

- Click: `Browse`

<img width="1511" alt="isolated" src="https://github.com/vincentchachere/osticket-prereqs/assets/161680745/4653e904-d198-4b43-b88e-01d3c322a9f0"><br>

***

### 21.F ) Download php-7.3.8 and Unzip it into the Directory (C:\PHP) you just created

- Go To: `This PC` > `Windows (C:)` > `PHP`

<img width="1511" alt="isolated" src="https://github.com/vincentchachere/osticket-prereqs/assets/161680745/26564e01-7ad7-44d5-a27e-32877be87ab4"><br>

***

### 21.G ) Download php-7.3.8 and Unzip it into the Directory (C:\PHP) you just created

- Click: `select Folder` (*PHP*)

<img width="1511" alt="isolated" src="https://github.com/vincentchachere/osticket-prereqs/assets/161680745/1e8cf932-6f8d-4dd0-ae01-e7b746292449"><br>

***

### 21.H ) Download php-7.3.8 and Unzip it into the Directory (C:\PHP) you just created

- Click: `Extract`

<img width="1511" alt="isolated" src="https://github.com/vincentchachere/osticket-prereqs/assets/161680745/101abf72-f1e0-4f47-aec7-70d9b13fcc0f"><br>

***

### 22.A ) Check to see the php-7.3.8 made it into the PHP Directory

- Go Back To: `This PC` > `Windows (C:)` > `PHP`

- Double-Click: `PHP`

<img width="1511" alt="isolated" src="https://github.com/vincentchachere/osticket-prereqs/assets/161680745/f16a0e69-05ab-4d29-a9f1-792d6725f540"><br>

***

### 22.C ) Check to see the php 7.3.8 made it into the PHP Directory

- Now you will see the php.7.3.8 file inside the PHP directory, as seen in the image below.

<img width="1511" alt="isolated" src="https://github.com/vincentchachere/osticket-prereqs/assets/161680745/c1a99257-42a0-4c01-b687-102532db493a"><br>

***

<br>

### 23.A ) Download VC_redist.x86.exe

- Go To: [Installation Files](https://drive.google.com/drive/u/1/folders/1APMfNyfNzcxZC6EzdaNfdZsUwxWYChf6) and download VC_redist.x86.exe

  - *I will let you do the <ins>downloading</ins> steps on your own now, so that you can learn. Refer to previous steps for instruction (You got this! I believe in you!😁)*

- Check: The `I agree to the license terms and conditions` Box

- Click: `Install`

<img width="1511" alt="isolated" src="https://github.com/vincentchachere/osticket-prereqs/assets/161680745/5ec96900-768b-453e-b488-f1b94f83cf2b"><br>

***

<br>

### 23.B ) Download VC_redist.x86.exe

- Click: `Close` when it is done installing

<img width="1511" alt="isolated" src="https://github.com/vincentchachere/osticket-prereqs/assets/161680745/b96dbd82-60af-4e75-ac96-da2fb3f84ad7"><br>

***

### 24.A ) Download MySQL 5.5.62

- Go To: [Installation Files](https://drive.google.com/drive/u/1/folders/1APMfNyfNzcxZC6EzdaNfdZsUwxWYChf6) and download MySQL 5.5.62

- <ins>When the pop-up below shows up</ins>:

  - Click: `Next`

<img width="1511" alt="isolated" src="https://github.com/vincentchachere/osticket-prereqs/assets/161680745/59367782-74b6-4408-bf3f-ebe28a2c302b"><br>

***

### 24.B ) Download MySQL 5.5.62

- <ins>When the pop-up below shows up</ins>:

  - Check: The `I accept the terms in the License Agreement` Box

  - Click: `Next`

<img width="1511" alt="isolated" src="https://github.com/vincentchachere/osticket-prereqs/assets/161680745/aed0ccff-df67-4e94-9c7a-a98c86162d04"><br>

***

### 24.C ) Download MySQL 5.5.62

- Select: `Typical Setup`

- Click: `Next`

<img width="1511" alt="isolated" src="https://github.com/vincentchachere/osticket-prereqs/assets/161680745/8a137fe1-f0da-47a2-a339-693b5bfeb138"><br>

***

### 24.D ) Download MySQL 5.5.62

- Click: `Install`

<img width="1511" alt="isolated" src="https://github.com/vincentchachere/osticket-prereqs/assets/161680745/dbdb61d6-ea10-4370-8ed3-bdd01ed79710"><br>

***

### 24.E ) Download MySQL 5.5.62

- Check: The `Lanuch the MySQL Instance Configuration Wizard` Box

- Click: `Finish`

<img width="1511" alt="isolated" src="https://github.com/vincentchachere/osticket-prereqs/assets/161680745/43db12f6-5b9d-4517-85be-f7aacc72a83e"><br>

***

### 24.F ) Download MySQL 5.5.62

- Click: `Next`

<img width="1511" alt="isolated" src="https://github.com/vincentchachere/osticket-prereqs/assets/161680745/f8a6ce64-5cf1-49bb-96c4-51180aa3b021"><br>

***

### 24.G ) Download MySQL 5.5.62

- Select: `Standard Confirguration`

- Click: `Next`

<img width="1511" alt="isolated" src="https://github.com/vincentchachere/osticket-prereqs/assets/161680745/3e6dabfa-9096-4f60-aac9-18eedb587d86"><br>

***

### 24.H ) Download MySQL 5.5.62

- Make sure your screen matches the image below and once you verify that it does..&darr;

- Click: `Next`

<img width="1511" alt="isolated" src="https://github.com/vincentchachere/osticket-prereqs/assets/161680745/9d10e55d-15db-4439-bfea-061093afc753"><br>

***

### 24.I ) Download MySQL 5.5.62

- Type In: `The password you used to log into remote desktop.`

  - Click: `Next`

<img width="1511" alt="isolated" src="https://github.com/vincentchachere/osticket-prereqs/assets/161680745/70a583da-dc05-4d27-ab42-c29feaecaf31"><br>

***

### 24.J ) Download MySQL 5.5.62

- Click : `Finish`

<img width="1511" alt="isolated" src="https://github.com/vincentchachere/osticket-prereqs/assets/161680745/2505f9a5-604c-4197-9f4c-e87b6ae36097"><br>

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

### 29.A ) Enable Extensions

- Go to: `sites` > `Default` > `osTicket`

- Double-Click: `PHP Manager`

<img width="1511" alt="isolated" src="https://github.com/vincentchachere/osticket-prereqs/assets/161680745/44cb93d6-1662-40a1-ad77-ccd7b721b46b"><br>

***

### 29.B ) Enable Extensions

- Click: `Enable or Disable Extensions`

<img width="1511" alt="isolated" src="https://github.com/vincentchachere/osticket-prereqs/assets/161680745/fd5e93a8-cae4-4f2f-accb-1d39c99d1aef"><br>

***

### 29.C ) Enable Extensions

- Right-Click: `php_imap.dll`

- Click: `Enable`

<img width="1511" alt="isolated" src="https://github.com/vincentchachere/osticket-prereqs/assets/161680745/b85f7116-d50e-4593-a8d8-0a9f7fd2fb69"><br>

***

### 29.D ) Enable Extensions

- Right-Click: `php_intel.dll`

- Click: `Enable`

<img width="1511" alt="isolated" src="https://github.com/vincentchachere/osticket-prereqs/assets/161680745/97575f63-2d21-4113-8012-852224fe0ffb"><br>

***

### 29.E ) Enable Extensions

- Right-Click: `php_opache.dll`

- Click: `Enable`

<img width="1511" alt="isolated" src="https://github.com/vincentchachere/osticket-prereqs/assets/161680745/748526b0-3631-4115-8b09-2fbe5c796a23"><br>

### 29.F ) Verify all your extensions were enabled

- <ins>You should see the 3 following extensions in the 'enabled' section</ins>:

  - php_imap.dll
 
  - php_intel.dll

  - php_opache.dll

- Click: The `osTicket` folder to the left in your 'Connections' section.

<img width="1511" alt="isolated" src="https://github.com/vincentchachere/osticket-prereqs/assets/161680745/d08c24c3-9f19-44bc-a6e7-aebecb62886a"><br>

***

### 30. ) Restart the osTicket in your browser and observe the changes

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

  - Rename: `ost-sampleconfig.php`
 
  - To: `ost-config.php`

<img width="1511" alt="isolated" src="https://github.com/vincentchachere/osticket-prereqs/assets/161680745/8531889f-57a2-4d19-8a6b-67c650e109e4">

***

### 33. ) Rename: *ost-'sample'*config.php to ost-config.php

<img width="1511" alt="isolated" src="https://github.com/vincentchachere/osticket-prereqs/assets/161680745/205d5e8c-8f7d-42b1-a522-453d3ffda950"><br>

***

<img width="1511" alt="isolated" src="https://github.com/vincentchachere/osticket-prereqs/assets/161680745/1373c747-7943-48bb-baf9-a929be1c464f"><br>

***

<img width="1511" alt="isolated" src="https://github.com/vincentchachere/osticket-prereqs/assets/161680745/0667aff0-f52c-42e1-979c-6572067f84bb"><br>

***

<img width="1511" alt="isolated" src="https://github.com/vincentchachere/osticket-prereqs/assets/161680745/5d37d24b-8a5e-4934-a6a6-0567e2146189"><br>

***

<img width="1511" alt="isolated" src="https://github.com/vincentchachere/osticket-prereqs/assets/161680745/eb15d6f7-0f73-468b-94d1-20f0e961cf25"><br>

***

<img width="1511" alt="isolated" src="https://github.com/vincentchachere/osticket-prereqs/assets/161680745/ab42e0bf-dc39-405e-a2f3-01497e683ed5"><br>

***

<br>

### 34. ) Assign Permissions: ost-config.php

- Right-Click: `ost-config.php`

- Click: `Porperties`

- Click: `Security`

- Click: `Advanced`

- Select: `Disable Inheritance` > `Remove All`

- `New Permission` > `Everyone` > `All`

- Click: `Ok`

<img width="1511" alt="isolated" src="https://github.com/vincentchachere/osticket-prereqs/assets/161680745/e74adb11-a3ee-4901-8242-50fd7a6250f3"><br>

***

<img width="1511" alt="isolated" src="https://github.com/vincentchachere/osticket-prereqs/assets/161680745/cbaf1c4b-b0e6-4928-b5de-aa56cd41a6fc"><br>

***

<img width="1511" alt="isolated" src="https://github.com/vincentchachere/osticket-prereqs/assets/161680745/935cda62-1d67-45e0-93c4-39ebf92011cf"><br>

***

<img width="1511" alt="isolated" src="https://github.com/vincentchachere/osticket-prereqs/assets/161680745/14d20aec-b1c2-4839-ba3b-7e744b85ec95"><br>

***

<img width="1511" alt="isolated" src="https://github.com/vincentchachere/osticket-prereqs/assets/161680745/ad0b0008-da6d-4124-87a2-83826defb878"><br>

***

<img width="1511" alt="isolated" src="https://github.com/vincentchachere/osticket-prereqs/assets/161680745/adad3db8-a4ec-473f-9c71-3a37215ec688"><br>

***

<img width="1511" alt="isolated" src="https://github.com/vincentchachere/osticket-prereqs/assets/161680745/97a32d06-3517-452e-8ab0-87675667232d"><br>

***

<img width="1511" alt="isolated" src="https://github.com/vincentchachere/osticket-prereqs/assets/161680745/be008f3d-012a-4b11-a918-c3c22c0497e1"><br>

***

<img width="1511" alt="isolated" src="https://github.com/vincentchachere/osticket-prereqs/assets/161680745/fe2dfed6-11e7-46da-8038-9e136385df3d"><br>

***

<img width="1511" alt="isolated" src="https://github.com/vincentchachere/osticket-prereqs/assets/161680745/269eb513-a0b4-41bd-a369-c2b1e00cf068"><br>

***

<br>

### 35. ) Refresh PHP Manager (IIS) and Continue Setting Up osTicket in browser

- Click: `Continue`

- Name: `Helpdesk`

- `Default Email` (recieves emails from customers)

<img width="1511" alt="isolated" src="https://github.com/vincentchachere/osticket-prereqs/assets/161680745/1a924ff1-9f1f-435c-bec5-a3b9188ecc5d"><br>

***

<img width="1511" alt="isolated" src="https://github.com/vincentchachere/osticket-prereqs/assets/161680745/2ea73b73-8377-4c7d-ad18-3c0e2b82192d"><br>

***

<br>

### 37. ) Go To: [Installation Files](https://drive.google.com/drive/u/1/folders/1APMfNyfNzcxZC6EzdaNfdZsUwxWYChf6)

- Install: `HiediSQL`

- Open: `HiediSQL`

- Create a *New Session*: `username/Password`

- `Connect to Session`

- Create a database called: `osTicket`

<img width="1511" alt="isolated" src="https://github.com/vincentchachere/osticket-prereqs/assets/161680745/fade480e-0976-45d5-ae0c-8b14f56d1f3a"><br>

***

<img width="1511" alt="isolated" src="https://github.com/vincentchachere/osticket-prereqs/assets/161680745/caf744e4-2bdc-4147-9465-5518fa048245"><br>

***

<img width="1511" alt="isolated" src="https://github.com/vincentchachere/osticket-prereqs/assets/161680745/0bd0bce1-8dcb-44d1-aee2-a4d48dd776d1"><br>

***

<img width="1511" alt="isolated" src="https://github.com/vincentchachere/osticket-prereqs/assets/161680745/081856d4-ef5d-4ec7-a59b-22e8855aeca9"><br>

***

<img width="1511" alt="isolated" src="https://github.com/vincentchachere/osticket-prereqs/assets/161680745/ea34d25c-a02b-4d21-8f2c-5316b344bfe7"><br>

***

<img width="1511" alt="isolated" src="https://github.com/vincentchachere/osticket-prereqs/assets/161680745/939d0fda-cca3-46d6-ac98-f183d56fcc9a"><br>

***

<img width="1511" alt="isolated" src="https://github.com/vincentchachere/osticket-prereqs/assets/161680745/8e13a12e-d14e-42bf-b3c9-cc0479194a26"><br>

***

<img width="1511" alt="isolated" src="https://github.com/vincentchachere/osticket-prereqs/assets/161680745/12cd0142-0e16-4073-903a-d0e209f4bbab"><br>

***

<img width="1511" alt="isolated" src="https://github.com/vincentchachere/osticket-prereqs/assets/161680745/89aaecb0-f7a3-4e38-9aa6-0b220e7e9e9b"><br>

***

<img width="1511" alt="isolated" src="https://github.com/vincentchachere/osticket-prereqs/assets/161680745/50393481-ec35-40ad-a719-486a90ce6355"><br>

***

<img width="1511" alt="isolated" src="https://github.com/vincentchachere/osticket-prereqs/assets/161680745/4cdcb8e8-bd1a-4e5f-829d-dce605c8ee98"><br>

***

<img width="1511" alt="isolated" src="https://github.com/vincentchachere/osticket-prereqs/assets/161680745/4e0da616-805c-4acb-a332-642c6e29438d"><br>

***

<img width="1511" alt="isolated" src="https://github.com/vincentchachere/osticket-prereqs/assets/161680745/efd049eb-1d1d-4600-a58b-f59c33f908f1"><br>

***

<img width="1511" alt="isolated" src="https://github.com/vincentchachere/osticket-prereqs/assets/161680745/62806062-5451-4ae7-a22c-9154a62e0af6"><br>

***

<img width="1511" alt="isolated" src="https://github.com/vincentchachere/osticket-prereqs/assets/161680745/6554b822-d257-49e1-8c35-bd0c8e09c3e0"><br>

***

<br>

### 38. ) Continue Setting Up osTicket in Browser

- HiediSQL Database: `osTicket`

- MySQL Username: `vincentchachere` (put whatever you want just remember it)

- MySQL Password: `*Your Password*` (put whatever you want just remember it)

- Click: `INSTALL NOW`

<img width="1511" alt="isolated" src="https://github.com/vincentchachere/osticket-prereqs/assets/161680745/753262e2-49d9-47a9-a380-fb31e9067a68)"><br>

***

<img width="1511" alt="isolated" src="https://github.com/vincentchachere/osticket-prereqs/assets/161680745/bbd64de0-cdab-4757-8662-75e2ab0c7ea3"><br>

***

<br>

### 39. ) Congrats! Hopefully No Errors! Before logging in we need to do 2 Things:

#### <ins>1st Thing</ins>
- Delete: c:\inept\wwwroot\osTicket\\*`setup`*

  - ONLY DELETE THE `setup` PART NOT THE WHOLE THING

#### <ins>2nd Thing</ins>
- Set Permissions to '`Read` only' for:

  - C:\inetpub\wwwroot\osTicket\include\\*`ost-config.php`*

<img width="1511" alt="isolated" src="https://github.com/vincentchachere/osticket-prereqs/assets/161680745/665d900d-6f13-4172-b25b-6dc8dfe33469"><br>

***

<img width="1511" alt="isolated" src="https://github.com/vincentchachere/osticket-prereqs/assets/161680745/8a6d7d37-7227-4742-8fd4-aa0022645f1a"><br>

***

<img width="1511" alt="isolated" src="https://github.com/vincentchachere/osticket-prereqs/assets/161680745/6235eb2e-e4d5-4168-ae0f-ac1a7942b52a"><br>

***

<img width="1511" alt="isolated" src="https://github.com/vincentchachere/osticket-prereqs/assets/161680745/d1aca000-1239-4203-b9a3-8b932107092d"><br>

***

<img width="1511" alt="isolated" src="https://github.com/vincentchachere/osticket-prereqs/assets/161680745/a3c0a350-06ee-48ea-aabb-5fd680ba811c"><br>

***

<br>

### 40. ) Login: http://localhost/osTicket/scp/login.php

- Username: vincentchachere (The username you made at #38)

- Password: *YourPassword* (The password you made at #38)

<img width="1511" alt="isolated" src="https://github.com/vincentchachere/osticket-prereqs/assets/161680745/1c58635f-de50-42d3-8cf6-755f0e2ed9c0"><br>

***

<img width="1511" alt="isolated" src="https://github.com/vincentchachere/osticket-prereqs/assets/161680745/9977c4a4-0c10-4463-bc7b-99a123edc19f"><br>

***

<br>

### 41. ) End Users osTicket URL:

- http://localhost/osTicket/ 

<img width="1511" alt="isolated" src="https://github.com/vincentchachere/osticket-prereqs/assets/161680745/db3d50dd-5604-4f7e-a5d1-fe0e7b797677"><br>

***

<br>
