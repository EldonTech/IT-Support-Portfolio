# Active Directory Home Lab

## Overview

This project documents how I built an Active Directory home lab using Oracle VirtualBox and Windows Server 2025. The goal was to gain hands-on experience with Windows Server administration and common IT Help Desk tasks.

## Lab Environment

| Component | Configuration |
|---|---|
| Host Operating System | Windows 11 |
| Virtualization Software | Oracle VirtualBox |
| Server Operating System | Windows Server 2025 Standard Evaluation (Desktop Experience) |
| Virtual Machine RAM | 4 GB |
| Virtual Machine CPU | 2 virtual CPUs |
| Virtual Disk | 50 GB |
| Domain Name | `ad.lab` |
| NetBIOS Name | `AD` |

## Lab Objectives

- Install Windows Server in a virtual machine.
- Install Active Directory Domain Services (AD DS).
- Create a new Active Directory domain.
- Create an Organizational Unit (OU).
- Create and manage user accounts.
- Practice resetting user passwords.

---

# Step-by-Step Setup Guide

## Step 1: Create the Virtual Machine

**Goal:** Create a virtual machine to host Windows Server 2025 for the Active Directory lab.

### Configuration

- **Virtualization software:** Oracle VirtualBox
- **Operating system:** Windows Server 2025 (64-bit)
- **Memory:** 4 GB RAM
- **Processors:** 2 CPUs
- **Virtual disk:** 50 GB
- **Installation method:** Manual installation using an ISO image

### Procedure

1. Open Oracle VirtualBox and select **New**.
2. Name the virtual machine `AD-Lab-Server2025`.
3. Select the Windows Server 2025 ISO image.
4. Disable unattended installation to perform the setup manually.
5. Allocate 4096 MB of RAM and 2 processors.
6. Create a 50 GB virtual hard disk.
7. Review the configuration and create the virtual machine.

**Result:** A virtual machine was configured to host the Windows Server 2025 installation.

**Screenshot 1: Virtual Machine Configuration**

The screenshot shows the virtual machine name, operating system, memory, processor allocation, and virtual disk size.
<img width="842" height="628" alt="01-vm-configuration" src="https://github.com/user-attachments/assets/11ff6782-1948-4846-b837-40d84c1d6249" />
