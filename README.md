<p align="center">
<img src="https://i.imgur.com/Clzj7Xs.png" alt="osTicket logo"/>
</p>

<h1>osTicket - Prerequisites and Installation</h1>
This tutorial outlines the prerequisites and installation of the open-source help desk ticketing system osTicket.<br />

<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- WindowsApp (macOS) *optional*
- Internet Information Services (IIS) (include something about the important of IIS, it will be serving as a web server for osTicket)

<h2>Operating Systems Used </h2>

- Windows 10</b> (22H2)

<h2>List of Prerequisites</h2>

- <a href="https://drive.google.com/uc?export=download&id=1b3RBkXTLNGXbibeMuAynkfzdBC1NnqaD">osTicket Installation Files</a>
- IIS 
- PHP Manager for IIS 
- Rewrite Module  
- VC_redistx86   
- MySQL 5.5.62

<h3>Note: The files inside of this link have been collected from the osTicket Documentation webpage and have been consolidated into a single link (see URL above) for your convenience.</h3>

<h2>Installation Steps</h2>

## Step 1: Create a Virtual Machine in Azure
- Log into Azure
- Create a Resource Group
- Create a VM with a Windows 10 Pro disk image
- Select at least 2 vcpus and 8 GiB memory for decent performance
<p>
<img width="1439" height="533" alt="vm-creation" src="https://github.com/user-attachments/assets/d5e9d5df-cece-4d98-9ae1-04c69a798677" />
</p>

## Step 2: Log into your VM
- You can use Remote Desktop Connection via any Windows OS to connect to your VM
- WindowsApp on macOS is another option to log into your VM (I will be using this method in the demonstration)
- Enter the **Public IP address** for your VM
- Enter your credentials you made in Azure when connecting

<p>
<img width="470" height="533" alt="2  connecting-to-vm" src="https://github.com/user-attachments/assets/bd139e1b-7630-45a2-a7d7-15427bffb642" />
</p>


## Step 3: Download the osTicket Installation Files

- Download the osTicket Installation Files using this <a href="https://drive.google.com/uc?export=download&id=1b3RBkXTLNGXbibeMuAynkfzdBC1NnqaD">link</a> inside of your VM
- Open the browser, copy and paste the link and hit enter
- You will most likely see this page, click "Download anyway"


<p>
<img width="559" height="160" alt="3  cant-scan-for-virus" src="https://github.com/user-attachments/assets/667ef732-4c45-4b4b-bb98-3203f1d3521b" />
</p>


- Exit the browser
- Click your "File Explorer" and navigate to the "Downloads" folder
- Click and drag your new **osTicket-Installation-Files** folder onto the Desktop (or wherever you prefer to have this)
- Right click the folder and select "Extract all"
- Select the destination folder you want the extracted files to go into

<img width="621" height="455" alt="Screenshot 2025-09-21 at 7 15 54 PM" src="https://github.com/user-attachments/assets/3c02bde8-8ff2-42ba-be6e-c89d9840fbbc" />

- You should have two folders now
- The folder we need is the one with all of the new extracted files (see screenshot below)
- Optional: You may delete the compressed folder to avoid any confusion in later steps.

<img width="164" height="218" alt="Screenshot 2025-09-21 at 7 18 37 PM" src="https://github.com/user-attachments/assets/f52461ab-7ccf-40d3-88d1-652b6f141e17" />

## Step 4:

- Navigate to the Windows search bar and type in **Turn Windows Features on or off**
- This is what this window should look like

<img width="419" height="376" alt="Screenshot 2025-09-21 at 7 58 39 PM" src="https://github.com/user-attachments/assets/16643084-d82f-4f22-8439-08224ed46934" />

- Scroll down and find the folder called **Internet Information Services**
- Select that folder (the black dot indicates you have selected it)
- Click the **plus button** right next to it to show the contents of the folder

<img width="413" height="366" alt="IIS " src="https://github.com/user-attachments/assets/3da05cc5-1d56-48b6-af69-a56a1f73fbbf" />

- Now you should see both folders **Web Management Tools** and **World Wide Web Services** selected (indicated by the black dot)
- Now refer to the **World Wide Web Services** folder (indicated in red in screenshot below)
- Click the **plus button** next to this folder to show the contents of it

