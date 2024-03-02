<p align="center">
<img src="https://i.imgur.com/Clzj7Xs.png" alt="osTicket logo"/>
</p>

# osTicket - Prerequisites and Installation
This tutorial outlines the prerequisites and installation of the open-source help desk ticketing system osTicket.<br/>

## Environments and Technologies Used

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Internet Information Services (IIS)

## Operating Systems Used

- Windows Windows 10 (21H2)

## List of Prerequisites

- Connect to your Virtual Machine with Remote Desktop
- Install / Enable IIS in Windows
- Install Web Platform Installer
- Install osTicket v1.15.8
- Download and Install HeidiSQL
- Created database for "osTicket
- Clean up 
- Change File Permissions

<br>

________________________________________________________________________________________________________________________<br>

# 📝 Installation Steps - Part A: Create a 'Resource Group'

<br>

## 1. ) Starting at the 'Home' screen in your Microsoft Azure Portal

- Click: the 'Resource Groups' icon that's already on your home screen or..

- You can Search: 'Resource Groups' and click that one. It will take you to the same place, which is the 'Resource Groups Default Directory'

<img width="1511" alt="isolated" src="https://github.com/vincentchachere/osticket-prereqs/assets/161680745/d273a110-a34c-4707-8a06-058d12c11cc5"><br>

 >**NOTE: You can make a 'Resource Group' at the same time you create a VM. I just wanted to show you how to do it step-by-step.**

***

<br>
 
## 2. ) Click 'Create' to start your resource group

- Or..

- You can click the blue 'Create' in the middle of the screen as well, and it will take you to the same place.
 
<img width="1511" alt="isolated" src="https://github.com/vincentchachere/osticket-prereqs/assets/161680745/56fec2c9-0ba3-4e35-8c26-6bc6e7e6313b"><br>

***

<br>

## 3. ) Next, we'll input the following:

- Resource Group Name: RG-osTicket

- Region: (US) West US 3

- *Scroll Down*

 >**ATTENTION: Double check spelling when creating anything (resource groups, virtual machines, etc.) or you will have to delete all your work and start over, because the information you input will NOT be able to be able to be edited once it's created (name, region, etc.)**

<img width="1511" alt="E2C30B0C-FA81-4329-8F23-DBB018C41018" src="https://github.com/vincentchachere/osticket-prereqs/assets/161680745/4829d10a-d483-4c28-93a1-64034a6e0cf3"><br>

***

<br>

## 4. ) Now, let's click 'Review + Create'

- Dont worry about the 'Tags' section, we don't need that part for this lab.

- The 'Tags' section is used for organizational purposes.

<img width="1511" alt="F462BC66-31ED-444E-A61B-CD02C75151FD" src="https://github.com/vincentchachere/osticket-prereqs/assets/161680745/22252a11-ece8-4e38-873c-f6faf00efe29"><br>

 >**NOTE: We have NOT finished creating the resource group yet by clicking 'Review + Create'. Microsoft Azure let's you double check (review) the information you input before finalizing (creating) your resource group. It also does this for virtual machines, so make it a habit to double check the information you type in, so that you don't have to erase everything you end up creating, because of one wrong letter.**

***

<br>

## 5. ) Finally, we review and create!

- Look over the resource group information.

- Verify its all correct.

- Click 'Create' to bring alive our first resource group!

<img width="1511" alt="6353AD56-C708-4D3D-ABEB-7C29A8E42E5F" src="https://github.com/vincentchachere/osticket-prereqs/assets/161680745/2f2d3265-2f3f-457f-a710-1be04c7d9545"><br>

***

<br>

## Congrats!

### You're done creating you're Resource Group!

- You should see the 'Successfully Ceated Resource Group Notification' in the top right corner of your screen.

- Click 'Refresh' if you dont see your Resource Group, then..

- Click your resource group 'RG-osTicket' to enter into the next part of this lab.

<img width="1509" alt="3C89D03C-0D84-4484-BFD6-79D2FBDF9012" src="https://github.com/vincentchachere/osticket-prereqs/assets/161680745/e2981d35-3f56-4b35-a47d-d2dafd1600a6"><br>

 >**NOTE: Whenever you create a resource group or virtual machine and DO NOT see it in your Azure Portal in its correct location, there's two solutions to this:**

 >**First, refresh your Resource Group Default Directory (Search: Resource Group and you'll be in that section), and if that's unsuccessful..**

 >**Go through the steps again in this lab and if it doesn't let you create a resource group with the name 'RG-osTicket' (the name you originally typed in for the resurce group), then that's how you know the Resource Group is created, you will just have to wait a little longer and refresh your Resource Group Default Directory.**

________________________________________________________________________________________________________________________<br>

# 📝 Installation Steps - Part B: Create a 'Resource Group'

<br>

## 7. ) 

- First, click Refresh then if your resource group doesnt pop up..

- Click 'Refresh' and it should show up.

<img width="1509" alt="D562A5D5-19D6-423B-BB96-A794E4869CCF" src="https://github.com/vincentchachere/osticket-prereqs/assets/161680745/28151172-7ca9-49ec-823f-14686998d4a6"><br>

 >**NOTE: If your resource group doesnt show up just go through the steps again, and if it doesn't let you create a resource group with 'RG-osTicket' (the name you originally typed in), then that's how you know it went through and you just have to wait a minute, refresh your 'Resource Groups Default Directory', and let technology do its thing.**

***

<br>

## 8. ) 

- 

- 

- 

 >**h**

<img

***

## 8. ) 

- 

- 

- 

 >**h**

<img

***

## 8. ) 

- 

- 

- 

 >**h**

<img

***
