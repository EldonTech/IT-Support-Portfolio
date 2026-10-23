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

### Procedure

1. Open **Server Manager**.
2. Select **Manage** > **Add Roles and Features**, or click **Add roles and features** on the dashboard.
3. Choose **Role-based or feature-based installation**.
4. Select the local server.
5. Check **Active Directory Domain Services**.
6. Click **Add Features** when prompted.
7. Continue through the wizard, leaving the other default feature selections unchanged.
8. Click **Install**.

**Result:** The Active Directory Domain Services role was installed.

**Screenshot 12: Select Installation Type**

The Role-based or feature-based installation option was selected in Server Manager to install Active Directory Domain Services (AD DS) on the Windows Server 2025 virtual machine.
<img width="1022" height="831" alt="12-installation-type" src="https://github.com/user-attachments/assets/14d3a49a-8638-4515-8b4c-aac32761813b" />

**Screenshot 13: Select Destination Server**

The local Windows Server 2025 machine was selected as the destination server for installing the Active Directory Domain Services role.
<img width="1023" height="829" alt="13-server-selection" src="https://github.com/user-attachments/assets/1be29395-be35-468d-b2a6-d2854d2fb991" />

**Screenshot 14: Select Active Directory Domain Services**

The Active Directory Domain Services (AD DS) role was selected in the Add Roles and Features Wizard. The required management tools were included.
<img width="1021" height="832" alt="14-server-roles" src="https://github.com/user-attachments/assets/4d573edf-3d3b-4ea8-8ced-1e00561f902b" />

**Screenshot 15: Add Required Features**

The required management tools and features for Active Directory Domain Services were confirmed before continuing with the installation.
<img width="1022" height="832" alt="15-add-required-features" src="https://github.com/user-attachments/assets/d5a5fe61-a621-45fd-a55b-c3efe49f8d24" />

**Screenshot 16: Select Features**

The Select Features page was reviewed, and the required default selections were retained.
<img width="1020" height="833" alt="16-select-features" src="https://github.com/user-attachments/assets/5159fb62-750d-426f-bb6a-120f69749e71" />

**Screenshot 17: Active Directory Domain Services Information**

The AD DS information page was reviewed to understand the role and its relationship to domain controllers and DNS.
<img width="1021" height="830" alt="17-adds-information" src="https://github.com/user-attachments/assets/6d726378-7075-434f-a7cb-c6a1e6dd4a82" />

**Screenshot 18: Confirm Installation Selections**

The installation selections were reviewed, including Active Directory Domain Services and its required management tools, before installation.
<img width="1023" height="830" alt="18-confirm-adds-installation" src="https://github.com/user-attachments/assets/01391eb7-7ba6-4d3b-9c56-afd4665a3e8a" />

**Screenshot 19: Active Directory Domain Services Installation Progress**

Active Directory Domain Services and its management tools were installed successfully. The wizard displayed the option to promote the server to a domain controller.
<img width="1024" height="833" alt="19-adds-installation-results" src="https://github.com/user-attachments/assets/76cacb00-5833-4801-9ab2-1cf1ea9f6544" />



## Step 4: Promote the Server to a Domain Controller

**Goal:** Create a new Active Directory domain.

### Procedure

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

**Result:** The Windows Server 2025 virtual machine was successfully promoted to a domain controller for `ad.lab`. Active Directory Users and Computers confirmed the domain controller, and DNS Manager showed the `ad.lab` and `_msdcs.ad.lab` zones running.

**Screenshot 20: New Forest Configuration**

A new Active Directory forest was configured using `ad.lab` as the root domain name.
<img width="1024" height="831" alt="20-new-forest-configuration" src="https://github.com/user-attachments/assets/022786c5-59d6-4381-a769-c5e7640a7416" />

**Screenshot 21: Domain Controller Options**

Windows Server 2025 functional levels were selected, with DNS Server and Global Catalog enabled. A Directory Services Restore Mode (DSRM) password was configured.
<img width="1025" height="833" alt="21-domain-controller-options" src="https://github.com/user-attachments/assets/f8ab2e6d-6fa3-497b-b5de-b9db30980596" />

