
<p align="center">
<img src="https://i.imgur.com/pU5A58S.png" alt="Microsoft Active Directory Logo"/>
</p>

<h1>Active Directory Deployment in Azure</h1>
This project demonstrates how to build a complete Active Directory infrastructure in Microsoft Azure, replicating an on-premises environment entirely in the cloud. By leveraging Azure virtual machines, we deploy and configure Active Directory Domain Services to establish centralized management of users, devices, and security. The setup highlights how to organize network resources with Organizational Units, enforce domain-level authentication, and support large-scale deployments by automating the creation of thousands of user accounts via Powershell. This showcases the ease and flexibility of running enterprise-grade directory services in a fully virtualized Azure environment.

<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop Connection
- Active Directory Domain Services
- PowerShell

<h2>Operating Systems Used </h2>

- Windows Server 2022 Datacenter: Azure Edition - x64 Gen2
- Windows 10 Pro, version 22H2 - x64 Gen2

<h2> Prerequisites </h2>

  - [Active Directory Infrastructure Setup in Azure](https://github.com/nikocapp56/Active-Directory-Infrastructure-Setup-in-Azure)
 
<h2>Deployment and Configuration Steps</h2>

<h3> 0️⃣ Overview of Active Directory Deployment </h3>

In this walkthrough, we will:
- Install Active Directory Domain Services.
- Promote the DC VM to a Domain Controller, creating a new forest (mydomain.com) that becomes the main authority for controlling user accounts, authentication, and access to network resources.
- Create Organizational Units (_EMPLOYEES, _ADMINS, _CLIENTS) and a domain admin user to organize and control our directory environment.
- Join the Windows 10 client VM to the domain, connecting it to our new Active Directory infrastructure.
- Configure Remote Desktop to allow standard domain user access.
- Use a PowerShell script to generate thousands of employee accounts, then test by logging into the client as one of these users to verify domain authentication.

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

This establishes the server as the central point for managing user accounts, security policies, and authentication across the domain.

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
<img width="809" alt="RDC-domain-dc-1" src="https://github.com/user-attachments/assets/70e87bdf-659e-4a2e-bd72-63ac2c5d9edb" />

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
This makes it so that Jane has full administrative privileges across the domain.
</p>
<img width="442" alt="24" src="https://github.com/user-attachments/assets/4175f30d-fe5b-420f-9608-8a14a17db06c" />
<img width="315" alt="25" src="https://github.com/user-attachments/assets/d90d3b33-86cf-40f8-a6c2-dcd55291d015" />
<img width="400" alt="26" src="https://github.com/user-attachments/assets/9f409b02-e451-4153-897f-f6dd08e68091" />
<img width="400" alt="27" src="https://github.com/user-attachments/assets/5551defc-4f4b-4925-a85a-5b52fdec642f" />
<img width="338" alt="28" src="https://github.com/user-attachments/assets/55f3e25c-7529-443c-99fa-c979d87fc8d0" />

Log out of DC.

<h3> 5️⃣ Join Client to the domain </h3>

Log into Client as the local user

<img width="806" alt="RDC-client-1" src="https://github.com/user-attachments/assets/1ec7227c-01b7-4774-9c02-4436f44c8f64" />
</p>
Go to System Settings -> About -> Rename this PC (Advanced)
</p>
<img width="548" alt="29" src="https://github.com/user-attachments/assets/562fb705-627c-4c94-804e-38b18890a7bf" />
</p>
Join the computer to the domain mydomain.com
</p>
<img width="400" alt="30" src="https://github.com/user-attachments/assets/e4327dd6-4ba4-48b2-8603-5ff3b51056d1" />
<img width="260" alt="31" src="https://github.com/user-attachments/assets/728a557e-c57e-4322-bfcb-5fb89aef0824" />
</p>
Use jane_admin login credentials to join the domain.
</p>
Restart when prompted.
</p>
<img width="300" alt="32" src="https://github.com/user-attachments/assets/a9faff12-7bc7-4886-b5cb-4201638ef89f" />
<img width="250" alt="33" src="https://github.com/user-attachments/assets/b0e6c77f-4fb9-46f4-b24f-e640f70328d8" />
<img width="250" alt="34" src="https://github.com/user-attachments/assets/2398a75c-a83f-49c4-9d96-29cc4aa48c54" />

<h3> 6️⃣ Verify that Client shows up in Active Directory Users and Computers </h3>

Log back into DC as mydomain.com\jane_admin. Use this admin account for all domain administration going forward.

<img width="806" alt="RDC-jane-domain-dc-1" src="https://github.com/user-attachments/assets/1c1b7d3d-3db9-4703-8055-8f35969393ad" />

Open Active Directory Users and Computers.

<img width="298" alt="18" src="https://github.com/user-attachments/assets/f6b7275d-36ff-4d63-b6ea-544575f2f99a" />

Within the domain, create an Organizational Unit named _CLIENTS and drag Client into it.

<img width="397" alt="35" src="https://github.com/user-attachments/assets/e57a3f7b-a6e6-4016-a19a-d5d366d4c290" />
<img width="370" alt="36" src="https://github.com/user-attachments/assets/ad8f1769-47ac-48cf-be74-e27d3fb496dc" />
<img width="750" alt="37" src="https://github.com/user-attachments/assets/2c9a56b2-2ea8-4ed4-8ea2-df479e3fed01" />

<h3> 7️⃣ Allow domain users to access remote desktop on Client </h3>

Log into Cient as mydomain.com\jane_admin

<img width="802" alt="RDC-jane-domain-client-1" src="https://github.com/user-attachments/assets/8beab503-d497-48d5-96d4-46f4c3f61d1a" />
</p>
Go to System Settings -> About -> Remote Desktop
</p>
<img width="550" alt="38" src="https://github.com/user-attachments/assets/cf7ba50a-060a-42bd-b160-5c981d8d1cae" />
<img width="307" alt="39" src="https://github.com/user-attachments/assets/d474bc13-1c0b-4d9d-b3f4-a92a79430f80" />
<img width="300" alt="40" src="https://github.com/user-attachments/assets/c1cb0abb-fe2c-471f-88d9-7c688751e352" />
<img width="400" alt="41" src="https://github.com/user-attachments/assets/2b94735d-6e47-42a4-a77d-224e941f0883" />
<img width="300" alt="42" src="https://github.com/user-attachments/assets/f73a9bb4-f535-4c52-ac4e-c8ff0796e761" />

This ensures standard domain users can sign in via Remote Desktop.

Log out of Client.

<h3> 8️⃣ Create additional employee users and test logging into Client with one of the users </h3>

Run PowerShell ISE as an administrator.

<img width="148" alt="43" src="https://github.com/user-attachments/assets/c68f8fdf-61f0-4b85-8845-101eddafacab" />

### [User Creation Script](https://github.com/joshmadakor1/AD_PS/blob/master/Generate-Names-Create-Users.ps1) 
This script will create 10,000 employee user accounts and store them in the _EMPLOYEES Organizational Unitin Active Directory Users and Computers.

Create a new file in PowerShell ISE, then paste the contents of the user creation script into it.

Run the script and observe the accounts in the appropriate Organizational Unit (_EMPLOYEES).

<img width="829" alt="44" src="https://github.com/user-attachments/assets/40adb1d1-9f06-45d1-9557-ffad9173ff1b" />
<img width="1138" alt="45" src="https://github.com/user-attachments/assets/89746e6f-8134-4ae9-a70d-8d41657dfdd1" />

Return to Client and attempt to log in as one of the newly created users using the password you set before (Password1).
Verify that login succeeds, demonstrating that domain authentication is working properly.

<img width="805" alt="RDC-cip dep-domain-client-1" src="https://github.com/user-attachments/assets/3652e674-6e04-4c6a-98de-ea3198524e54" />
