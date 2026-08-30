# Experiment 6 – Virtual Machine File Transfer

## Title
Find a Procedure to Transfer Files from One Virtual Machine to Another Virtual Machine

## Aim
To find a procedure to transfer files from one virtual machine to another virtual machine using VirtualBox.

---

## Requirements
| Item | Details |
|------|---------|
| Hypervisor | Oracle VM VirtualBox |
| Extension | VirtualBox Extension Pack (for USB) |
| Guest Additions | VirtualBox Guest Additions (for Drag & Drop / Shared Folders) |
| Host OS | Windows 8 / 10 / 11 |
| Guest OS | Any (Windows / Linux) |

---

## Introduction
In a virtualized environment, files cannot be directly copied between virtual machines (VMs) the same way they are on a physical network. VirtualBox provides several built-in mechanisms to enable file sharing and transfer between the host machine and guest VMs, and indirectly between two VMs.

---

## Method 1: Drag and Drop

**Tool Required:** VirtualBox Guest Additions  
**Direction:** Host ↔ Guest

### Steps:
1. Install Guest Additions: **Devices → Insert Guest Additions CD Image**
2. In the VirtualBox menu: **Devices → Drag and Drop → Bidirectional**
3. Drag a file from the host file explorer into the VM window (or vice versa).
4. To transfer between VM1 and VM2:
   - VM1 → Host (Guest to Host)
   - Host → VM2 (Host to Guest)

---

## Method 2: USB Drive

**Tool Required:** VirtualBox Extension Pack  
**Direction:** VM1 → USB → VM2

### Steps:
1. Install Extension Pack: **File → Preferences → Extensions → Add**
2. Connect USB drive to the host.
3. **VM Settings → USB → Enable USB Controller → Add USB Filter**
4. Select the USB drive.
5. Start VM1 — USB appears inside the guest OS.
6. Copy the file to the USB drive.
7. Remove the USB from VM1, attach to VM2.
8. Access the file from the USB inside VM2.

---

## Method 3: Shared Folder

**Tool Required:** VirtualBox Guest Additions  
**Direction:** Both VMs access a common host folder

### Steps:
1. Create a folder on the host: `C:\VMShare\`
2. **VM Settings → Shared Folders → + → Add Shared Folder**
   - Folder Path: `C:\VMShare\`
   - Folder Name: `VMShare`
   - Auto-mount: ✓
   - Make Permanent: ✓
3. Start the VM. The folder is mounted as:
   - Linux guest: `/media/sf_VMShare/`
   - Windows guest: Network Drive (e.g., `Z:\`)
4. Both VM1 and VM2 can read/write to this shared folder simultaneously.

---

## Files
| File | Description |
|------|-------------|
| `procedure.txt` | Detailed step-by-step procedure for all three methods |
| `output.txt` | Simulated file transfer output |

---

## How to Execute
This is a procedure-based experiment. Follow the steps in `procedure.txt` using Oracle VM VirtualBox. No programming or code compilation is required.

---

## Expected Output
- Files successfully transferred between the host and guest VMs.
- USB device visible inside the VM.
- Shared folder accessible by both VMs.

---

## Result
The procedure to transfer files between virtual machines was documented and executed successfully using three methods: Drag and Drop, USB Drive, and Shared Folder.
