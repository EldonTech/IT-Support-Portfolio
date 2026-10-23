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
| Virtual Disk | 80 GB |
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

## Step 1: Create a Virtual Machine

**Goal:** Create a virtual computer to run Windows Server.

1. Open Oracle VirtualBox.
2. Click **New** to create a virtual machine.
3. Name the virtual machine `WinServer2025`.
4. Select the Windows Server 2025 ISO file.
5. Disable unattended installation so Windows can be installed manually.
6. Configure the virtual hardware:
   - Memory: 4096 MB (4 GB)
   - Processors: 2
   - Virtual disk: 80 GB
7. Review the settings and create the virtual machine.

**Result:** A virtual machine was created for the Windows Server installation.
**Screenshot 1: VirtualBox virtual machine configuration**

The virtual machine was configured with 4 GB of RAM, 2 processors, and an 80 GB virtual hard disk to run Windows Server 2025.
<img width="841" height="702" alt="Screenshot 2026-10-22 082107" src="https://github.com/user-attachments/assets/83c014be-ee0d-4457-964e-3ac7a09b4819" />

<!-- Screenshot: VirtualBox virtual machine configuration -->

## Step 2: Install Windows Server 2025

**Goal:** Install the server operating system.

1. Start the `WinServer2025` virtual machine.
2. Select English (United States) and the US keyboard layout.
3. Choose **Install Windows Server**.
4. Select **Windows Server 2025 Standard Evaluation (Desktop Experience)**.
5. Review and accept the license terms.
6. Select the 80 GB unallocated virtual disk.
7. Click **Install** and wait for setup to finish.
8. Create and securely store the Administrator password.
9. Sign in to Windows Server.

**Result:** Windows Server 2025 was installed and the server desktop was accessible.

<img width="1021" height="855" alt="Screenshot 2026-10-22 090746" src="https://github.com/user-attachments/assets/f031d9a8-d523-4bf8-9059-b1f1947dcdf4" />

<!-- Screenshot: Windows Server desktop -->

## Step 3: Install Active Directory Domain Services

**Goal:** Add the Windows Server role needed to manage a domain.

1. Open **Server Manager**.
2. Select **Manage** > **Add Roles and Features**, or click **Add roles and features** on the dashboard.
3. Choose **Role-based or feature-based installation**.
4. Select the local server.
5. Check **Active Directory Domain Services**.
6. Click **Add Features** when prompted.
7. Continue through the wizard, leaving the other default feature selections unchanged.
8. Click **Install**.

**Result:** The Active Directory Domain Services role was installed.

**Screenshot:** Add a screenshot showing the installed role or Server Manager dashboard.

<!-- Screenshot: Active Directory Domain Services installed -->

## Step 4: Promote the Server to a Domain Controller

**Goal:** Create a new Active Directory domain.

1. In Server Manager, click the notification flag.
2. Select **Promote this server to a domain controller**.
3. Choose **Add a new forest**.
4. Enter `ad.lab` as the root domain name.
5. On the Domain Controller Options page:
   - Keep DNS server selected.
   - Keep Global Catalog selected.
   - Leave Read Only Domain Controller unchecked.
   - Create and securely store a Directory Services Restore Mode (DSRM) password.
6. Leave DNS delegation unchecked for this standalone lab.
7. Keep the generated NetBIOS name `AD`.
8. Leave the database, log, and SYSVOL paths at their defaults.
9. Review the configuration and run the prerequisite check.
10. Click **Install** after the prerequisite checks pass.
11. Allow the server to restart.

**Result:** The server was promoted to a domain controller for the `ad.lab` domain.

**Screenshot:** Add a screenshot of the domain controller configuration or successful promotion.

<!-- Screenshot: Domain controller setup -->

## Step 5: Open Active Directory Users and Computers

**Goal:** Access the tool used to manage domain accounts.

1. Sign in using the domain Administrator account.
2. Open **Server Manager**.
3. Select **Tools** > **Active Directory Users and Computers**.
4. Expand the `ad.lab` domain in the left panel.

**Result:** Active Directory Users and Computers opened and displayed the domain.

**Screenshot:** Add a screenshot showing the `ad.lab` domain.

<!-- Screenshot: Active Directory Users and Computers -->

## Step 6: Create an Organizational Unit

**Goal:** Organize test user accounts in a dedicated OU.

1. In Active Directory Users and Computers, right-click `ad.lab`.
2. Select **New** > **Organizational Unit**.
3. Enter `Help Desk Users` as the name.
4. Leave **Protect container from accidental deletion** checked.
5. Click **OK**.
6. Select the new OU.

**Result:** The `Help Desk Users` OU was created.

**Screenshot:** Add a screenshot showing the OU.

<!-- Screenshot: Help Desk Users OU -->

## Step 7: Create a Test User Account

**Goal:** Practice creating an employee account.

1. Right-click the `Help Desk Users` OU.
2. Select **New** > **User**.
3. Enter the first name `Jamie` and last name `Smith`.
4. Enter `jsmith` as the user logon name.
5. Click **Next**.
6. Set and confirm a strong practice password.
7. Select **User must change password at next logon**.
8. Ensure **Account is disabled** is unchecked.
9. Complete the wizard.

**Result:** A test account for Jamie Smith was created in the `Help Desk Users` OU.

**Screenshot:** Add a screenshot showing the test account in the OU.

<!-- Screenshot: Jamie Smith user account -->

## Step 8: Reset a User Password

**Goal:** Practice a common Help Desk request.

1. In Active Directory Users and Computers, locate Jamie Smith.
2. Right-click the account.
3. Select **Reset Password**.
4. Enter and confirm a new practice password.
5. Select **User must change password at next logon**.
6. Click **OK** to complete the reset.

**Result:** The test user's password was reset successfully.

**Screenshot:** Add a screenshot of the password reset confirmation if available. Never include the password itself.

<!-- Screenshot: Password reset confirmation -->

---

## Skills Practiced

- Windows Server installation and configuration
- Virtual machine creation and resource allocation
- Active Directory Domain Services installation
- Domain controller promotion
- Active Directory domain and OU management
- User account creation
- Password resets
- Basic Windows Server administration
- Technical documentation

## Future Improvements

- Create additional test users and security groups.
- Practice disabling and re-enabling accounts.
- Configure a separate Windows client virtual machine.
- Join the client to the `ad.lab` domain.
- Practice troubleshooting DNS and domain sign-in issues.
- Add screenshots and troubleshooting notes as the lab grows.

## Conclusion

This lab provided hands-on practice installing Windows Server 2025, configuring Active Directory, organizing user accounts, and resetting passwords. These foundational tasks are relevant to entry-level IT Help Desk and IT Support roles.
