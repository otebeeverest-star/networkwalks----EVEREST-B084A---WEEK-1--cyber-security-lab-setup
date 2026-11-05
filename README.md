# Networkwalks---B084A---WEEK-1--CyberSecurity-Lab-Setup
CYBERSECURITY LAB SETUP
<div align="center">

# 🔐 Cybersecurity Lab Environment Setup

**Building an isolated virtual lab for penetration testing and ethical hacking practice**
</div>

<p align="center">
  <img src="https://img.shields.io/badge/Skill-Cybersecurity-404040?style=flat-square&labelColor=C00000" />
  <img src="https://img.shields.io/badge/Ver-Virtualbox%20v7.2-0070C0?style=flat-square&labelColor=000000" />
  <img src="https://img.shields.io/badge/Kali%20Linux-v2026.2-E87500?style=flat-square&labelColor=000000&logo=kalilinux&logoColor=white" />
  <img src="https://img.shields.io/badge/Skill-Linux-404040?style=flat-square&labelColor=C00000" />
  <img src="https://img.shields.io/badge/Network-10.0.0.0%2F24-238F89?style=flat-square&labelColor=000000" />
  <img src="https://img.shields.io/badge/Penetration%20Testing-C00000?style=flat-square&labelColor=000000&logo=kalilinux&logoColor=white" />
  <img src="https://img.shields.io/badge/Skill-Virtualization-404040?style=flat-square&labelColor=C00000" />
  <img src="https://img.shields.io/badge/GitHub-404040?style=flat-square&labelColor=0070C0&logo=github&logoColor=white" />
  <img src="https://img.shields.io/badge/Kali%20Linux-404040?style=flat-square&labelColor=C00000&logo=kalilinux&logoColor=white" />
  <img src="https://img.shields.io/badge/NetworkWalks-404040?style=flat-square&labelColor=C00000" />
  <img src="https://img.shields.io/badge/Ethical%20Hacking-E87500?style=flat-square&labelColor=000000&logo=kalilinux&logoColor=white" />
  <img src="https://img.shields.io/badge/Waqas%20Karim%20CCIE-C00000?style=flat-square" />
</p>

---

## 📌 Project Overview

This project builds a virtual cybersecurity and penetration-testing lab using VirtualBox and Kali Linux. It gives you a safe, isolated environment for practicing network scanning, reconnaissance, and vulnerability assessment. The lab runs on a private virtual network, so more machines can be added later as targets for authorized testing.

## 🎯 Objectives

The main objectives of this project are to:

- Install and configure VirtualBox.
- Install/import Kali Linux as a virtual machine.
- Create a private **NAT Network** for the cybersecurity lab.
- Configure network connectivity for Kali Linux.
- Assign a consistent IP address to the Kali VM.
- Verify network connectivity and DNS resolution.
- Take a clean VM snapshot for recovery.
- Document the complete setup process.
- Prepare the environment for future cybersecurity projects.

---
## 🛡️ Purpose of the Lab

The lab provides an isolated and controlled environment for cybersecurity learning and authorized security testing.

It can be used for activities such as:

- Network reconnaissance
- Port scanning
- Vulnerability assessment
- Packet analysis
- Web security testing
- Exploitation practice
- Security-tool experimentation

⚠️ **Important:** This laboratory must only be used for systems that you own or have explicit permission to test. Do not use the lab or its tools to attack unauthorized systems.

---
# 🪜 Lab Setup Procedure

## Step 1. Install 7-Zip

7-Zip was installed to extract the Kali Linux virtual-machine package, which may be distributed as a `.7z` archive.

**Tool:** 7-Zip

---

## Step 2. Install VirtualBox

VirtualBox was installed as the hypervisor.

---

## Step 3. Create the NAT Network

A dedicated NAT Network was created in VirtualBox.

Configuration:
Network Name: NatNetwork
IPv4 Prefix:  10.0.0.0/24
DHCP:         Enabled
IPv6:         Disabled
<img width="1366" height="768" alt="Screenshot (11)" src="https://github.com/user-attachments/assets/0a00ab5f-5916-40d7-9828-d71d7bdfb443" />
A **NAT Network** was selected because multiple virtual machines connected to the same NAT Network can communicate with one another while also having outbound network connectivity.

