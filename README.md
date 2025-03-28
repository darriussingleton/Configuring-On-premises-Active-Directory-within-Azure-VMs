<p align="center">
<img src="https://miro.medium.com/v2/resize:fit:720/1*--RgGZA7dD7JUX7ZDwzG-g.png" alt="Microsoft Active Directory Logo"
    height="300"
  width="300"/>
</p>

<h1>On-premises Active Directory Deployed in the Cloud (Azure)</h1>
In this project I will be  preparing multiple environments using Microsoft Azure, to create a domain controller server and demonstrate how you can use the cloud to provision and use Active Directory and administrative tools. This will require deployments of Windows OS Virtual Environment(Client), a Windows Server 22 Datacenter (Domain Controller). Creating a  connection between the Windows Server VM (Domain Controller DC-1) and the Windows OS VM (Client-1). This connection will be established by setting the DCs (Domain Controllers) Private IP address to static and pointing the Windows OS Client-1 DNS Server to this Static Private IP of the DC.<br />


<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute, DNS, Networking)
- Remote Desktop
- Active Directory Domain Services
- PowerShell

<h2>Operating Systems Used </h2>

- Microsoft Azure Windows 10 Pro version 22H2 - x64 Gen2 Virtual Machine
- Microsoft Azure Windows Server 22 Datacenter: Azure Edition - x64 Gen2 Virtual Machine

<h2>List of Prerequisites</h2>

Microsoft Azure
Laptop or Desktop (works best)

<h2>Deployment and Configuration Steps</h2>
<p>
When working with in the Azure cloud one of the first steps you should always do is establish a resource. This allows you to see all your resource created in one place. Microsoft also mentions this a one of the best practices for managing resources. I created a resource group and  named  "ADpracticeLab"  
</p>

<p>
 Inside the created resource group you should deployed a Virtual network with subnets for the virtual machines. (a virtual network lets computers and devices talk to each other without needing physical cables, making IT networks more flexible, scalable, and efficient!).  
</p>
<br />

<p>
<img src="https://i.imgur.com/pERPKJA.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<h3>Domain Controller Virtual Machine Deployment</h3>
    <ul>
      <li>
        <strong>Virtual Machine:</strong> Deploy a Windows Server 2022 virtual machine instance.
      </li>
      <li>
        <strong>Domain Controller Role:</strong> Install and configure the Active Directory Domain Services role on the deployed virtual machine, promoting it to a Domain Controller.
      </li>
    </ul>
  </li>
</ol>
<p>
Once the Virtual network is created, deploy a Virtual machine. Be sure to choose the resource group you the windows server virtual machine in azure, inside the "Active-Directory-Lab" resource group for unified deployment, organization as well as easier management.   
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





