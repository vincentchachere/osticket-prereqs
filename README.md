<p align="center">
<img src="https://i.imgur.com/Clzj7Xs.png" alt="osTicket logo"/>
</p>

<h1>osTicket - Prerequisites and Installation</h1>
This tutorial outlines the prerequisites and installation of the open-source help desk ticketing system osTicket.<br/>

<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Internet Information Services (IIS)

<h2>Operating Systems Used</h2>

- Windows Windows 10 (21H2)

<h2>List of Prerequisites</h2>

- Connect to your Virtual Machine with Remote Desktop
- Install / Enable IIS in Windows
- Install Web Platform Installer
- Install osTicket v1.15.8
- Download and Install HeidiSQL
- Created database for "osTicket
- Clean up 
- Change File Permissions

<br>________________________________________________________________________________________________________________________<br>

<h2>📝 Installation Steps - Part A: Create a 'Resource Group'</h2><br>

<h3>1. ) Starting at the 'Home' screen in your Microsoft Azure Portal</h3>

 >**Click: the 'Resource Groups' icon that's already on your home screen**

 >**OR..**

 >**Search: 'Resource Groups' and click that one**

<img width="1511" alt="215035B0-C25C-4D73-97EF-D7B853FA0981" src="https://github.com/vincentchachere/osticket-prereqs/assets/161680745/6fbd7e34-2007-4a38-8023-85d094b8ebac"><br>
<img width="1511" alt="288E1011-D2F5-4BEA-BE41-76501A70922C" src="https://github.com/vincentchachere/osticket-prereqs/assets/161680745/aaf74755-636a-4191-935f-29f2f746a1e6"><br>
 >**NOTE: You can make a 'Resource Group' at the same time you create a VM. I just wanted to show you how to do it step-by-step.**
 
<h2></h2><br>

<h3>2. ) Next, click 'Create' to start your resource group</h3>

 >**Or..**

 >**You can click the blue 'Create' in the middle of the screen as well, and it will take you to the same place.**
 
<img width="1511" alt="2CF02E11-E2CA-4A52-B500-9B6841B62872" src="https://github.com/vincentchachere/osticket-prereqs/assets/161680745/a2758218-482c-4153-8931-cbd9a63d09e0">

<h2></h2><br>

<h3>3. ) Now, we'll input the following:</h3>

 >**Resource Group Name: RG-osTicket**

 >**Region: (US) West US 3**

 >***Scroll Down**

<img width="1511" alt="E2C30B0C-FA81-4329-8F23-DBB018C41018" src="https://github.com/vincentchachere/osticket-prereqs/assets/161680745/4829d10a-d483-4c28-93a1-64034a6e0cf3">

<h2></h2><br>

<h3>4. ) Finally, click 'Review + Create' </h3>