<img width="414" height="362" alt="Screenshot 2025-09-21 at 8 03 26 PM" src="https://github.com/user-attachments/assets/1e9b45b2-f747-405d-af6d-c32c8ddea9c1" />

- Click the **plus button** next to the **Application Development Features** folder to show the contents of it

<img width="407" height="361" alt="Screenshot 2025-09-21 at 8 07 35 PM" src="https://github.com/user-attachments/assets/9670a940-f9ce-48f1-aed7-071be0cbad77" />

- Click the **CGI** folder and make sure it has a checkmark
- Press OK

<img width="406" height="364" alt="Screenshot 2025-09-21 at 8 09 10 PM" src="https://github.com/user-attachments/assets/c5292c34-09ff-492f-ba47-e5ce1bb0028a" />

- After Windows is doing searching the files and applying the changes, you should be met with this window below
- Go ahead and close it after has completed
  
<img width="651" height="474" alt="Screenshot 2025-09-21 at 8 11 51 PM" src="https://github.com/user-attachments/assets/02f833a9-3a44-467b-b048-43d8287fbf4b" />


## Step 5: Install PHP Manager

- Next we are going to install the PHP Manager, which is inside of our folder
- Go ahead and navigate to **osTicket-Installation-Files** folder on your desktop (or wherever you saved it)
- Open the **osTicket-Installation-Files** folder
- 
<img width="90" height="96" alt="Screenshot 2025-09-21 at 8 17 09 PM" src="https://github.com/user-attachments/assets/6fa61949-1a11-445a-b677-cce97dfd8e97" />

- No you're not crazy, there is another file inside called the same exact thing. Open this folder
- You should see these contents inside of this folder (see screenshot below)
- Open the installer called **PHPManagerForIIS_V1.5.0**

<img width="820" height="557" alt="Screenshot 2025-09-21 at 8 24 01 PM" src="https://github.com/user-attachments/assets/5583ae8e-9b3f-42a0-88cd-589d3b5d5ef5" />

- Go through the steps in the installer
- If successful this should pop up (see screenshot below)

<img width="497" height="404" alt="Screenshot 2025-09-21 at 8 26 59 PM" src="https://github.com/user-attachments/assets/cb747097-100d-4ac6-8d62-2a5fe7faaf2e" />


## Step 6: Install the Rewrite Module

- Go back to your **osTicket-Installation-Files** folder
- Open the installer called **rewrite_amd64_en-US**

<img width="645" height="168" alt="Screenshot 2025-09-21 at 8 29 08 PM" src="https://github.com/user-attachments/assets/6f229ddd-e71d-426b-863b-a9d84c74a7da" />

- Go through the installation wizard
- If successful, you should get this prompt (see screenshot below)
- Click Finish

<img width="491" height="382" alt="Screenshot 2025-09-21 at 8 30 24 PM" src="https://github.com/user-attachments/assets/c30cc505-0cc9-4799-bf4f-34613506713d" />

## Step 7: Create the directory C:\PHP

- Open a new window of File Explorer
- Navigate to your C:\ drive
- Create a folder in here called **PHP**

<img width="826" height="493" alt="Screenshot 2025-09-21 at 8 33 54 PM" src="https://github.com/user-attachments/assets/90f2be6d-c19f-47cd-9fb6-62b33f1e8bb2" />

## Step 8: Unzipping our PHP 7.3.8 into our new PHP folder

- Go back to your **osTicket-Installation-Files** folder
  
<img width="828" height="564" alt="Screenshot 2025-09-21 at 8 36 31 PM" src="https://github.com/user-attachments/assets/a3842f06-a2fd-4973-a359-8f52f2a9696e" />

- Right click the **php-7.3.8-nts-Win32-VC15-x86** folder
- Select **Extract all**
- Click Browse and navigate to C:\PHP ... or simply copy and paste **C:\PHP** into the search bar
- Click **Extract**

<img width="602" height="420" alt="Screenshot 2025-09-21 at 8 39 57 PM" src="https://github.com/user-attachments/assets/a56dbb7a-babc-453a-a80a-77dd09a9e5e0" />

## Step 9: Installing VC_redist.x86

- Navigate back to the **osTicket-Installation-Files** folder
- Double click to open the **VC_redist.x86** installer