This will allow future attacker and target VMs to communicate within the lab.


---

## Step 4. Import Kali Linux

The Kali Linux virtual machine was downloaded from the official Kali Linux website and imported into VirtualBox.

The VM network adapter was configured as follows:

```text
Adapter 1
Attached to: NAT Network
Network:     NatNetwork
Adapter Type: Intel PRO/1000 MT Desktop
```

The VM was allocated:
```text
RAM: 2048 MB
```
<img width="1366" height="768" alt="Screenshot (17)" src="https://github.com/user-attachments/assets/42630719-fa8f-49ab-88b2-0891586cfdb5" />
A shared folder was also configured for transferring required files between the host operating system and the Kali VM.



---

## Step 5. Configure the Kali Linux Network

The Kali Linux network configuration was checked and configured with a consistent IPv4 address.

A consistent IP address makes it easier to document the lab and reference the Kali machine in future exercises.
<img width="1280" height="960" alt="ss" src="https://github.com/user-attachments/assets/c74784eb-3ce9-4927-a52a-5aeee91ca4e2" />

# 🐞 Problems Encountered & Solutions
1. **The downloaded file was empty and would not extract.**
   WinRAR displayed "No archives found" because the file was 0 bytes, so the download had not completed. An incomplete "Unconfirmed .crdownload" file was also left on the Desktop. I deleted both and downloaded the Kali VirtualBox image again from the official Kali website (kali.org/get-kali).

2. **Display settings were greyed out in VirtualBox.**
   I could not change the Graphics Controller or Video Memory because the virtual machine was running. I shut down Kali completely, then changed the Graphics Controller from VMSVGA to VBoxVGA and left 3D Acceleration unchecked, as the lab guide shows.

3. **Could not take screenshots inside Kali.**
   The Print Screen key was being captured by Windows instead of the virtual machine. I used VirtualBox's built-in screenshot option (View → Take Screenshot, or Right Ctrl + E) and the Windows Snipping Tool (Win + Shift + S) instead.

4. **Difficulty locating some settings in VirtualBox.**
   Some options were hard to find because VirtualBox groups its settings into categories (General, System, Display, Storage, Network, and so on) and has Basic and Expert views. I used the Settings window and its search box to find the right option, and the Expert view to see all the options on one page.

5. **Did not know the virtual machine must be switched off before changing some settings.**
   Settings such as Display and System were greyed out and could not be edited while Kali was running. I learned that the machine has to be fully powered off first (shut down from inside Kali or through Machine → ACPI Shutdown) before these settings can be changed. Only then did the options become available.

---

# 💡 What I Learned

Through this project, I learned how to create and configure a virtual environment for cybersecurity practice.

The most important concepts I learned include:

### 1. NAT vs NAT Network

A standard NAT configuration and a NAT Network serve different purposes.

A NAT Network allows multiple VMs connected to the same virtual network to communicate with one another while providing network address translation for external connectivity.

This makes it useful for building a multi-machine cybersecurity laboratory.

### 2. Virtual Machine Networking

I learned how VirtualBox virtual network adapters connect virtual machines to different types of networks and how network configuration affects communication between machines.

### 3. Static IP Configuration

I learned how to configure and verify IPv4 addressing, subnet masks, gateways, and DNS settings in Kali Linux.

### 4. VM Snapshots

I learned that a clean snapshot should be created **before performing risky or experimental activities**.

This provides a known-good recovery point for future cybersecurity exercises.

### 5. Documentation

I learned that documenting commands, configuration, screenshots, problems, and solutions is an important part of a professional cybersecurity project.

---
# 🔗 Tools & Resources

- **7-Zip:** [https://7-zip.org/download.html](https://7-zip.org/download.html)
- **VirtualBox:** [https://virtualbox.org/wiki/Downloads](https://virtualbox.org/wiki/Downloads)
- **Kali Linux:** [https://kali.org/get-kali](https://kali.org/get-kali)

- LinkedIn: https://www.linkedin.com/in/otebe-everest-029700449/
---
## 📌 Project Information

**Program Name:** Cybersecurity at Networkwalks | **Week:** 01 | **Project:** Cybersecurity & Pentesting Lab Setup | **Repository:** GitHub
