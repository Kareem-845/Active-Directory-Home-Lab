Active Directory Home Lab

1.Lab Overview

This lab shows how to build a small Windows environment using virtual machines. The environment consists of a Windows Server domain controller and Windows 10 client. The server provides the network and directory services and the Windows 10 system acts as a domain-joined workstation. The completed lab simulates common IT tasks, including user account management, DHCP address assignment, DNS resolution, domain joining, authentication, and workstation administration.

2.Objectives
 
The objectives of this lab were to:

Create a Windows Server and Windows 10 environment
Configure a Windows Server system as a domain controller
Install and configure Active Directory Domain Services
Configure DHCP to automatically assign IP addresses
Configure DNS for internal name resolution
Configure NAT so the client can access the internet through the domain controller
Create Active Directory user accounts
Use PowerShell to automate/bulk-create users
Configure a Windows 10 workstation as a domain member
Test domain authentication using an Active Directory account
Verify network connectivity

3.Lab Architecture

Domain Controller

The Windows Server virtual machine functions as the central server and provides:

Active Directory Domain Services
DNS
DHCP
NAT
User and computer management

Client Workstation

The Windows 10 virtual machines represents a corporate workstation. It receives network configuration from DHCP and joins the Active Directory domain.

Network Design

The client communicates with the domain controller through the internal network in VirtualBox.

4. Software and Requirements

Components used in this lab include:

Oracle VirtualBox - Virtualization platform

Windows Server 2019 ISO - Domain controller

Windows 10 ISO - Client workstation

Active Directory Domain Services - Authentication and directory management

DHCP - Automatic IP address assignment

DNS - Name resolution and domain functionality

PowerShell - User creation and administration

NAT - Internet access through the server

5.Lab Procedure

Step 1 - Create the Virtual Machines

VirtualBox was used to create the Windows Server 2019 and Windows 10 virtual machines.
<img width="569" height="235" alt="image" src="https://github.com/user-attachments/assets/0284ca4c-ed64-4036-87af-26e78477efdb" />


Step 2 - Configure the Domain Controller

The server was configured with a static IP address and then prepared to provide directory and network services. Active Directory Domain Services was installed and promoted to a domain controller.

Step 3 - Configure DHCP

DHCP was set up on the Windows Server so that client machines could automatically receive IP addresses. A DHCP scope was created to provide addresses to devices on the internal network. One issue occurred where the DHCP server wa not initially providing the default gateway to the Windows 10 client.

Step 4 - Configure NAT

The domain controller was configured to provide internet forwarding for the internal network. This allows the Windows 10 workstation to communicate with the internet through the domain controller.

Step 5 - Configure Active Directory Users

Active Directory Users and Computers was used to manage domain accounts. The lab also demonstrated account creation using Powershell. Bulk user creation represents a realistic enterprise scenario where many employees may need accounts at the same time.

Step 6 - Install and Configure Windows 10

Windows 10 was installed as the client operating system. After installation, network configuration was verified using the ipconfig command.

Step 7 - Rename and Join the Windows 10 Computer to the Domain

The workstation was renamed to Client1 and was configured to join mydomain.com. After restarting the computer, the workstation became a member of the Active Directory domain.

Step 8 - Verify the Domain Join

The domain controller was inspected using Active Directory Users and Computers. The Windows 10 computer appeared in the appropriate computer container.

Step 9 - Log in Using a Domain Account

Instead of using the local Windows account, the workstation was accessed using an Active Directory user account. The other user option was selected and domain credentials were used.



 

