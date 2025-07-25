# AD-Domain-Install On VM

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
        Created a new virtual machine in Proxmox VE with the following resources:<br>
        <br>
        -CPU: 2 cores<br>
        -Memory: 2 GB<br>
        -Disk: 120 GB<br>
        -ISO files: Windows Server 2022 and VirtIO driver ISO added to CD-ROM drives<br> 
        <br>
        <img src="https://github.com/user-attachments/assets/f801cb7e-6068-424e-bc1f-73d372cfeb1c" alt="Proxmox VM Creation" width="1000">
        <img src="https://github.com/user-attachments/assets/d4e14173-c2fd-46db-99d7-92244f0fc116"Proxmox VM Creation" width="1000">
      </td>
    </tr>

  <tr>
      <td><strong>Step 2<br>ISO Boot Order Configuration</strong></td>
      <td>
        Adjusted virtual hardware settings to ensure the Windows Server ISO boots first, followed by the VirtIO ISO. This step ensures driver availability during installation.<br><br>
        <img src="https://github.com/user-attachments/assets/96b64655-b705-4a9c-832c-ae5558f0f9fe" alt="Adjust Iso Images" width="1000">
      </td>
    </tr>

  <tr>
      <td><strong>Step 3<br>Windows Server Installation</strong></td>
      <td>
        Launched the VM and installed Windows Server 2022 Desktop Experience. Selected region, language, and installation type (Custom Install). Proceeded through standard setup steps.<br>
        <br>
        <img src="https://github.com/user-attachments/assets/22b34de5-f488-4eb5-8a87-a56e0e50e10c"Launch VM & Install Windows Server" width="1000">
        <img src="https://github.com/user-attachments/assets/fe34e6fe-fb2f-48e4-8777-8eeab7867308"Launch VM & Install Windows Server" width="1000">
        <img src="https://github.com/user-attachments/assets/d8fe5b20-13e5-40ed-82d9-ac3122889065"Launch VM & Install Windows Server" width="1000">
      </td>
    </tr>

  <tr>
      <td><strong>Step 4<br>VirtIO Driver Installation</strong></td>
      <td>
        Mounted the VirtIO ISO and manually installed critical drivers to enable virtual disk, network, and serial devices:<br>
        <br>
        -Red Hat VirtIO Ethernet<br>
        -VirtIO Balloon<br>
        -VirtIO SCSI<br>
        Download source: https://fedorapeople.org/groups/virt/virtio-win/direct-downloads/latest-virtio/<br>
        <br>
        <img src="https://github.com/user-attachments/assets/66d417ad-d099-42f3-bf13-dd85f1464056" alt="VM Diver Install" width="1000">
        <img src="https://github.com/user-attachments/assets/7ba4528d-32ee-41e6-be4a-d3c67cd01116" alt="VM Diver Install" width="1000">
        <img src="https://github.com/user-attachments/assets/333c241e-2468-4391-adc9-4bd047cd26d1" alt="VM Diver Install" width="1000">
        <img src="https://github.com/user-attachments/assets/02163f93-0de1-4754-92ca-e0b8ced2d787" alt="VM Diver Install" width="1000">
        <img src="https://github.com/user-attachments/assets/05f5b0af-e47c-482d-b420-9707d13ad9ad" alt="VM Diver Install" width="1000">
      </td>
    </tr>
<tr>
      <td><strong>Step 5<br> Fixing PCI Simple Communications Controller Error</strong></td>
      <td>
        Resolved missing driver by: <br><br>
        1. Opening Device Manager<br>
        2. Right-clicking PCI Simple Communications Controller<br>
        3. Selecting “Browse my computer for drivers”<br>
        4. Navigating to VirtIO ISO and selecting correct subfolder (e.g., NetKVM, Balloon)<br>
        5. Letting Windows search and install the driver<br>
        <img src="https://github.com/user-attachments/assets/5ac9ae4a-a162-4b46-916e-921a02398c52" alt="DNS Configuration" width="1000">
      </td>
    </tr>
     <tr>
      <td><strong>Step 6<br>Fixing Keyboard Input Issues</strong></td>
      <td>
        Completed administrator setup and manually updated the server’s IP address, subnet mask, and DNS server to place it on a secure internal network. <br><br>
        <img src="https://github.com/user-attachments/assets/5ac9ae4a-a162-4b46-916e-921a02398c52" alt="DNS Configuration" width="1000">
        <img src="https://github.com/user-attachments/assets/40c7428d-d2ed-4b95-890a-c0ccd8be208f" alt="OU and User Setup" width="1000">
        <img src="https://github.com/user-attachments/assets/898e6c2b-8cd1-4d2d-855f-441314f267d6" alt="DNS Configuration" width="1000">
        <img src="https://github.com/user-attachments/assets/f87a7e7c-52f5-4cce-b74e-cb404372d9a0" alt="DNS Configuration" width="1000">
      </td>
    </tr>

  <tr>
      <td><strong>Step 7<br>Final Setup and Static IP Configuration</strong></td>
      <td>
        Completed administrator setup and manually updated the server’s IP address, subnet mask, and DNS server to place it on a secure internal network. <br><br>
        <img src="https://github.com/user-attachments/assets/5ac9ae4a-a162-4b46-916e-921a02398c52" alt="DNS Configuration" width="1000">
        <img src="https://github.com/user-attachments/assets/40c7428d-d2ed-4b95-890a-c0ccd8be208f" alt="OU and User Setup" width="1000">
        <img src="https://github.com/user-attachments/assets/898e6c2b-8cd1-4d2d-855f-441314f267d6" alt="DNS Configuration" width="1000">
        <img src="https://github.com/user-attachments/assets/f87a7e7c-52f5-4cce-b74e-cb404372d9a0" alt="DNS Configuration" width="1000">
      </td>
    </tr>


  </tbody>
</table>

