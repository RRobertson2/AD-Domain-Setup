# AD-Domain-Install On VM

## Objective
Installed Windows Server 2022 on a virtual machine using Proxmox VE to build a foundational server environment. This lab project provided hands-on experience with virtual machine deployment, OS installation, driver management, and system configuration using enterprise tools.

### Skills Learned
- Windows Server 2022 installation and configuration
- Virtualization and resource provisioning using Proxmox VE
- Troubleshooting driver issues in virtual environments (e.g., VirtIO driver setup)
- Identifying and resolving keyboard mapping issues in virtual machines

### Tools Used
- Proxmox VE – for hypervisor and virtual machine management
- Windows Server 2022 – for enterprise server OS installation
- VirtIO Drivers – for enabling virtual hardware support (disk, network, etc.)
- Windows Device Manager and system settings – for post-install configuration

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
        <br>
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
        <br>
        Adjusted virtual hardware settings to ensure the Windows Server ISO boots first, followed by the VirtIO ISO. This step ensures driver availability during installation.<br><br>
        <img src="https://github.com/user-attachments/assets/96b64655-b705-4a9c-832c-ae5558f0f9fe" alt="Adjust Iso Images" width="1000">
      </td>
    </tr>

  <tr>
      <td><strong>Step 3<br>Windows Server Installation</strong></td>
      <td>
        <br>
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
        <br>
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
        <br>
        Resolved missing driver by: <br><br>
        1. Opening Device Manager<br>
        2. Right-clicking PCI Simple Communications Controller<br>
        3. Selecting “Browse my computer for drivers”<br>
        4. Navigating to VirtIO ISO and selecting correct subfolder (e.g., NetKVM, Balloon)<br>
        5. Letting Windows search and install the driver<br>
        <br>
        <img src="https://github.com/user-attachments/assets/5ac9ae4a-a162-4b46-916e-921a02398c52" alt="DNS Configuration" width="1000">
      </td>
    </tr>
     <tr>
      <td><strong>Step 6<br>Fixing Keyboard Input Issues</strong></td>
      <td>
        <br>
        Resolved random input and keyboard glitches by: <br><br>
        -Navigating to Advanced Keyboard Settings
        -Switching input method to “English (United States) – US” This corrected typing behavior inside the Proxmox VM console.<br>
        <br>
        <img src="https://github.com/user-attachments/assets/66a9f586-c9d7-4ebe-9e71-f7051a4f2120" alt="DNS Configuration" width="1000">
      </td>
    </tr>

  <tr>
      <td><strong>Step 7<br>Final Setup and Static IP Configuration</strong></td>
      <td>
        <br>
        Completed administrator setup and manually updated the server’s IP address, subnet mask, and DNS server to place it on a secure internal network. <br>
        <br>
        <img src="https://github.com/user-attachments/assets/5ac9ae4a-a162-4b46-916e-921a02398c52" alt="DNS Configuration" width="1000">
        <img src="https://github.com/user-attachments/assets/40c7428d-d2ed-4b95-890a-c0ccd8be208f" alt="OU and User Setup" width="1000">
        <img src="https://github.com/user-attachments/assets/898e6c2b-8cd1-4d2d-855f-441314f267d6" alt="DNS Configuration" width="1000">
        <img src="https://github.com/user-attachments/assets/f87a7e7c-52f5-4cce-b74e-cb404372d9a0" alt="DNS Configuration" width="1000">
      </td>
    </tr>


  </tbody>
</table>

