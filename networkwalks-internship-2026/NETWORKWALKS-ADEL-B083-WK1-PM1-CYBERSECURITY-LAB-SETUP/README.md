# Networkwalks Cybersecurity Internship — Week 1

## Project
Cybersecurity & Pentesting Lab Setup with VirtualBox and Kali Linux.

## Objective
Build an isolated virtual lab for cybersecurity practice with Kali Linux, NAT Network `10.0.0.0/24`, static Kali IP `10.0.0.2/24`, shared folders, clipboard, drag-and-drop, and full Internet access.

## Step-by-Step Setup

### 1. VirtualBox and Kali Installation
Imported the pre-built Kali Linux VirtualBox image.
![VM Running](screenshots/01-vm-running.png)

### 2. NAT Network Configuration
Created a NAT Network named `NatNetwork` with the IPv4 Prefix `10.0.0.0/24`.
![NAT Network](screenshots/02-natnetwork-settings.png)

### 3. Kali VM Network Settings
Attached the Kali VM to `NatNetwork` and set Promiscuous Mode to `Allow All`.
![Kali Network Adapter](screenshots/03-kali-network-adapter.png)

### 4. Clipboard and Drag-and-Drop
Enabled Bidirectional Shared Clipboard and Drag-and-Drop.
![Clipboard Settings](screenshots/04-clipboard-dragdrop.png)

### 5. Shared Folders
Shared the Windows Downloads folder to Kali as `/downloads`.
![Shared Folder Settings](screenshots/07-shared-folder-settings.png)
![Shared Folder on Desktop](screenshots/05-shared-folder-desktop.png)

### 6. Static IP Configuration
Configured the static IP `10.0.0.2/24` inside Kali using `nmcli`.
![IP and Internet](screenshots/06-kali-ip-config-internet.png)

### 7. Snapshot
Took a clean snapshot of the finished lab.
![Snapshot](screenshots/08-snapshot.png)

## Troubleshooting

**Issue:** Kali Linux had no Internet access after configuring the static IP in VirtualBox.
**Fix:** Applied the known VirtualBox 7 / Kali 2026 fix by disabling the DAD timeout. Ran:
```bash
sudo nmcli connection modify "Wired connection 1" ipv4.dad-timeout 0
sudo nmcli connection down "Wired connection 1"
sudo nmcli connection up "Wired connection 1"
