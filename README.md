# Creating-Virtual-Machines-Virtual-Networks-and-Domain-Controllers


## Objective
Using Microsoft Azure we are going to create a Virtual Machine(s) (VM's), Virtual Network (VNet), and a Domain Controller (DC).



---

## Environments and Technologies Used
- Microsoft Azure



Note
- This example will use a previously created Microsoft Azure account, subscription, and resource group.

---

## Operating System
- This breakdown is created using Windows platform.

---

## Creating Our Virtual Network

<p>
For sake of ease, we will create our Virtual Network first. However it should be noted that VM's can have their network changed after the VM is already created
</p>
<br />

<p>
<img width="1678" height="870" alt="image" src="https://github.com/user-attachments/assets/20d1ab9e-b272-4de6-8910-c23a23ab4811" />
</p>
<p>
Navigate to your "Virtual Networks" from the Microsoft Azure Portal. This can be done either by the search bar at the top, or the drop down menu on the left. Click "Create".
</p>
<br />

<p>
<img width="1065" height="626" alt="image" src="https://github.com/user-attachments/assets/22876f7f-7ecf-41bd-864f-c449a176ade3" />
</p>
<p>
To create your Virtual Network simply add to your existing resource group, name the network, and select your region. Click "Review + Create" followed by "Create".
</p>
<br />

## Creating our Virtual Machine(s)

<p>
<img width="1507" height="797" alt="image" src="https://github.com/user-attachments/assets/00189fa6-eb85-4dfc-9e03-af186a3b3f15" />

</p>
<p>
To begin, we will access the Microsoft Azure page, and navigate to virtual machines. This can be done either by the search bar at the top, or the drop down menu. Once there, click "Create", then select "Virtual Machine".
</p>
<br />

<p>
<img width="1061" height="820" alt="image" src="https://github.com/user-attachments/assets/f70bb4d1-6fcd-42c4-a740-dcefe1d8f379" />
<img width="1113" height="693" alt="image" src="https://github.com/user-attachments/assets/91195679-053e-4cfd-b3b1-5052cb4938d7" />
<img width="630" height="114" alt="image" src="https://github.com/user-attachments/assets/f608d5a8-3206-41f0-bc06-83d4a4d4b73c" />
</p>
<p>
Now you will select your resource group, and name your virtual machine. Pay close attention to what operating system you are putting on the machine as well as  the "size" of the machine. Create Username, and password, and be sure to select the licensing box at the bottom. From here we click "next" until we reach the Networking page.
</p>
<br />

<p>
<img width="1232" height="717" alt="image" src="https://github.com/user-attachments/assets/749edb4f-1e6e-4042-b3d0-d4c1ae86b01b" />

</p>
<p>
Ensure your virtual machine is on the virtual network you created earlier. Click "Review + Create" followed by "Create". 
</p>
<br />



<p>
<img width="656" height="380" alt="image" src="https://github.com/user-attachments/assets/563503e6-0962-478b-a6ff-897532d7614d" />
</p>
<p>
Repeat this series of steps at least one more time, or until you have achieved the number of virtual machines desired.
</p>
<br />

# Creating Domain Controller

<p>
<img width="1087" height="707" alt="image" src="https://github.com/user-attachments/assets/86b87fdd-918f-4aa3-b6ab-54c1066621cd" />
</p>
<p>
This portion is largely the same as "Creating Our Virtual Machine(s)" There is one very important note here: when we go to select "Image" you must make sure to select a datacenter or equivelant to i.e. Windows Server 2022 Datacenter: Azure Edition Hotpatch - x64 Gen2
</p>
<br />

---
## This completes the creation of Virtual Machine(s), Virtual Network, and Domain Controller

<p align="center">
<img src="https://i.imgur.com/pU5A58S.png" alt="Microsoft Active Directory Logo"/>
</p>

<h1>Active Directory, Account Management, Security Policy Enforcement</h1>
This project demonstrates hands on implementation of user account management and security policy enforcement within an Active Directory environment using Windows Server.
Core administrative tasks included configuring account lockout policies through Group Policy, managing user account states, and resolving authentication related incidents such as account lockouts and credential resets.


## Environments and Technologies Used

- Microsoft Azure
- Remote Desktop
- Active Directory Domain Services
- PowerShell

<h2>Operating Systems Used </h2>

- Windows Server 2022
- Windows 10

<h2>Objectives</h2>

- Set lockout policies
- Simulate account lockout
- Simulate account lockout resolution

<h2>Deployment and Configuration Steps</h2>

## Install Active Directory on Domain Controller

<p>
<img width="1496" height="799" alt="image" src="https://github.com/user-attachments/assets/40944d50-b09b-4a97-92fe-a89c0a799a8d" />
</p>
<p>
Assuming our VM does not have Active Directory installed, we will install via the server manager. Once installed promote this VM to Domain Controller through server manager. I will also create a server admin account to act as.
</p>
<br />

## Adding a "Client" VM to the domain

<p>
<img width="1080" height="353" alt="image" src="https://github.com/user-attachments/assets/8d6adf25-103e-45c0-a705-4e7b505617d4" />

</p>
<p>
In a previous session, we already joined "Client" VM to the domain. This was done by setting the VM's DNS settings to our Domain Controllers private I.P. address, and joining the domain through system settings.
</p>
<br />

<p>
<img width="874" height="590" alt="image" src="https://github.com/user-attachments/assets/9c9e9a76-b920-41f4-8794-67028853e1e4" />
</p>
<p>
You can verify that "Client" VM joined the DC through "Active Directory Users and Computers". 
</p>
<br />

## Group Policy

<p>
<img width="1892" height="932" alt="image" src="https://github.com/user-attachments/assets/b1285f34-31b0-4685-af8e-e53aa3efa1f8" />
<img width="1703" height="902" alt="image" src="https://github.com/user-attachments/assets/17010aea-335f-4530-9459-ed26e7aa2c02" />
<img width="513" height="147" alt="image" src="https://github.com/user-attachments/assets/4b094cb3-847f-4bc2-949b-d6e747d3e0f6" />



</p>
<p>
Group Policies can be used to control users and computers behavior across the domain. This ranges from security settings, computer configuration, user configuration, adminstrative templates, and much more. In this example we are only editing an existing policty to control number of attempted log ins before the account is locked out.
</p>
<br />

## Unlocking a locked out account

<p>
<img width="782" height="569" alt="image" src="https://github.com/user-attachments/assets/63acce77-5b3e-451a-a7ed-e51f14be3f3f" />

</p>
<p>
To unlock an account, simply go to active directory users and computers. Find and select the user that has requested assistance with a lockout. Under the properties of this users, you will go to account. Here you will see the notification stating that the user is in fact locked out. You must only check the box that says "Unlock Account". Depending on company policy you may want to force a password change, or any other condition.
</p>
<br />

## Managing a users account

</p>
<p>
Through Active Directory Users and Computers you can also disable, or re-enable a users account. I perform this action with a simple right click on the user under the database they can be found in.
</p>
<br />


## Throug Active Directory , and Group Policy Management Console as an admin, you have control of the domain, policies, and the users on it. This example is only a very brief demonstration of what can be managed from this station.
<br />

## Working a ticketing system (osTicket)

<p>
<img width="1678" height="870" alt="image" src="https://github.com/user-attachments/assets/20d1ab9e-b272-4de6-8910-c23a23ab4811" />
</p>
<p>
Navigate to your "Virtual Networks" from the Microsoft Azure Portal. This can be done either by the search bar at the top, or the drop down menu on the left. Click "Create".
</p>
<br />


<p>
<img width="1678" height="870" alt="image" src="https://github.com/user-attachments/assets/20d1ab9e-b272-4de6-8910-c23a23ab4811" />
</p>
<p>
Navigate to your "Virtual Networks" from the Microsoft Azure Portal. This can be done either by the search bar at the top, or the drop down menu on the left. Click "Create".
</p>
<br />


<p>
<img width="1678" height="870" alt="image" src="https://github.com/user-attachments/assets/20d1ab9e-b272-4de6-8910-c23a23ab4811" />
</p>
<p>
Navigate to your "Virtual Networks" from the Microsoft Azure Portal. This can be done either by the search bar at the top, or the drop down menu on the left. Click "Create".
</p>
<br />


<p>
<img width="1678" height="870" alt="image" src="https://github.com/user-attachments/assets/20d1ab9e-b272-4de6-8910-c23a23ab4811" />
</p>
<p>
Navigate to your "Virtual Networks" from the Microsoft Azure Portal. This can be done either by the search bar at the top, or the drop down menu on the left. Click "Create".
</p>
<br />


<p>
<img width="1678" height="870" alt="image" src="https://github.com/user-attachments/assets/20d1ab9e-b272-4de6-8910-c23a23ab4811" />
</p>
<p>
Navigate to your "Virtual Networks" from the Microsoft Azure Portal. This can be done either by the search bar at the top, or the drop down menu on the left. Click "Create".
</p>
<br />


<p>
<img width="1678" height="870" alt="image" src="https://github.com/user-attachments/assets/20d1ab9e-b272-4de6-8910-c23a23ab4811" />
</p>
<p>
Navigate to your "Virtual Networks" from the Microsoft Azure Portal. This can be done either by the search bar at the top, or the drop down menu on the left. Click "Create".
</p>
<br />


<p>
<img width="1678" height="870" alt="image" src="https://github.com/user-attachments/assets/20d1ab9e-b272-4de6-8910-c23a23ab4811" />
</p>
<p>
Navigate to your "Virtual Networks" from the Microsoft Azure Portal. This can be done either by the search bar at the top, or the drop down menu on the left. Click "Create".
</p>
<br />


<p>
<img width="1678" height="870" alt="image" src="https://github.com/user-attachments/assets/20d1ab9e-b272-4de6-8910-c23a23ab4811" />
</p>
<p>
Navigate to your "Virtual Networks" from the Microsoft Azure Portal. This can be done either by the search bar at the top, or the drop down menu on the left. Click "Create".
</p>
<br />


