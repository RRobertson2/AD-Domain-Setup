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


<table>
  <thead>
    <tr>
      <th>Step</th>
      <th>Description</th>
    </tr>
  </thead>
  <tbody>
<tr>
      <td><strong>Step 1<br>Proxmox VM Creation</strong></td>
      <td>
        Create a new Windows Server 2022 virtual machine using Proxmox. Assign CPU, memory, and disk space based on lab needs.<br><br>
        <img src="https://imgur.com/your_image_1.png" alt="Proxmox VM Creation" width="600">
      </td>
    </tr>

  <tr>
      <td><strong>Step 2<br>Windows Server Installation</strong></td>
      <td>
        Install Windows Server 2022 on the VM and complete initial setup including computer name and network settings.<br><br>
        <img src="https://imgur.com/your_image_2.png" alt="Windows Server Setup" width="600">
      </td>
    </tr>

  <tr>
      <td><strong>Step 3<br>AD DS Role Installation</strong></td>
      <td>
        Use Server Manager to install the Active Directory Domain Services role and related features.<br><br>
        <img src="https://imgur.com/your_image_3.png" alt="AD DS Role Installation" width="600">
      </td>
    </tr>

  <tr>
      <td><strong>Step 4<br>Promote to Domain Controller</strong></td>
      <td>
        Promote the server to a domain controller by configuring a new forest and domain (e.g., homelab.local).<br><br>
        <img src="https://imgur.com/your_image_4.png" alt="Domain Promotion" width="600">
      </td>
    </tr>

  <tr>
      <td><strong>Step 5<br>DNS Integration</strong></td>
      <td>
        Verify DNS settings and ensure that forward and reverse lookup zones are properly configured and dynamic updates are enabled.<br><br>
        <img src="https://imgur.com/your_image_5.png" alt="DNS Configuration" width="600">
      </td>
    </tr>

  <tr>
      <td><strong>Step 6<br>OU and User Creation</strong></td>
      <td>
        Create Organizational Units (OUs) and add test user accounts to simulate a real organization structure.<br><br>
        <img src="https://imgur.com/your_image_6.png" alt="OU and User Setup" width="600">
      </td>
    </tr>

  <tr>
      <td><strong>Step 7<br>Group Policy Setup</strong></td>
      <td>
        Use Group Policy Management Console to create and link GPOs to control user settings (e.g., restrict control panel access).<br><br>
        <img src="https://imgur.com/your_image_7.png" alt="GPO Creation" width="600">
      </td>
    </tr>

   <tr>
      <td><strong>Step 8<br>Domain Join</strong></td>
      <td>
        Join a client machine to the domain and confirm connectivity with the domain controller.<br><br>
        <img src="https://imgur.com/your_image_8.png" alt="Client Domain Join" width="600">
      </td>
    </tr>

  <tr>
      <td><strong>Step 9<br>Test GPO Enforcement</strong></td>
      <td>
        Log in with a domain user and verify that GPOs are applied using `gpresult` and by testing expected policy effects.<br><br>
        <img src="https://imgur.com/your_image_9.png" alt="GPO Testing" width="600">
      </td>
    </tr>

  <tr>
      <td><strong>Step 10<br>Review and Snapshot</strong></td>
      <td>
        Review configuration, create a Proxmox snapshot of the working domain controller for easy rollback or reuse.<br><br>
        <img src="https://imgur.com/your_image_10.png" alt="Snapshot in Proxmox" width="600">
      </td>
    </tr>

  </tbody>
</table>

