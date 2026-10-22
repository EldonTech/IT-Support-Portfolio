# Active Directory Home Lab

## 1. Overview

**Objective:** Build a Windows Server environment to practice Active Directory administration and common IT Help Desk tasks.

**Environment:**
- Virtualization software: Oracle VirtualBox
- Host operating system: Windows 11
- Server operating system: Windows Server 2025 Standard Evaluation
- Domain name: `ad.lab`
- Domain NetBIOS name: `AD`
- Active Directory role: Active Directory Domain Services (AD DS)
- DNS: Installed on the domain controller

## 2. Lab Goals

- Install and configure Windows Server.
- Install Active Directory Domain Services.
- Create a new Active Directory domain.
- Create and organize user accounts using an Organizational Unit (OU).
- Reset user passwords.
- Require users to change their password at the next logon.

## 3. Configuration

- **Domain:** `ad.lab`
- **Organizational Unit:** `Help Desk Users`
- **Test user:** Jamie Smith
- **Username:** `jsmith`

## 4. Tasks Completed

### Task 1: Install Windows Server

Installed Windows Server 2025 Standard Evaluation (Desktop Experience) in a VirtualBox virtual machine.

### Task 2: Configure Active Directory

Installed Active Directory Domain Services and promoted the server to a domain controller for the new `ad.lab` forest.

### Task 3: Create an Organizational Unit

Created an OU named `Help Desk Users` to organize test user accounts.

### Task 4: Create a User Account

Created a test account for Jamie Smith with the username `jsmith` inside the `Help Desk Users` OU.

### Task 5: Reset a User Password

Used Active Directory Users and Computers to reset the test user's password and enable the requirement to change the password at the next logon.

## 5. Skills Practiced

- Windows Server installation
- Active Directory Domain Services configuration
- Domain controller promotion
- Organizational Unit management
- User account creation
- Password resets
- Basic Windows Server administration
- Technical documentation

## 6. Future Improvements

- Create additional users and security groups.
- Practice disabling and re-enabling user accounts.
- Configure a separate Windows client virtual machine.
- Join the client computer to the `ad.lab` domain.
- Practice troubleshooting domain sign-in and DNS issues.
- Capture screenshots of key configuration steps.

## 7. Results

Successfully created a Windows Server 2025 domain controller and configured a basic Active Directory environment. Created a test user account and practiced a password reset, demonstrating foundational tasks relevant to IT Help Desk and IT Support roles.
