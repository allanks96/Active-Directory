<p align="center">
<img src="https://i.imgur.com/pU5A58S.png" alt="Microsoft Active Directory Logo"/>
</p>

<h1>Active Directory Deployed in the Cloud (Azure)</h1>
This tutorial outlines the implementation of on-premises Active Directory within Azure Virtual Machines.<br />


<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Active Directory Domain Services
- PowerShell

<h2>Operating Systems Used </h2>

- Windows Server 2022
- Windows 10 (21H2)

<h2>High-Level Deployment and Configuration Steps</h2>

- Step 1: Created two VM's in Azure. The first being the "Domain Controller" and the second being the "Client User".
- Step 2: Change the virtual NIC on the domain controller from dynamic to static so the IP address stays the same.
- Step 3: Ping from client 1 to test connectivity to domain controller with perpetual ping "-T"
- Step 4: Opened up the firewall in the domain controller to allow ICMP
- Step 5: Went to server manager on domain controller > clicked add on roles and features > Selected active directory domain services > installed > created a domain name > Installed > let computer refresh then log back in to the domain controller with the new doman specific prefix followed by \ (username)
- Step 6: Open my domain inside of users and comupters in AD and create two folders "_EMPLOYEES" and "_ADMINS" 
- Step 7: Created an official Admin user account to simulate admin personnel with the organization
- Step 8: Added user to the domain admin group
- Step 9: Logged out and logged back in as the admin user
- Step 10: Logged into client computer and renamed it to the domain of the domain controller. Settings > system > Rename this PC > click domain
- Step 11: Restart client VM > Get private IP address from domain controller > Go to client network settings > DNS settings > custom > Paste domain controller private NIC IP address
- Step 12: Join the domain on client computer with an admin account that was created
- Step 13: Add domain users as people to remote into desktop
- Step 14: Copied code into powershell (admin) to creaate multiple user profiles at once
- Step 15: Login into client computers with any user with the domain specific username "mydomain.com\(user)" 

<h2>Deployment and Configuration Steps</h2>

<p>
<img width="1433" alt="created 2 vm's" src="https://github.com/user-attachments/assets/b5a27305-55fd-4c3f-99a7-894795f90652">

</p>
<p>
Created two VM's in Azure. The first being the "Domain Controller" and the second being the "Client User".
</p>
<br />

<p>
  <img width="596" alt="switched IP address from static to dynamic" src="https://github.com/user-attachments/assets/4e9b27a4-6c75-405a-87ae-efe273b3a6a9">

</p>
<p>
Change the virtual NIC on the domain controller from dynamic to static so the IP address stays the same.
</p>
<br />

<p>
<img width="1436" alt="Allowed ping on DC 1" src="https://github.com/user-attachments/assets/0f533e83-425a-434d-b075-ea891df671c3">

</p>
<p>
Opened up the firewall in the domain controller to allow ICMP
</p>
<br />

<p>
<img width="1423" alt="Download AD domain services" src="https://github.com/user-attachments/assets/78c95db1-0123-4f36-a893-e07121b760e8">

</p>
<p>
Went to server manager on domain controller > clicked add on roles and features > Selected active directory domain services > installed > created a domain name > Installed > let computer refresh then log back in to the domain controller with the new doman
</p>
<br />

<p>
<img width="1111" alt="created admin and added them to admin group" src="https://github.com/user-attachments/assets/1e16bb1c-8dfc-45ba-94ea-799ef7211ff5">

</p>
<p>
Created an official Admin user account to simulate admin personnel with the organization and added user to the domain admin group
</p>
<br />

<p>
<img width="1430" alt="made C1 use DC DNS server" src="https://github.com/user-attachments/assets/7ab9287a-2ff5-4f8d-9585-a4e54c44d733">

</p>
<p>
Restart client VM > Get private IP address from domain controller > Go to client network settings in Azure > DNS settings > custom > Paste domain controller private NIC IP address
</p>
<br />

<p>
<img width="700" alt="renamed C1 computer to mydomain com" src="https://github.com/user-attachments/assets/4bf87de4-e137-45be-a726-ec981bb21dd8">

</p>
<p>
Logged into client computer and renamed it to the domain of the domain controller. Settings > system > Rename this PC > click domain
</p>
<br />

<p>
<img width="455" alt="added domain users as the security group that can login:remote into C1" src="https://github.com/user-attachments/assets/0e8cfa19-626b-4839-a880-9adc0a481834">

</p>
<p>
Add domain users as people to remote into desktop
</p>
<br />

<p>
<img width="1299" alt="copied code into p shell admin to create 1000 users " src="https://github.com/user-attachments/assets/f22c03c6-cfda-4451-88b4-496edf653f58">

</p>
<p>
Copied code into powershell (admin) to creaate multiple user profiles at once. With those users you're able to Log into client computers with the domain specific username "mydomain.com\(user)" 

</p>
<br />
