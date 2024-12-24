<p align="center">
<img src="https://i.imgur.com/Clzj7Xs.png" alt="osTicket logo"/>
</p>

# osTicket - Prerequisites and Installation

In this lab, we set up the osTicket helpdesk system by completing its prerequisites and installation. Using tools like Microsoft Azure, IIS, and Remote Desktop, we prepare a virtual environment, configure necessary components, and install osTicket step-by-step.

## Environments and Technologies Used

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop (macOS)
- Internet Information Services (IIS)

## Operating Systems Used

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

## Installation Files

- https://drive.google.com/drive/u/1/folders/1APMfNyfNzcxZC6EzdaNfdZsUwxWYChf6

<details>

<summary>

## ⚙️ Part A: Create a Resource Group

</summary>

### 1. ) Create a Resurce Group

*For assistance on creating Virtual Machines and Resource Groups go to my other lab [here](https://github.com/vincentchachere/virtual-machine)

<ins>Input the following Information</ins>:

- Resource Group Name: `RG-osTicket`

- Region: `(US) West US 3`

- Click: `Review + Create`

- Click: `Create`

*Double-check spelling when creating resources (e.g., resource groups, virtual machines). Names, regions, and similar inputs cannot be edited after creation. Errors may require deleting and restarting your work.*

<p align="center">
<img width="800" alt="E2C30B0C-FA81-4329-8F23-DBB018C41018" src="https://github.com/vincentchachere/osticket-prereqs/assets/161680745/4829d10a-d483-4c28-93a1-64034a6e0cf3">

</details>

<details>

<summary>

## ⚙️ Part B: Create a Virtual Machine

</summary>

### 2. ) Create a Virtual Machine inside the Resource Group

<ins>Input the following Information</ins>:

*Fill in everything displayed in the image below.*

- Select Resource Group Name: `RG-osTicket` (The one you created in Part A: Step 1)

- Virtual Machine Name: `vm-osticket` (all lowercase)

- Region: `(US) West 3`

- Image: `Windows 10 Pro, version 22H2 - ×64 Gen2`

- Size: `Standard_D45_v3 - 4 vcpus, 16 GiB memory ($140.16/month)`

- Username: `vincentchachere` (this can be whatever you want - just remember it)

- Password: `whatever-you-want` (just remember it)

- Check: The `Licensing` Box

- Select: `Review and Create`

- Click: `Create`

<p align="center">
<img width="800" alt="isolated" src="https://github.com/user-attachments/assets/4081f85f-969f-44ba-b922-173a14e9ac78">
<p align="center">
<img width="800" alt="isolated" src="https://github.com/user-attachments/assets/d2ce647d-88fe-440a-9a34-387d4cc3b56d">

</details>

<details>

<summary>

## ⚙️ Part C: Remote Desktop into your Virtual Machine

</summary>

### 3. ) Connect your Virtual Machine to Remote Desktop

*For assistance on connecting Virtual Machines to Remote Desktop go to Step 5 on [this lab](https://github.com/vincentchachere/virtual-machine)*

- Username: `vincentchachere` (whatever you created in Part B: Step 2)

- Password: `Your Password` (whatever you created in Part B: Step 2)

- Click: `Continue`

<p align="center">
<img width="800" alt="isolated" src="https://github.com/user-attachments/assets/ccaac932-e865-4110-a96e-96d18b5b3cd0">

<br>
<br>
<br>

<ins>Connect your Virtual Machine to Remote Desktop</ins>:

- Uncheck: `All Boxes`

- Click: `Accept`

<p align="center">
<img width="800" alt="isolated" src="https://github.com/vincentchachere/osticket-prereqs/assets/161680745/f59877e2-da56-4767-8cef-54cb4d0fdbe9">

</details>

<details>

<summary>

## ⚙️ Part D: Install Prerequisites

</summary>

### 4. ) Install and Enable IIS in Windows Virtual Machine

<ins>Once inside your Virtual Machine we'll need to Install and Enable IIS by doing the following</ins>:

  - Right-Click: `Start` in the bottom left corner of your screen

  - Select: `Run`

*Or you could just type `run` inside the search bar and press `Enter`*

<p align="center">
<img width="800" alt="isolated" src="https://github.com/vincentchachere/osticket-prereqs/assets/161680745/6f279019-c2f3-4446-b4f1-76e5cf798e2b">

<br>
<br>
<br>

<ins>Install and Enable IIS in Windows Virtual Machine</ins>:

- Type In: `Control Panel`

- Click: `OK`

<p align="center">
<img width="800" alt="isolated" src="https://github.com/user-attachments/assets/789188b7-01d1-45b8-a805-bbd6ff0594aa">

<br>
<br>
<br>

<ins>Install and Enable IIS in Windows Virtual Machine</ins>:

  - Select: `Programs`

<p align="center">
<img width="800" alt="isolated" src="https://github.com/user-attachments/assets/3c279675-4075-4b70-9702-f319b73c7131">

<br>
<br>
<br>

<ins>Install and Enable IIS in Windows Virtual Machine</ins>:

  - Select: `Turn Windows Features On or Off`

<p align="center">
<img width="800" alt="isolated" src="https://github.com/user-attachments/assets/3ef2747d-3665-48a8-9796-a482fd275039">

<br>
<br>
<br>

<ins>Install and Enable IIS in Windows Virtual Machine</ins>:
                              
  - Enable and Open: `Internet Information Services (IIS)`
 
  - Enable and Open: `World Wide Web Services`

    - Check: `All Boxes` within this feature's folder

<p align="center">
<img width="800" alt="isolated" src="https://github.com/user-attachments/assets/ece03bc2-ec8a-4392-b658-b98b771be30b">

<br>
<br>
<br>

<ins>Install and Enable IIS in Windows Virtual Machine</ins>

*While still inside the World Wide Web Service folder:*

  - Open: `Application Development Features` folder

  - Enable: `CGI`

  - Collapse: `Application Development Features` folder

  - Go Back Inside: `World Wide Web Service` folder

<p align="center">
<img width="800" alt="isolated" src="https://github.com/user-attachments/assets/7e2097ad-9abe-4db1-8f70-80c60d46548f">

<br>
<br>
<br>

<ins>Install and Enable IIS in Windows Virtual Machine</ins>:

*Back inside the World Wide Web Service folder:*

  - Enable: Common HTTP Features

<ins>Within the Common HTTP Fetures feature folder</ins>:

  - Check: `All Boxes` within this feature's folder
 
  - Click: `OK`

<p align="center">
<img width="800" alt="isolated" src="https://github.com/vincentchachere/osticket-prereqs/assets/161680745/4a756f64-9ba3-45fb-a690-0ddf5bd5b4bd"><br>

<br>
<br>
<br>

<ins>Install and Enable IIS in Windows Virtual Machine</ins>:

- Wait for it to load...

<p align="center">
<img width="800" alt="isolated" src="https://github.com/vincentchachere/osticket-prereqs/assets/161680745/81b5957a-ab51-4c47-8e46-91a8d3b3f961"><br>

<br>
<br>
<br>

<ins>Install and Enable IIS in Windows Virtual Machine</ins>:

<ins>When that's done loading<ins>:

- Click: `Close`

<p align="center">
<img width="800" alt="isolated" src="https://github.com/vincentchachere/osticket-prereqs/assets/161680745/904c8fec-b77a-4efa-81fa-a62e801dc3fa"><br>

<br>
<br>
<br>

### 17.A ) Open Microsoft Edge to Test IIS

- Open: `Microsoft Edge` Internet Browser

- Click: `Start without your data`

<p align="center">
<img width="800" alt="isolated" src="https://github.com/vincentchachere/osticket-prereqs/assets/161680745/e7c74b77-ca58-4c36-8623-b641438aee10"><br>

***

### 17.B ) Open Microsoft Edge to Test IIS

- Uncheck: `the Box`

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

- Uncheck: `the Box`

- Click: `Confirm and start browsing`

<p align="center">
<img width="800" alt="isolated" src="https://github.com/vincentchachere/osticket-prereqs/assets/161680745/1e5c7aa4-97dd-4c8d-a09d-c9cafddda685"><br>

***

### 17.E ) Open Microsoft Edge to Test IIS

- Type: `127.0.0.1` into the browser

  - If you do not see the image displayed below then try uninstalling and reinstalling IIS

  - The `How To Uninstall and Reinstall Instructions` are directly underneath the image below

<p align="center">
<img width="800" alt="isolated" src="https://github.com/vincentchachere/osticket-prereqs/assets/161680745/7c2dae78-f8bb-40ba-9f73-b24d60b25c91"><br>

>**To Uninstall and Reinstall IIS do the following:**

>**Right-Click: `Start` > Click: `Run` >**

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

<ins>Open the Installation Files into a seperate tab or split screen as seen below, so that you can easily access them throught out this lab</ins>:

  - Double-Click: `PHP Manager`

  - Click: The `...` Dots in the upper right of your screen next to the 'Share' button

  - Click: `Open in new window`

*Downloading this way is the only method I've found that is quick and successful on the first try, without needing multiple attempts.* 

<p align="center">
<img width="800" alt="isolated" src="https://github.com/vincentchachere/osticket-prereqs/assets/161680745/7c65e858-f02e-4a8f-91e3-961c718d1956"><br>

***

### 18.B ) Download PHP Manager for IIS

- Click: `Download anyway`

- <ins>Now you can Either:</ins>

  - Wait for it to pop up when its done loading
  
    or..

  - Click: The `...` Dots in the upper right corner of your screen and Click: `Downloads`

>**Sometimes when the file downloads it does not pop up, so I wanted to show you both ways.**

>**You can also simply go to your `File Explorer` > `Downloads` > Double-Click: `PHPManagerforIIS_V1.5.0`**

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

- Check the Box: `I accept the terms in the License Agreement`

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

- Go To: `File Explorer` > `This PC` > `Windows (C:)`

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

- Click: `Select Folder` (*PHP*)

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

- Go To: [Installation Files](https://drive.google.com/drive/u/1/folders/1APMfNyfNzcxZC6EzdaNfdZsUwxWYChf6) and Download: `VC_redist.x86.exe`

  - *I will let you do the <ins>downloading</ins> steps on your own now, so that you can learn. Refer to previous steps for guidance.*

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

- Go To: [Installation Files](https://drive.google.com/drive/u/1/folders/1APMfNyfNzcxZC6EzdaNfdZsUwxWYChf6) and Download: `MySQL 5.5.62`

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

- Click: `OK`

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

</details>

<details>

<summary>

## ⚙️ Part E: Install osTicket

</summary>

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

 - Go To: `This PC` > `Windows (C:)` > `inetpub` > `wwwroot`

- <ins>Drag and Drop `upload` into</ins>:

  - `This PC` > `Windows (C:)` > `inetpub` > `wwwroot`

<p align="center">
<img width="800" alt="isolated" src="https://github.com/vincentchachere/osticket-prereqs/assets/161680745/54aa0527-e724-48f3-898c-0c1797462f43"><br>

***

### 27.D ) Install osTicket v1.15.8

- Right-Click: `upload` (*the `upload` that is in the new File Explorer you just opened*)

- Click: `Rename`

<p align="center">
<img width="800" alt="isolated" src="https://github.com/vincentchachere/osticket-prereqs/assets/161680745/a92db299-809a-40c2-b194-9ba4b6f01f6b"><br>

***

### 27.E ) Install osTicket v1.15.8

- Type In: `osTicket`

- Press: `Enter`

  - Spell it exactly like this: `osTicket` (with a capital `T` and lowercase everything else)

<p align="center">
<img width="800" alt="isolated" src="https://github.com/vincentchachere/osticket-prereqs/assets/161680745/2f19fba0-01d9-413c-97b3-8fc1b71c78f2"><br>

***

### 28.A ) Refresh the osTicket site in your browser and observe the changes

- Open: `IIS` <ins>as an Administrator</ins>

<p align="center">
<img width="800" alt="isolated" src="https://github.com/vincentchachere/osticket-prereqs/assets/161680745/c9e6f828-a8e4-4087-be9a-c257ac61efbf"><br>

***

### 28.B ) Refresh the osTicket site in your browser and observe the changes

- Click: `Restart`

<p align="center">
<img width="800" alt="isolated" src="https://github.com/vincentchachere/osticket-prereqs/assets/161680745/0bc5bda8-62d2-47d7-8db4-2de5b7be4513"><br>

***

### 28.C ) Refresh the osTicket site in your browser and observe the changes

- Go to: `Sites` > `Default Web Site` > `osTicket`

- <ins>On the Right side of your IIS Manager</ins>:
  - Click: `Browse*: 80`

<p align="center">
<img width="800" alt="isolated" src="https://github.com/vincentchachere/osticket-prereqs/assets/161680745/fbad175e-01b3-4c3a-a8fb-8b2db19db2f6"><br>

***

### 29.A ) Enable Extensions for osTicket

- Go to: `Sites` > `Default Web Site` > `osTicket`

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

- You should see the 3 following extensions in the `enabled` section:

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

- *Observe the changes*

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

- *Scroll all the way down*

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

- Click: `Remove all inherited permissions from this object`

<p align="center">
<img width="800" alt="isolated" src="https://github.com/vincentchachere/osticket-prereqs/assets/161680745/b0a950c8-51f1-48b2-b757-d0edeebfc9ab"><br>

***

### 32.C ) Assign Permissions To: ost-config.php

- Click: `Add` > `Select a principal` > Type In: `Everyone` > Click: `Check Names`

  - *It should be underlined after you click 'Check Names'*

- Click: `OK`

<p align="center">
<img width="800" alt="isolated" src="https://github.com/vincentchachere/osticket-prereqs/assets/161680745/63e662f4-ada6-417a-81c2-d5668c39065d"><br>

***

### 32.D ) Assign Permissions To: ost-config.php

- Select: `Full Control` *(make sure all boxes are checked as seen in the image below)*

- Click: `OK`

- Click: `OK`

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

- Right-Click: `Unamed`

- Click: `Create new`

- Click: `Database`

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

<ins>Scroll down to `Part G: Clean Up Resources` for further instructions on comlpleteing this lab.</ins>

<p align="center">
<img width="800" alt="isolated" src="https://github.com/vincentchachere/osticket-prereqs/assets/161680745/7f4988fb-ea09-4432-b689-dedfe5b96449"><br>

***

</details>

<details>

<summary>

## ⚙️ Part G: Clean Up Resources

</summary>

### 37.A ) Clean Up Resources

- Browse to your help desk login page: `http://localhost/osTicket/scp/login.php`

<ins>Before logging in we need to do 2 Things</ins>:

- Clean Up Resources

  - 1st Thing - Delete: c:\inept\wwwroot\osTicket\\*`setup`*

- Change File Permissions

  - 2nd Thing - Set Permissions to `Read` <ins>only</ins> for: This PC > inetpub > wwwroot > osTicket > include > *`ost-config.php`*

<ins>Scroll down to `Step 37.B` for further instruction</ins>

<p align="center">
<img width="800" alt="isolated" src="https://github.com/vincentchachere/osticket-prereqs/assets/161680745/94a00827-144e-435d-abaa-f2b052d6cb74"><br>

***

### 37.B ) Clean Up Resources

<ins>1st Thing</ins>:
  
  - Delete: c:\inept\wwwroot\osTicket\\`setup`

    - ONLY DELETE THE `setup` PART - NOT THE WHOLE THING

<ins>Scroll down `Part H: Change File Permissions` for the 2nd Thing</ins>

<p align="center">
<img width="800" alt="isolated" src="https://github.com/vincentchachere/osticket-prereqs/assets/161680745/1fcc1edd-c8da-406e-aaee-495acdd2ab82"><br>

***

</details>

<details>

<summary>

## ⚙️ Part H: Change File Permissions

</summary>

<ins>2nd Thing: Set Permissions to `Read` only for `ost-config.php`</ins>:

  - File Explorer: This PC > inetpub > wwwroot > osTicket > include > *`ost-config.php`*

    - Right-Click: *`ost-config.php`*
 
    - Select: `Properties`

<p align="center">
<img width="800" alt="isolated" src="https://github.com/vincentchachere/osticket-prereqs/assets/161680745/a532e9ec-56e1-44a6-a8e1-7e02bf41ef61"><br>

***

### 38.A ) Change File Permissions

<ins>2nd Thing Set Permissions to `Read` only for `ost-config.php`</ins>:

- Go To: `Security` > `Advanced` > `Edit`

<p align="center">
<img width="800" alt="isolated" src="https://github.com/vincentchachere/osticket-prereqs/assets/161680745/251d87d6-5fec-4133-a470-113d61ee3905"><br>

***

### 38.B ) Change File Permissions

<ins>2nd Thing: Set Permissions to `Read` only for `ost-config.php`</ins>:

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

☎️ For any questions, or just to connect, you can message me at: www.linkedin.com/in/vincentchachere

</details>
