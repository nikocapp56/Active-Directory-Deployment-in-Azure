
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
<img width="412" alt="2" src="https://github.com/user-attachments/assets/11cde674-9bda-4277-8de3-c83b9d18ecce" />
<img width="412" alt="3" src="https://github.com/user-attachments/assets/373aa58c-923b-4f3e-a5dc-5cb80542e85b" />
<img width="412" alt="4" src="https://github.com/user-attachments/assets/43b290b9-0a59-4416-b013-32f1265712cf" />
<img width="412" alt="5" src="https://github.com/user-attachments/assets/2016f373-7a5c-46e6-a9c0-2466fa6825f1" />
<img width="412" alt="6" src="https://github.com/user-attachments/assets/da3e04c2-92a5-4bfa-b366-0fbb4fff5764" />
<img width="412" alt="7" src="https://github.com/user-attachments/assets/b9b3403c-3881-4988-87b4-7754af1aec60" />
<img width="412" alt="8" src="https://github.com/user-attachments/assets/49132580-e72c-4365-b7db-66b133cfafbb" />

<h3> 2️⃣ Promote DC to a Domain Controller </h3>

This establishes the server as the central point for managing users, devices, and security within the network.

<img width="300" alt="9" src="https://github.com/user-attachments/assets/dfb0af6e-65a0-4ac9-b0ab-2f6d18ed5be1" /> 
</p>
Create a new forest using a domain name like mydomain.com.
</p>
An Active Directory forest is the highest level of organization within Active Directory. Creating a new forest sets up a completely separate Active Directory environment with its own domain structure and security boundaries. It serves as the overall framework for managing all network resources and identities within an organization.
</p>
When asked for the Directory Services Restore Mode (DSRM) password, just set it to Password1 and continue.
</p>
<img width="412" alt="10" src="https://github.com/user-attachments/assets/ebc1ef31-840b-466d-8d1d-57ad9e166d96" />
<img width="412" alt="11" src="https://github.com/user-attachments/assets/adfc3826-1a44-4fe3-a33e-cf9b47046d4a" />
<img width="412" alt="12" src="https://github.com/user-attachments/assets/26be85a2-0f07-4be3-96f1-8a29aaed8ea3" />
<img width="412" alt="13" src="https://github.com/user-attachments/assets/ad70bbca-c61c-41ef-ad7f-ee11c61ee04e" />
<img width="412" alt="14" src="https://github.com/user-attachments/assets/4b9c4a85-f63d-4cd5-a330-e7f20b20956e" />
<img width="412" alt="15" src="https://github.com/user-attachments/assets/7623a080-1762-4959-b1f0-71ea747c84c2" />
<img width="412" alt="16" src="https://github.com/user-attachments/assets/959da2e1-81ab-4a55-877c-da306671a961" />

<h3> 3️⃣ Allow server to restart and log back into DC using the domain format: mydomain.com\username </h3>

This confirms the server is now part of the new domain.

<img width="809" alt="17" src="https://github.com/user-attachments/assets/7f1b5078-0c5d-42db-9bed-dd7593a9ab3b" />
<img width="809" alt="RDC-domain-dc-1" src="https://github.com/user-attachments/assets/9d25ae70-3f49-4a64-bf67-a3e1f107ae48" />

<h3> 4️⃣ Create Organizational Units and a Domain Admin user </h3>

Open Active Directory Users and Computers (ADUC).

<img width="298" alt="18" src="https://github.com/user-attachments/assets/405b2cc0-7868-434e-b845-58c6a6923c47" />

Within the domain,
  - Create an Organizational Unit named _EMPLOYEES.
  - Create an Organizational Unit named _ADMINS.

<img width="660" alt="19" src="https://github.com/user-attachments/assets/04d05457-82e1-4260-a97c-de0076f32194" />
<img width="394" alt="20" src="https://github.com/user-attachments/assets/b6b2bf23-930c-473a-8a14-a86a5478575e" />
<img width="392" alt="21" src="https://github.com/user-attachments/assets/bc707d9b-f2b1-4b34-8646-80ac7a94cf4b" />
</p>
Inside _ADMINS, create a new user: jane_admin

<img width="863" alt="22" src="https://github.com/user-attachments/assets/fba41636-b9e7-4b03-9a4b-bf3bb3a261e7" />
<img width="400" alt="22 5" src="https://github.com/user-attachments/assets/c281984e-8369-4d4f-b2b2-62dae4195b3a" />
<img width="400" alt="23" src="https://github.com/user-attachments/assets/3f42a5a5-0dcf-454f-af07-5c8feac993ef" />
</p>
Add jane_admin to the “Domain Admins” Security Group.
</p>
This makes it so that she has full administrative privileges across the domain.
</p>
<img width="442" alt="24" src="https://github.com/user-attachments/assets/4175f30d-fe5b-420f-9608-8a14a17db06c" />
<img width="315" alt="25" src="https://github.com/user-attachments/assets/d90d3b33-86cf-40f8-a6c2-dcd55291d015" />
<img width="400" alt="26" src="https://github.com/user-attachments/assets/9f409b02-e451-4153-897f-f6dd08e68091" />
<img width="400" alt="27" src="https://github.com/user-attachments/assets/5551defc-4f4b-4925-a85a-5b52fdec642f" />
<img width="338" alt="28" src="https://github.com/user-attachments/assets/55f3e25c-7529-443c-99fa-c979d87fc8d0" />

<h3> 5️⃣ Create Organizational Units and a Domain Admin user </h3>