<img width="822" height="519" alt="Screenshot 2025-09-21 at 8 45 51 PM" src="https://github.com/user-attachments/assets/756304f3-c980-4b52-861f-31da5865dfee" />

- Go through the installation wizard
- If successful you should see this (screenshot below)
- Go ahead and close this window

<img width="475" height="292" alt="Screenshot 2025-09-21 at 8 46 33 PM" src="https://github.com/user-attachments/assets/c8831d40-5ec9-42c9-b755-08dfb892a950" />

## Step 10: Installing MySQL 5.5.62

- Navigate back to the **osTicket-Installation-Files** folder
- Double click to open the **mysql-5.5.62-win32** installer

<img width="818" height="395" alt="Screenshot 2025-09-21 at 8 50 56 PM" src="https://github.com/user-attachments/assets/f5192e85-da6a-4a83-8082-e3271c309c72" />

- Go through the installation wizard
- When prompted with the three options: Typical, Custom, Complete
- Select **Typical**
- Click Install
- If successful you should see this (see screenshot below)
- Make sure that **Launch the MySQL Instance Configuration Wizard** is selected
- Click Finish

<img width="491" height="384" alt="Screenshot 2025-09-21 at 8 55 06 PM" src="https://github.com/user-attachments/assets/c5a111f3-a077-452e-b30f-c76ae0ba6e97" />

- You should now be met with a new installation wizard
- Click Next

<img width="497" height="375" alt="Screenshot 2025-09-21 at 8 56 49 PM" src="https://github.com/user-attachments/assets/fdc55950-a833-4da1-a594-6bcb474cfe00" />

- Choose **Standard Configuration**

<img width="492" height="373" alt="Screenshot 2025-09-21 at 8 57 40 PM" src="https://github.com/user-attachments/assets/404b57d8-2d40-422d-be96-54480941fc99" />

- This should be the next page of the wizard
- Everything is already fine in here, click next

<img width="499" height="375" alt="Screenshot 2025-09-21 at 8 58 06 PM" src="https://github.com/user-attachments/assets/d25ffca5-2dbd-4685-a882-c20de638726d" />

- **WARNING**: It is very easy to mess up at this part
- Please write out credentials that **you will be able to remember**
- Click Next
- Click Execute

<img width="497" height="376" alt="Screenshot 2025-09-21 at 8 59 33 PM" src="https://github.com/user-attachments/assets/ac873765-bbe9-4b5b-99d5-399741cc5894" />

- If you followed the steps correctly, you should be met with this (screenshot below)
- Click Finish
- Our database is now installed

<img width="494" height="372" alt="Screenshot 2025-09-21 at 9 03 58 PM" src="https://github.com/user-attachments/assets/49361ad0-b58b-41d3-868a-b399ae3f9ecf" />



## Step 11: Open IIS as an Admin

- Go to your Windows search bar
- Type in **IIS**
- You should see this pop up. Right click it and select **Run as administrator**
<img width="341" height="87" alt="Screenshot 2025-09-21 at 9 06 45 PM" src="https://github.com/user-attachments/assets/703c2aea-12a9-481f-87c6-a83128241f4a" />

- This is the page that should pop up (see screenshot below)

<img width="1062" height="612" alt="Screenshot 2025-09-21 at 9 07 37 PM" src="https://github.com/user-attachments/assets/c0d1fa90-2b6f-4130-bf9b-2475f92fd483" />

- Double click **PHP Manager**

<img width="85" height="83" alt="Screenshot 2025-09-21 at 9 08 39 PM" src="https://github.com/user-attachments/assets/a6020f24-d61b-42d1-bb3d-5efb3d02e635" />

- Click **Register new PHP version**

<img width="742" height="298" alt="Screenshot 2025-09-21 at 9 09 11 PM" src="https://github.com/user-attachments/assets/fd2a9c11-3778-48ac-bf80-131dcc5976f3" />

- The new page should ask you to provide a path
- Click the **...**
- Navigate to C:\PHP\php-cgi.exe
- Or simply copy and paste **C:\PHP\php-cgi.exe** into the path **IF AND ONLY IF** you copied my steps exactly earlier for where we created our PHP folder.
- Click OK

