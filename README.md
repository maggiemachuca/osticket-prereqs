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






---------------

<br />
