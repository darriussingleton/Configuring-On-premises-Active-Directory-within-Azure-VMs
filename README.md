<p align="center">
<img src="https://miro.medium.com/v2/resize:fit:720/1*--RgGZA7dD7JUX7ZDwzG-g.png" alt="Microsoft Active Directory Logo"
    height="300"
  width="300"/>
</p>

<h1>On-premises Active Directory Deployed in the Cloud (Azure)</h1>
This tutorial outlines the implementation of on-premises Active Directory within Azure Virtual Machines.<br />


<h2>Video Demonstration</h2>

- ### [YouTube: How to Deploy on-premises Active Directory within Azure Compute](https://www.youtube.com)

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
- Setup Client-1 in Azure
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
<img src="https://i.imgur.com/5wLc5pJ.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>

Created and deployed the Vnet for the virtual machines in azure, inside the "Active-Directory-Lab" resource group (a virtual network lets computers and devices talk to each other without needing physical cables, making IT networks more flexible, scalable, and efficient!).


Disk Sanitization Steps

Created and deployed the windows server virtual machine in azure, inside the "Active-Directory-Lab" resource group for unified deployment, organization as well as easier management.


Disk Sanitization Steps

Created and deployed the windows 10 virtual machine in azure, inside the "Active-Directory-Lab" resource group for unified deployment, organization as well as easier management.


Disk Sanitization Steps

Setting Client-1’s DNS to DC-1’s Private IP is essential for domain authentication, Active Directory functionality, group policy updates, and proper internal resource resolution. Without this setting, Client-1 may fail to join the domain, authenticate users, or access shared network resources.


Disk Sanitization Steps

Running ipconfig /all in PowerShell helps verify Client-1’s network configuration, ensuring that: It has the correct IP address, subnet mask, and default gateway. It is using DC-1’s Private IP as its DNS server (critical for domain functionality). It is connected to the correct domain and can communicate with network resources. If there are issues, this command is the first troubleshooting step in diagnosing network or Active Directory problems.


Disk Sanitization Steps Disk Sanitization Steps Disk Sanitization Steps Disk Sanitization Steps

Installing Active Directory Domain Services (AD DS) is essential for managing a Windows-based IT infrastructure. It centralizes user authentication, security, and resource management, making IT operations more secure, efficient, and scalable.


Disk Sanitization Steps Disk Sanitization Steps Disk Sanitization Steps



Creating a Domain Admin user is a best practice in Active Directory management. It ensures secure administration, prevents unauthorized changes, and allows IT teams to efficiently manage the domain.
Disk Sanitization Steps Disk Sanitization Steps Disk Sanitization Steps

Joining Client-1 to mydomain.com ensures centralized management, security, and access control in an enterprise IT environment. It simplifies user authentication, IT administration, and resource access, making it a best practice for businesses.


Disk Sanitization Steps Disk Sanitization Steps Disk Sanitization Steps

Setting up Remote Desktop for non-admin users on Client-1 allows IT staff and employees to securely access workstations remotely without giving unnecessary admin rights. This improves security, efficiency, and IT management while preventing unauthorized system modifications.


Disk Sanitization Steps Disk Sanitization Steps Disk Sanitization Steps

Creating additional users and testing login ensures that domain authentication is working properly. This step is crucial for verifying Active Directory setup, user permissions, and network policies, which are essential for managing an IT environment effectively.

