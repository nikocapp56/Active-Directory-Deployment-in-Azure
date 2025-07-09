
<p align="center">
<img src="https://i.imgur.com/pU5A58S.png" alt="Microsoft Active Directory Logo"/>
</p>

<h1>Active Directory Deployment in Azure</h1>
This tutorial outlines the implementation of on-premises Active Directory within Azure Virtual Machines.<br />

<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop Connection
- Active Directory Domain Services
- PowerShell

<h2>Operating Systems Used </h2>

- Windows Server 2022 Datacenter: Azure Edition - x64 Gen2
- Windows 10 Pro, version 22H2 - x64 Gen2

<h2>Deployment and Configuration Steps</h2>

<h3> 0️⃣ Overview of AD Deployment </h3>


<h3> 1️⃣ Install Active Directory Domain Services </h3>

Open Remote Desktop Connection.

Enter DC’s public IP address and log in.

Open Server Manager, select Add roles and features, and install Active Directory Domain Services (AD DS).

<h3> 2️⃣ Promote this server to a Domain Controller: Create a new forest using a domain name like mydomain.com.</h3>

An Active Directory forest is the highest level of organization within Active Directory.


<h3> 3️⃣ Allow server to restart and log back into DC using the domain format: mydomain.com/username
<img width="801" alt="azure" src="https://github.com/user-attachments/assets/f81c6800-45ef-4c8d-be3c-1f2bde5a0e9c" />

<img width="539" alt="resourcegroup" src="https://github.com/user-attachments/assets/fe39fb40-c24b-4cd9-898c-d6225b75d3cd" />

<img width="557" alt="vnet" src="https://github.com/user-attachments/assets/23e03380-e422-4080-85b6-0c52e51fc28f" />

<img width="457" alt="dc-1" src="https://github.com/user-attachments/assets/b60ef10f-8580-45a2-ad27-1d0e797c7ff8" />

<img width="454" alt="client-1" src="https://github.com/user-attachments/assets/ccb69a2a-feaa-498b-85ab-29d5cd941232" />

<img width="475" alt="vmsize,password,licensing" src="https://github.com/user-attachments/assets/d5637f58-db61-47a7-adc8-29ce88bf8d13" />
</p>
<img width="622" alt="dc-1static" src="https://github.com/user-attachments/assets/f5c7c345-c953-45e0-9470-95ac16c70518" />

<img width="530" alt="client-1dnsserver" src="https://github.com/user-attachments/assets/4b613a8d-545f-480e-92b2-9780598352fd" />

<img width="818" alt="client-1restart" src="https://github.com/user-attachments/assets/affe18e4-5e96-4acb-8801-271db9f81adc" />

<img width="807" alt="RDC-dc-1" src="https://github.com/user-attachments/assets/3ae1e24f-31ff-4da4-a332-04beb9d23077" />

<img width="782" alt="firewalloff" src="https://github.com/user-attachments/assets/845b2379-607c-4c8d-adb1-f07b661de9ce" />

<img width="806" alt="RDC-client-1" src="https://github.com/user-attachments/assets/1d221b42-b5d9-4b76-bfcf-542027fcd485" />

<p>
Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.
</p>
<br />

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.
</p>
<br />

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.
</p>
<br />
