<p align="center">
<img src="https://i.imgur.com/pU5A58S.png" alt="Microsoft Active Directory Logo"/>
</p>

<h1>Active Directory Infrastructure in Microsoft Azure</h1>
This walkthrough demonstrates how to deploy Active Directory in Microsoft Azure.  <br />


<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Active Directory Domain Services
- PowerShell

<h2>Operating Systems Used </h2>

- Windows Server 2022
- Windows 10 (21H2)


<h2>Deployment Steps</h2>

<p>
</p>
<p>
Log in to DC-1 and install Active Directory Domain Services.
Promote as a DC: Set up a new forest as mydomain.com (can be anything, just remember what it is). 

<br />
<p>
<img src="https://github.com/user-attachments/assets/c791fdf1-8d3a-406d-9f18-3d360d33bf82" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<img src="https://github.com/user-attachments/assets/901afe72-cb27-4da0-874e-0b4cc5de719d" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Restart and then log back into DC-1 as user: mydomain.com\labuser
 
<img src="https://github.com/user-attachments/assets/1a3836d6-1467-41a5-8e5c-cdb1a207a685" height="60%" width="60%" alt="Disk Sanitization Steps"/>


</p>
<br />

<p>In Active Directory Users and Computers (ADUC), create an Organizational Unit (OU) called “_EMPLOYEES”. Then, create another OU named “_ADMINS”.


<img src="https://github.com/user-attachments/assets/d0004016-32a4-4e9f-a7af-d131daf5cf3b" height="60%" width="60%" alt="Disk Sanitization Steps"/>
</p>
<img src="https://github.com/user-attachments/assets/0330c5b1-e2a8-439a-b9db-0703bca64b19" height="60%" width="60%" alt="Disk Sanitization Steps"/>
<p>
Create a new employee named “Jane Doe” (same password) with the username of “jane_admin” / Cyberlab123! Next, add jane_admin to the “Domain Admins” Security Group

</p>
<img src="https://github.com/user-attachments/assets/b5a101c6-6f57-4063-9aa5-fa801143d004" height="80%" width="80%" alt="Disk Sanitization Steps"/>

<br />
</p>
Log out / close the connection to DC-1 and log back in as “mydomain.com\jane_admin”. User jane_admin as your admin account from now on.


</p>
<img src="https://github.com/user-attachments/assets/86cc9285-140b-476d-ab95-35291b13bed8"
height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
</p>

Login to Client-1 as the original local admin (labuser) and join it to the domain (computer will restart)

</p>
<img src="https://github.com/user-attachments/assets/3d455c42-ab07-48ba-9fa5-a333b2c60f5b" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<img src="https://github.com/user-attachments/assets/ea9b43cd-1b20-4db8-89bd-c32cd45cb3c1" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
</p>

Login to the Domain Controller and verify Client-1 shows up in ADUC. Then, create a new OU named “_CLIENTS” and drag Client-1 into there.


</p>
<img src="https://github.com/user-attachments/assets/b1705253-4f2c-4094-9969-d72093a6bbca" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<img src="https://github.com/user-attachments/assets/0cdcca07-f0cd-4104-a482-945476ab3c9b" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
</p>