<img width="504" height="214" alt="Screenshot 2025-09-21 at 9 10 51 PM" src="https://github.com/user-attachments/assets/99a6d0c6-b080-42d3-82e9-9b114427a5c1" />

- Now simply **right click** the box shown in the screenshot below
- Select **Stop**
- Wait a few moments
- Select **Start**
- By doing all of this we have effectively restarted the IIS web server.

<img width="1062" height="617" alt="Screenshot 2025-09-21 at 9 14 54 PM" src="https://github.com/user-attachments/assets/279c51a9-c43f-4627-91ca-7232862597fd" />


## Step 12: Install osTicket v1.15.8

- Navigate back to the **osTicket-Installation-Files** folder
- Right click the **osTicket-v1.15.8** folder
- Click **Extract all**
- Click Extract
- This will make another folder called **osTicket-v1.15.8** (this will have our contents)
- The extraction process may take a minute or two

<img width="822" height="397" alt="Screenshot 2025-09-21 at 9 21 40 PM" src="https://github.com/user-attachments/assets/1264b3cf-5107-4e64-af00-d76013db4cbb" />

- Open up the extracted **osTicket-v1.15.8** folder
- There should be two folders called **scripts** and **upload**
- We are going to copy the **upload** folder

<img width="819" height="281" alt="Screenshot 2025-09-21 at 9 25 02 PM" src="https://github.com/user-attachments/assets/7109f961-1c76-42a7-97a9-961c92c9cfe9" />

- Open up a new instance of File Explorer
- Navigate to **C:\inetpub\wwwroot** path
- Paste your **upload** folder from the previous step into **C:\inetpub\wwwroot**
- The result should look like this (screenshot below)
  
<img width="822" height="338" alt="Screenshot 2025-09-21 at 9 28 23 PM" src="https://github.com/user-attachments/assets/ef9735cd-ba09-4d08-a1d9-61dd732430df" />

- Now, rename the upload folder to **osTicket**
- Your result should look like this (screenshot below)

<img width="828" height="287" alt="Screenshot 2025-09-21 at 9 29 50 PM" src="https://github.com/user-attachments/assets/0fafa739-87d8-4705-baf0-0ad872f6e8d3" />


## Step 13: Restarting the IIS web server (again)

- Go back to this window again
- Right click the box
- Click Stop
- Wait a few moments
- Click Start
- This ensures that we have restarted the IIS web server

<img width="299" height="412" alt="Screenshot 2025-09-21 at 9 32 21 PM" src="https://github.com/user-attachments/assets/30fcdb5e-8707-4501-85b3-9f5a6460f8a8" />

- Now click the **Sites arrow**
- Click the **Default Web Site arrow**
- Click **osTicket**
- Then click **Browse :80 (http)**

<img width="1060" height="614" alt="Screenshot 2025-09-21 at 9 34 29 PM" src="https://github.com/user-attachments/assets/dc83561d-290f-418c-8453-378af53f1c6a" />

- If successful this should load up the osTicket website

<img width="1431" height="857" alt="Screenshot 2025-09-21 at 9 37 49 PM" src="https://github.com/user-attachments/assets/806b005e-4a35-4fcb-97c5-d09963ee2663" />


## Step 14: Enabling necessary extensions

- Go back to the **IIS Manager** window
- Click osTicket
- Double-click PHP Manager (see screenshot below)

<img width="1059" height="467" alt="Screenshot 2025-09-21 at 9 41 49 PM" src="https://github.com/user-attachments/assets/84ff2c61-490e-48ce-9977-05ee2e22c3e8" />

- You should be met with this page
- Click **Enable or disable an extension**

<img width="1061" height="613" alt="Screenshot 2025-09-21 at 9 43 55 PM" src="https://github.com/user-attachments/assets/06234836-7903-4bfa-b2be-923a992af30a" />

- We are going to enable the following extensions:
- **php_imap.dll**
- **php_intl.dll**
- **php_opcache.dll**

- Once you find these extensions, right click them and click Enable
- This should be the end result (see screenshot below)

<img width="1068" height="477" alt="Screenshot 2025-09-21 at 9 47 02 PM" src="https://github.com/user-attachments/assets/851414f3-6e0f-4c5e-af47-8fda4f9ef95c" />








---------------

<br />
