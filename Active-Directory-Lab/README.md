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

**Result:** The virtual machine was created successfully and is ready for Windows Server installation.

**Screenshot 1: Virtual Machine Configuration**

The screenshot shows the virtual machine name, operating system, memory, processor allocation, and virtual disk size.
<img width="842" height="628" alt="01-vm-configuration" src="https://github.com/user-attachments/assets/aebbcb9d-ce10-4bc6-951c-dd9a375758c0" />



## Step 2: Install Windows Server 2025

**Goal:** Install the server operating system.

### Procedure

1. Start the `AD-Lab-Server2025` virtual machine.
2. Select English (United States) and the US keyboard layout.
3. Choose **Install Windows Server**.
4. Select **Windows Server 2025 Standard Evaluation (Desktop Experience)**.
5. Review and accept the license terms.
6. Select the 50 GB unallocated virtual disk.
7. Click **Install** and wait for setup to finish.
8. Create and securely store the Administrator password.
9. Sign in to Windows Server.

**Result:** Windows Server 2025 was installed and the server desktop was accessible.

**Screenshot 2: Windows Server Language Settings**

The Windows Server 2025 installation was configured to use English (United States) for the installation language and time and currency format.
<img width="1021" height="780" alt="02-windows-server-language" src="https://github.com/user-attachments/assets/efc46cca-d2cb-41aa-b423-3ba19dde0916" />

**Screenshot 3: Windows Server Keyboard Settings**

The keyboard layout was configured as US during Windows Server 2025 installation.
<img width="1015" height="769" alt="03-keyboard-settings" src="https://github.com/user-attachments/assets/98db347b-a95e-40a9-977a-1228efcfae6e" />

**Screenshot 4: Select Windows Server Installation**

The Windows Server setup option was selected to begin installing Windows Server 2025. The installation acknowledgment was checked before continuing.
<img width="1019" height="773" alt="04-install-windows-server" src="https://github.com/user-attachments/assets/709ba435-cfbf-4c5e-9254-719129ffd40f" />

**Screenshot 5: Windows Server 2025 Edition Selection**

Windows Server 2025 Standard Evaluation (Desktop Experience) was selected to install the server with a graphical user interface for managing Active Directory and other Windows Server features.
<img width="1018" height="757" alt="05-windows-server-edition" src="https://github.com/user-attachments/assets/680967a0-0f52-44ad-b55a-e1950698ecaa" />

**Screenshot 6: Windows Server License Terms**

The Windows Server 2025 software license terms were presented during installation before proceeding with setup.
<img width="1012" height="769" alt="06-license-terms" src="https://github.com/user-attachments/assets/d815a3a3-0304-41b6-9b05-37ac96744118" />

**Screenshot 7: Select Windows Server Installation Disk**

The 50 GB unallocated virtual disk was selected as the destination for the Windows Server 2025 installation.
<img width="1018" height="781" alt="07-installation-disk" src="https://github.com/user-attachments/assets/06bcc83e-1773-4518-8501-3a09e49c7e7d" />

**Screenshot 8: Windows Server Installation Confirmation**

Windows Server 2025 Standard Evaluation (Desktop Experience) was selected, and the setup was ready to begin installing the operating system on the virtual machine.
<img width="1019" height="758" alt="08-ready-to-install" src="https://github.com/user-attachments/assets/934ff21d-69f9-4e73-a337-fb7b60f3189c" />

**Screenshot 9: Configure the Administrator Account**

A password was configured for the built-in Administrator account to secure access to the Windows Server 2025 virtual machine.
<img width="1021" height="806" alt="09-administrato-password-setup" src="https://github.com/user-attachments/assets/3ddb1bd3-d714-4abd-92d8-b116ca147499" />

**Screenshot 10: Windows Server Administrator Sign-In**

Windows Server 2025 installation completed successfully, and the built-in Administrator sign-in screen was displayed.
<img width="1023" height="819" alt="10-administrator-sign-in" src="https://github.com/user-attachments/assets/cbbb1bda-e9ec-408c-8ba3-3e8a7cc8221e" />

**Screenshot 11: Windows Server Manager Dashboard**

After signing in as Administrator, Server Manager opened successfully. The dashboard provides access to server configuration and management tools.
<img width="1023" height="830" alt="11-server-manager-dashboard" src="https://github.com/user-attachments/assets/f842e52d-c8a5-4c71-9c9a-bbb7290bbcdf" />



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
