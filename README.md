<p align="center">
<img src="https://miro.medium.com/v2/resize:fit:720/1*--RgGZA7dD7JUX7ZDwzG-g.png" alt="Microsoft Active Directory Logo"
    height="300"
  width="300"/>
</p>

<h1>On-premises Active Directory Deployed in the Cloud (Azure)</h1>
The goal of this lab is to deploy and configure Active Directory (AD) in a virtualized environment using Azure. We will create a Domain Controller (DC), join a client machine to the domain, and configure user accounts and Remote Desktop access for both administrative and non-administrative users.<br />


<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Active Directory Domain Services
- PowerShell

<h2>Operating Systems Used </h2>

- Windows Server 2022
- Windows 10 (21H2)

<h2>High-Level Deployment and Configuration Steps</h2>

- Create a Resource Group
- Create a Virtual Network and Subnet
- Create the Domain Controller VM (Windows Server 2022)
- Create the Client VM (Windows 10)
- Attach it to the same region and Virtual Network as DC-1
- After VM is created, set Client-1’s DNS settings to DC-1’s Private IP address
- From Client-1, open PowerShell and run ipconfig /all
- Install Active Directory
- Create a Domain Admin user within the domain
- Join Client-1 to your domain (mydomain.com)
- Setup Remote Desktop for non-administrative users on Client-1
- Create a bunch of additional users and attempt to log into client-1 with one of the users




<h2>Deployment and Configuration Steps</h2>



<p>
Created and deployed the Vnet for the virtual machines in azure, inside the "Active-Directory-Lab" resource group (a virtual network lets computers and devices talk to each other without needing physical cables, making IT networks more flexible, scalable, and efficient!).  
</p>
<br />

<p>
<img src="https://i.imgur.com/pERPKJA.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Created and deployed the windows server virtual machine in azure, inside the "Active-Directory-Lab" resource group for unified deployment, organization as well as easier management.   
</p>
<br />

<p>
<img src="https://i.imgur.com/6a25u7I.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Created and deployed the windows 10 virtual machine in azure, inside the "Active-Directory-Lab" resource group for unified deployment, organization as well as easier management.
</p>
<br />

<p>
<img src="https://i.imgur.com/fCHSqz2.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Setting Client-1’s DNS to DC-1’s Private IP is essential for domain authentication, Active Directory functionality, group policy updates, and proper internal resource resolution. Without this setting, Client-1 may fail to join the domain, authenticate users, or access shared network resources.   
</p>
<br />

<p>
<img src="https://i.imgur.com/MMBzW6e.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Running ipconfig /all in PowerShell helps verify Client-1’s network configuration, ensuring that:
It has the correct IP address, subnet mask, and default gateway.
It is using DC-1’s Private IP as its DNS server (critical for domain functionality).
It is connected to the correct domain and can communicate with network resources.
If there are issues, this command is the first troubleshooting step in diagnosing network or Active Directory problems.
</p>
<br />

<p>
<img src="https://i.imgur.com/GNdDd6K.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<img src="https://i.imgur.com/17Vp9Eb.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<img src="https://i.imgur.com/0oAN80D.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<img src="https://i.imgur.com/HlVXaPK.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>





