# AD-Domain-Install On VM

### Objective
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
- Windows Device Manager and system settings – for post-install configuration<br>

<hr style="border: 0.15px solid rgba(0, 0, 0, 0.05);">
  
### Step 1: Proxmox VM Creation
Created a new virtual machine in Proxmox VE with the following resources:
- CPU: 2 cores  
- Memory: 2 GB  
- Disk: 120 GB  
- ISO files: Windows Server 2022 and VirtIO driver ISO added to CD-ROM drives

<img src="https://github.com/user-attachments/assets/f801cb7e-6068-424e-bc1f-73d372cfeb1c" width="1000">
<img src="https://github.com/user-attachments/assets/d4e14173-c2fd-46db-99d7-92244f0fc116" width="1000">

<hr style="border: 0.15px solid rgba(0, 0, 0, 0.05);">

### Step 2: ISO Boot Order Configuration
Adjusted virtual hardware settings to ensure the Windows Server ISO boots first, followed by the VirtIO ISO. This step ensures driver availability during installation.

<img src="https://github.com/user-attachments/assets/96b64655-b705-4a9c-832c-ae5558f0f9fe" width="1000">

<hr style="border: 0.35px solid rgba(0, 0, 0, 0.05);">

### Step 3: Windows Server Installation
Launched the VM and installed Windows Server 2022 Desktop Experience. Selected region, language, and installation type (Custom Install). Proceeded through standard setup steps.

<img src="https://github.com/user-attachments/assets/22b34de5-f488-4eb5-8a87-a56e0e50e10c" width="1000">
<img src="https://github.com/user-attachments/assets/fe34e6fe-fb2f-48e4-8777-8eeab7867308" width="1000">
<img src="https://github.com/user-attachments/assets/d8fe5b20-13e5-40ed-82d9-ac3122889065" width="1000">

<hr style="border: 0.35px solid rgba(0, 0, 0, 0.05);">

### Step 4: VirtIO Driver Installation
Mounted the VirtIO ISO and manually installed critical drivers to enable virtual disk, network, and serial devices:
- Red Hat VirtIO Ethernet  
- VirtIO Balloon  
- VirtIO SCSI  
Download: https://fedorapeople.org/groups/virt/virtio-win/direct-downloads/latest-virtio/

<img src="https://github.com/user-attachments/assets/66d417ad-d099-42f3-bf13-dd85f1464056" width="1000">
<img src="https://github.com/user-attachments/assets/7ba4528d-32ee-41e6-be4a-d3c67cd01116" width="1000">
<img src="https://github.com/user-attachments/assets/333c241e-2468-4391-adc9-4bd047cd26d1" width="1000">
<img src="https://github.com/user-attachments/assets/02163f93-0de1-4754-92ca-e0b8ced2d787" width="1000">
<img src="https://github.com/user-attachments/assets/05f5b0af-e47c-482d-b420-9707d13ad9ad" width="1000">

<hr style="border: 0.35px solid rgba(0, 0, 0, 0.05);">

### Step 5: Fixing PCI Simple Communications Controller Error
Resolved missing driver by:
1. Opening Device Manager  
2. Right-clicking PCI Simple Communications Controller  
3. Selecting “Browse my computer for drivers”  
4. Navigating to VirtIO ISO and selecting the correct subfolder (e.g., NetKVM, Balloon)  
5. Letting Windows search and install the driver

<img src="https://github.com/user-attachments/assets/47aa077a-3c16-4f99-9596-a20de87ecf43" width="1000">

<hr style="border: 0.35px solid rgba(0, 0, 0, 0.05);">

### Step 6: Fixing Keyboard Input Issues
Resolved random input and keyboard glitches by:
- Navigating to Advanced Keyboard Settings  
- Switching input method to “English (United States) – US”

<img src="https://github.com/user-attachments/assets/66a9f586-c9d7-4ebe-9e71-f7051a4f2120" width="1000">

<hr style="border: 0.35px solid rgba(0, 0, 0, 0.05);">

### Step 7: Final Setup and Static IP Configuration
Completed administrator setup and manually updated the server’s IP address, subnet mask, and DNS server to place it on a secure internal network.

<img src="https://github.com/user-attachments/assets/5ac9ae4a-a162-4b46-916e-921a02398c52" width="1000">
<img src="https://github.com/user-attachments/assets/40c7428d-d2ed-4b95-890a-c0ccd8be208f" width="1000">
<img src="https://github.com/user-attachments/assets/898e6c2b-8cd1-4d2d-855f-441314f267d6" width="1000">
<img src="https://github.com/user-attachments/assets/f87a7e7c-52f5-4cce-b74e-cb404372d9a0" width="1000">