**Screenshot 22: DNS Options**

The DNS delegation warning was reviewed during domain controller configuration. No DNS delegation was created because this is a standalone home lab environment.
<img width="1021" height="831" alt="22-dns-delegation" src="https://github.com/user-attachments/assets/c9964411-c5f0-463e-801b-6be261cb2236" />

**Screenshot 23: Additional Options**

The NetBIOS domain name was confirmed as `AD` for the new `ad.lab` domain.
<img width="1021" height="827" alt="23-netbios-domain-name" src="https://github.com/user-attachments/assets/527d4253-583a-42a8-99bc-53736ade6beb" />

**Screenshot 24: Paths**

The default paths for the Active Directory database, log files, and SYSVOL were retained.
<img width="1024" height="829" alt="24-paths" src="https://github.com/user-attachments/assets/0dad6e55-f678-4459-a1a4-54a963043f6b" />

**Screenshot 25: Review Options**

The domain controller configuration was reviewed, including the `ad.lab` domain, `AD` NetBIOS name, DNS, Global Catalog, and Windows Server 2025 functional levels.
<img width="1022" height="832" alt="25-review-options" src="https://github.com/user-attachments/assets/9b3daab2-2b2d-4bd0-b3fb-940b2f763c90" />

**Screenshot 26: Prerequisites Check**

The prerequisite checks completed successfully, allowing the server to be promoted to a domain controller. The displayed warnings were reviewed before proceeding.
<img width="1022" height="830" alt="26-prerequisites-check" src="https://github.com/user-attachments/assets/b3861b88-037f-4da1-a61c-beedae49c7e5" />

**Screenshot 27: Domain Administrator Sign-In**

After the server restarted following promotion, the sign-in screen displayed `AD\Administrator`, showing that the domain administrator account was available for sign-in.
<img width="1019" height="825" alt="27-admin-sign-in" src="https://github.com/user-attachments/assets/a3ea95c8-b504-40f4-9eea-6fc2ac4378c0" />

**Screenshot 28: Server Manager After Domain Controller Promotion**

Server Manager displayed the Active Directory Domain Services and DNS roles after the server was promoted to a domain controller.
<img width="1025" height="830" alt="28-server-manager-after-promotion" src="https://github.com/user-attachments/assets/59967fd9-9229-4eae-9a1d-1175befb3f7d" />

**Screenshot 29: Active Directory Users and Computers**

Active Directory Users and Computers was opened, and the newly created `ad.lab` domain was visible in the console.
<img width="1023" height="829" alt="29-Active-directory-users-and-computers" src="https://github.com/user-attachments/assets/4479dd58-3255-457d-b8f0-ca3268a8b64c" />

**Screenshot 30: Domain Controllers Container**

The Domain Controllers container displayed the server as a domain controller, with the Global Catalog (GC) designation visible.
<img width="1025" height="832" alt="30-domain-controllers" src="https://github.com/user-attachments/assets/58a1f229-ea9a-48ed-89c1-cc0203bfa1d0" />

**Screenshot 31: DNS Manager Overview**

DNS Manager displayed the server and its DNS management sections, including Forward Lookup Zones and Reverse Lookup Zones.
<img width="1025" height="829" alt="31-dns-manager" src="https://github.com/user-attachments/assets/5e8a7964-2792-40ca-86b6-951550e63f6a" />

**Screenshot 32: Active Directory DNS Zones**

The Forward Lookup Zones section displayed the `ad.lab` and `_msdcs.ad.lab` zones, both with a Running status.
<img width="1023" height="831" alt="32-active-directory-dns-zones" src="https://github.com/user-attachments/assets/7b9f3272-3941-4c46-9f1c-f69b1716eb10" />



## Step 5: Open Active Directory Users and Computers

**Goal:** Access the tool used to manage domain accounts.

### Procedure

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
