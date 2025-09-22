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



---------------

<br />
