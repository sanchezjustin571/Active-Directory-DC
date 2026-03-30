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

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.
</p>
<br />
