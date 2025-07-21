# AD-Domain-Setup

## Objective
Designed and deployed an Active Directory Domain Controller in a virtual lab using Proxmox VE. The project aimed to simulate a real enterprise IT environment, providing hands-on experience with domain services, centralized authentication, DNS integration, and Group Policy management. This environment was used to practice common administrative tasks and test Windows-based infrastructure scenarios.

### Skills Learned
- Active Directory Domain Services (AD DS) deployment and management
- Windows Server configuration and troubleshooting
- DNS configuration and integration with AD
- Group Policy Object (GPO) creation, linking, and testing
- Domain user and group account administration
- Organizational Unit (OU) design and role-based access control
- Virtualization setup and resource management using Proxmox VE.

### Tools Used
- Proxmox VE – for virtual machine provisioning and resource allocation
- Windows Server 2022 – installed as the domain controller
- Active Directory Users and Computers (ADUC) – for user and OU management
- Group Policy Management Console (GPMC) – for creating and enforcing policies
- DNS Manager – for verifying domain-integrated DNS zones
- RSAT Tools – for remote management of AD infrastructure

## Steps
Ref 1: Proxmox Virtual Machine Creation
Created a new Windows Server 2022 virtual machine in Proxmox, allocating appropriate CPU, memory, and storage resources.

Ref 2: Windows Server Installation
Installed and configured Windows Server 2022, updated system packages, and prepared the environment for AD role installation.

Ref 3: Active Directory Role Installation
Installed Active Directory Domain Services (AD DS) and promoted the server to a domain controller, creating a new forest and domain (e.g., homelab.local).

Ref 4: DNS Setup
Configured DNS to support dynamic updates and verified the creation of forward and reverse lookup zones integrated with Active Directory.

Ref 5: User and Group Management
Created Organizational Units (OUs) and added domain users and security groups to simulate role-based structure in a typical organization.

Ref 6: Group Policy Management
Created and applied Group Policy Objects (GPOs) to enforce security settings, such as disabling control panel access and restricting software installations.

Ref 7: Domain Join and Policy Testing
Joined client machines to the domain and confirmed GPO enforcement using gpresult and system behavior tests.

