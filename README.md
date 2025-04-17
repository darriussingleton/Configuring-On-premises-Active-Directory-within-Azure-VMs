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
        <strong>Virtual Machine:</strong> Once the Virtual network is created, Deploy a Windows Server 2022 virtual machine instance. This server will be the domain controller(dc-1) Must be created in the same resource group as the network.  The region and zone must be the same as the network created.
          <p>Enter a username and password to login into the domain controller. I used Username: labuser Password: Cyberlab123(for the purpose of this lab)</p>
      </li>
      <li>
        <strong>Domain Controller Role:</strong> Within the Azure console set Domain Controller's NIC Private IP address to be static. Then install and configure the Active Directory Domain Services role on the deployed virtual machine, promoting it to a Domain Controller. Be sure to disable the Windows firewall for testing connectivity.
      </li>
    </ul>
  </li>
</ol>
<p>  
</p>
<br />

<p>
<img src="https://i.imgur.com/6a25u7I.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<h2>Setting Up Client-1 Virtual Machine in Azure</h2>

<p>This section outlines the steps to create and configure a Windows 10 virtual machine named "Client-1" in Azure, connecting it to the same network as the Domain Controller (DC-1).</p>

<ul>
  <li>
    <h3>Create the Client VM (Client-1)</h3>
    <p>Deploy a Windows 10 virtual machine named "Client-1"</p>
    <ul>
      <li><strong>Username:</strong> fresh</li>
      <li><strong>Password:</strong> Cyberlab123!</li>
      <li><strong>Region:</strong> Same region as DC-1</li>
      <li><strong>Virtual Network:</strong> Same Virtual Network as DC-1</li>
    </ul>
  </li>
    <p>
    <img src="https://imgur.com/XJG87P1" height="80%" width="80%" alt="Disk Sanitization Steps"/>
    </p>
  <li>
    <h3>Configure DNS Settings</h3>
    <p>After the virtual machine is created, configure Client-1's DNS settings to point to the private IP address of DC-1.(critical for domain functionality). Setting Client-1’s DNS to DC-1’s Private IP is essential for domain authentication, Active Directory functionality, group policy updates, and proper internal resource resolution. Without this setting, Client-1 may fail to join the domain, authenticate users, or access shared network resources. 
  <p>
    <img src="https://imgur.com/vn23VhG" height="80%" width="80%" alt="Disk Sanitization Steps"/>
  </p>
  <p>
    <img src="https://imgur.com/ek5K6jV" height="80%" width="80%" alt="Disk Sanitization Steps"/>
  </p>
    <p>
    <img src="https://imgur.com/37BtlSn" height="80%" width="80%" alt="Disk Sanitization Steps"/>
    </p>

<h3>Restart Client-1</h3>
    <p>From the Azure Portal, restart the Client-1 virtual machine to apply the DNS settings.</p>
  </li>
  <li>
    <h3>Login and Verify Connectivity</h3>
    <p>Login to the Client-1 virtual machine using the provided credentials (fresh/Cyberlab123!).</p>
    <p>Open a command prompt or PowerShell window and attempt to ping the private IP address of DC-1.</p>
    <p><strong>Verification:</strong> Ensure the ping operation succeeds, indicating network connectivity.</p>
  </li>
  <p>
    <img src="https://imgur.com/IQRq0T5" height="80%" width="80%" alt="Disk Sanitization Steps"/>
    </p>
  <li>
    <h3>Verify DNS Configuration</h3>
    <p>From Client-1, open PowerShell and execute the command <code>ipconfig /all</code>.</p>
    <p><strong>Verification:</strong> Review the output and confirm that the DNS settings display the private IP address of DC-1. Running ipconfig /all in PowerShell helps verify Client-1’s network configuration, ensuring that:
It has the correct IP address, subnet mask, and default gateway.
It is using DC-1’s Private IP as its DNS server .
It is connected to the correct domain and can communicate with network resources.
If there are issues, this command is the first troubleshooting step in diagnosing network or Active Directory problems.</p>
  </li>
</ul>
<br />

<p>
<img src="https://imgur.com/nI5MDPc" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
  
