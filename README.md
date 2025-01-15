<p align="center">
<img src="https://i.imgur.com/pU5A58S.png" alt="Microsoft Active Directory Logo"/>
</p>

<h1>On-premises Active Directory Deployed in the Cloud (Azure)</h1>

<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Active Directory Domain Services
- PowerShell

<h2>Operating Systems Used </h2>

- Windows Server 2022
- Windows 10 (21H2)

<h2>High-Level Deployment and Configuration Steps</h2>

- Step 1: Set Up the Azure Environment
Provision Azure Virtual Machines:
Deploy at least two VMs: one for the domain controller (DC) and others for client or application servers.
Ensure VMs are in the same virtual network (VNet) for connectivity.
Configure Networking:
Set up a subnet for the VMs.
Assign static private IP addresses to the VM designated as the domain controller.
Configure network security groups (NSGs) to allow required traffic (e.g., port 3389 for RDP, 53 for DNS, and 135-139, 445 for AD traffic).

- Step 2: Configure the Domain Controller
Install Active Directory Domain Services (AD DS):
Log into the designated domain controller VM via RDP.
Open Server Manager, and use the Add Roles and Features Wizard to install the AD DS role.
Promote the Server to a Domain Controller:
Run the AD DS Configuration Wizard to create a new forest and domain.
Specify the domain name (e.g., example.local).
Set the Directory Services Restore Mode (DSRM) password.
Restart the server to apply changes.

- Step 3: Configure DNS and Join Client VMs to the Domain
Configure DNS:
Verify that the domain controller is running the DNS service.
Update the Azure VNet DNS settings to point to the private IP of the domain controller VM.
Ensure the domain controller's IP is the primary DNS for all VMs in the VNet.
Join Client VMs to the Domain:
Log into each client VM via RDP.
Update the TCP/IP settings to use the domain controller's IP as the DNS server.
Go to System Properties → Computer Name → Change → Domain → Enter the domain name (e.g., example.local) → Provide domain admin credentials.

- Step 4: Test and Secure the Deployment
Verify Domain Services:
Use tools like Active Directory Users and Computers (ADUC) to manage users, groups, and organizational units (OUs).
Test domain authentication by logging into client VMs using domain accounts.
Secure the Environment:
Implement Azure Bastion or VPN Gateway for secure RDP access.
Configure NSG rules to limit access to domain services.
Regularly back up the domain controller using Azure Backup or other backup tools.

<h2>Deployment and Configuration Steps</h2>

<p>
<img width="542" alt="image" src="https://github.com/user-attachments/assets/a2e5cdad-4888-4a9e-9da6-c886d59e17aa" />

</p>
<p>
</p>
<br />
__________________________________________________________________________________________________________________________________________


![Screenshot 2025-01-14 190543](https://github.com/user-attachments/assets/f6a12c6f-4d0e-4816-829c-d4fb719e0a15)

<p>

![Screenshot 2025-01-14 190613](https://github.com/user-attachments/assets/81c6c188-0409-4238-90b9-325bad38c102)

<br />
___________________________________________________________________________________________________________________________________________

![Screenshot 2025-01-14 191057](https://github.com/user-attachments/assets/bb359f2d-c115-4d94-8413-bd6449285650)

<p>
</p>
<br />
____________________________________________________________________________________________________________________________________________

<img width="724" alt="image" src="https://github.com/user-attachments/assets/f9499adb-2a53-4743-bc4d-52640a259213" />
