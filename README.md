
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

Open Remote Desktop Connection and log into DC.
<img width="807" alt="RDC-dc-1" src="https://github.com/user-attachments/assets/ae26ab94-3fd8-455e-b432-699b27aa6ba4" />

Open Server Manager, select Add roles and features, and install Active Directory Domain Services (AD DS).
<img width="1156" alt="1servermanager" src="https://github.com/user-attachments/assets/f40d227a-e1af-4254-b512-59b87ac18369" />
<img width="410" alt="2" src="https://github.com/user-attachments/assets/11cde674-9bda-4277-8de3-c83b9d18ecce" />
<img width="410" alt="3" src="https://github.com/user-attachments/assets/373aa58c-923b-4f3e-a5dc-5cb80542e85b" />
<img width="500" alt="4" src="https://github.com/user-attachments/assets/43b290b9-0a59-4416-b013-32f1265712cf" />
<img width="500" alt="5" src="https://github.com/user-attachments/assets/2016f373-7a5c-46e6-a9c0-2466fa6825f1" />
<img width="500" alt="6" src="https://github.com/user-attachments/assets/da3e04c2-92a5-4bfa-b366-0fbb4fff5764" />
<img width="500" alt="7" src="https://github.com/user-attachments/assets/b9b3403c-3881-4988-87b4-7754af1aec60" />
<img width="500" alt="8" src="https://github.com/user-attachments/assets/49132580-e72c-4365-b7db-66b133cfafbb" />

<h3> 2️⃣ Promote DC to a Domain Controller </h3>

This establishes the server as the central point for managing users, devices, and security within the network.
<img width="300" alt="9" src="https://github.com/user-attachments/assets/dfb0af6e-65a0-4ac9-b0ab-2f6d18ed5be1" />

Create a new forest using a domain name like mydomain.com.

An Active Directory forest is the highest level of organization within Active Directory.

<img width="500" alt="10" src="https://github.com/user-attachments/assets/ebc1ef31-840b-466d-8d1d-57ad9e166d96" />
<img width="500" alt="11" src="https://github.com/user-attachments/assets/adfc3826-1a44-4fe3-a33e-cf9b47046d4a" />
<img width="500" alt="12" src="https://github.com/user-attachments/assets/26be85a2-0f07-4be3-96f1-8a29aaed8ea3" />
<img width="500" alt="13" src="https://github.com/user-attachments/assets/ad70bbca-c61c-41ef-ad7f-ee11c61ee04e" />
<img width="500" alt="14" src="https://github.com/user-attachments/assets/4b9c4a85-f63d-4cd5-a330-e7f20b20956e" />
<img width="500" alt="15" src="https://github.com/user-attachments/assets/7623a080-1762-4959-b1f0-71ea747c84c2" />
<img width="500" alt="16" src="https://github.com/user-attachments/assets/959da2e1-81ab-4a55-877c-da306671a961" />




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
