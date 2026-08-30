# Experiment 1 – Virtual Workstation

## Title
Virtual Workstation

## Aim
To install VirtualBox / VMware / equivalent open-source cloud workstation with different flavours of Linux or Windows OS on top of Windows 8 and above.

---

## Requirements
| Item | Details |
|------|---------|
| Host OS | Windows 8 / Windows 10 / Windows 11 (64-bit) |
| Software | Oracle VM VirtualBox (latest) |
| Guest OS ISO | Windows 98 (or any Linux/Windows ISO) |
| RAM (Host) | Minimum 2 GB (4 GB recommended) |
| Disk Space | Minimum 5 GB free |

---

## Introduction
**VirtualBox** is a free and open-source hosted hypervisor (Type-2) developed by Oracle. It allows users to run multiple guest operating systems simultaneously on a single physical host machine. This is widely used in cloud computing labs to simulate virtual workstations and isolated environments.

---

## Procedure

### A. Installing VirtualBox
1. Visit [https://www.virtualbox.org/](https://www.virtualbox.org/) and download the Windows Hosts installer.
2. Run the downloaded `.exe` file.
3. Click **Next** through the setup wizard.
4. Choose installation directory (default: `C:\Program Files\Oracle\VirtualBox\`).
5. Select required features (USB support, Networking, Python support).
6. Allow the installer to configure network interfaces when prompted.
7. Click **Install** and allow UAC permissions.
8. Click **Finish** — VirtualBox Manager launches.

### B. Creating a Virtual Machine
1. Click **New** in VirtualBox Manager.
2. Set the following configuration:
   - **Name:** Windows 98
   - **Type:** Microsoft Windows
   - **Version:** Windows 98
   - **ISO Image:** Browse to `windows98.iso`
3. Allocate hardware:
   - **Base Memory:** 512 MB
   - **Processors:** 1 CPU
4. Create a Virtual Hard Disk:
   - **Size:** 2.00 GB
   - **Type:** VDI (Dynamically Allocated)
5. Click **Finish** to create the VM.
6. Select the VM and click **Start**.
7. Follow the Windows 98 installer on-screen instructions.
8. Guest OS desktop loads after installation.

---

## Files
| File | Description |
|------|-------------|
| `setup.txt` | Step-by-step VirtualBox installation and VM configuration |
| `output.txt` | Simulated terminal/console output for this experiment |

---

## How to Execute
This is a configuration/installation experiment — no code to compile.
1. Follow the steps in `setup.txt`.
2. Install VirtualBox on the host machine.
3. Create and start the virtual machine using the steps provided.

---

## Expected Output
- VirtualBox Manager opens successfully.
- Virtual Machine (Windows 98) is created with 512 MB RAM, 1 CPU, 2 GB disk.
- VM starts and the guest OS desktop loads.

---

## Result
VirtualBox was installed successfully, and a virtual machine with Windows 98 as the guest OS was configured and executed on the host machine running Windows 8 or above.
