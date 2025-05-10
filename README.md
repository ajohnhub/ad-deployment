<p align="center">
<img src="https://i.imgur.com/pU5A58S.png" alt="Microsoft Active Directory Logo"/>
</p>

<h1>Active Directory Infrastructure in Microsoft Azure</h1>
This walkthrough demonstrates how to set up Active Directory infrastructure in Microsoft Azure.  <br />


<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Active Directory Domain Services
- PowerShell

<h2>Operating Systems Used </h2>

- Windows Server 2022
- Windows 10 (21H2)


<h2>Deployment and Configuration Steps</h2>

<p>
</p>
<p>
In this lab, we will create two VMs in the same VNET. One will be a Domain Controller, and the other, a Client machine. We will change the DC to a static IP because it offers Active Directory services to the client machine. The client machine will be joined to the domain. We will control the DNS settings on the client machine; the client machine will use the DC as its DNS server. 

<br />
<p>
<img src="https://github.com/user-attachments/assets/21758e18-04c1-44f9-91a4-f4f71ca5b3e7" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
First, we will set up a Domain Controller in Azure.
Create a Resource Group.
Create a Virtual Network and Subnet.
Create the Domain Controller VM (Windows Server 2022) named “DC-1”.
Create the Client VM (Windows 10) named “Client-1”.
 
<img src="https://github.com/user-attachments/assets/0afbad48-3307-42c0-b945-4f65defe7ddc" height="60%" width="60%" alt="Disk Sanitization Steps"/>


</p>
<br />

<p>After the VMs are created, set the Domain Controller’s NIC Private IP address to be static and set Client-1’s DNS settings to DC-1’s Private IP address.

<img src="https://github.com/user-attachments/assets/8a008f4b-bbad-421d-9f99-493add5b9f2d" height="60%" width="60%" alt="Disk Sanitization Steps"/>
</p>
<img src="https://github.com/user-attachments/assets/d23d9313-72bf-4c85-8824-2dc9cbd33400" height="60%" width="60%" alt="Disk Sanitization Steps"/>
<p>
Log in to the Domain Controller VM and disable the Windows Firewall (for testing connectivity)
</p>
<img src="https://github.com/user-attachments/assets/7ef01efa-e55d-4985-84fa-8ceccd5b13f0" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<img src="https://github.com/user-attachments/assets/8e989d6e-f190-4856-bab0-5ef399161bed"
height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
</p>
From the Azure Portal, restart Client-1 and
Log in to Client-1. Next, attempt to ping DC-1’s private IP address. Ensure that the ping succeeded.

</p>
<img src="https://github.com/user-attachments/assets/4705220b-4a4e-4dc4-acd3-f6da854d73e4"
height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
</p>

From Client-1, open PowerShell and run ipconfig /all.
The output for the DNS settings should show DC-1’s private IP Address.

</p>
<img src="https://github.com/user-attachments/assets/e253735a-e17f-41bc-b4d1-ae4a59d48d64" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
</p>

