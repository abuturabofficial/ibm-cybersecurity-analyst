<!-- START doctoc generated TOC please keep comment here to allow auto update -->
<!-- DON'T EDIT THIS SECTION, INSTEAD RE-RUN doctoc TO UPDATE -->
**Table of Contents**

- [Introduction to Windows Administration](#introduction-to-windows-administration)
  - [User and Kernel Modes](#user-and-kernel-modes)
  - [File Systems](#file-systems)
  - [Typical Windows Directory Structure](#typical-windows-directory-structure)
- [Role-Based Access Control and Permissions](#role-based-access-control-and-permissions)
  - [Privileged Accounts](#privileged-accounts)
    - [Access Control](#access-control)
  - [Local User Accounts](#local-user-accounts)
    - [Management of Local Users accounts and Security Considerations](#management-of-local-users-accounts-and-security-considerations)
- [Features of Active Directory](#features-of-active-directory)
  - [What is AD?](#what-is-ad)
    - [Features of AD DS](#features-of-ad-ds)
  - [Active Directory Accounts and Security Considerations](#active-directory-accounts-and-security-considerations)
    - [AD Accounts](#ad-accounts)
    - [Restrict and Protect sensitive domain accounts](#restrict-and-protect-sensitive-domain-accounts)
- [Overview of Server Management with Windows Admin Center](#overview-of-server-management-with-windows-admin-center)
  - [Active Directory Groups](#active-directory-groups)
    - [Groups scope](#groups-scope)
    - [What is Windows Admin Center?](#what-is-windows-admin-center)
- [Windows Security and Compliance Topics](#windows-security-and-compliance-topics)
  - [Kerberos Authentication and Logs](#kerberos-authentication-and-logs)
    - [Kerberos Authentication](#kerberos-authentication)
    - [Windows Server Logs](#windows-server-logs)
  - [Windows Auditing Overview](#windows-auditing-overview)
    - [Audit Policy](#audit-policy)
- [Linux Components](#linux-components)
  - [Common Shells](#common-shells)
      - [Bash:](#bash)
      - [Sh:](#sh)
      - [Tcsh:](#tcsh)
      - [CSH:](#csh)
      - [Ksh:](#ksh)
      - [ZSH:](#zsh)
  - [Linux Internal and External Commands](#linux-internal-and-external-commands)
    - [Internal Commands:](#internal-commands)
    - [External commands:](#external-commands)
    - [Shell command Tricks:](#shell-command-tricks)
- [Samba](#samba)

<!-- END doctoc generated TOC please keep comment here to allow auto update -->

# Introduction to Windows Administration

## User and Kernel Modes

MS Windows Components:
- User Mode
	- Private Virtual address space
	- Private handle table
	- Application isolation
- Kernel Mode
	- Single Virtual Address, shared by other kernel processes

## File Systems

Types of file systems in Windows
- NTFS (New Technology File system)
- FATxx (File Allocation Table)
	- FAT16, FAT32

## Typical Windows Directory Structure

![](images/Pasted%20image%2020230311143515.png)

# Role-Based Access Control and Permissions

- Access Control Lists (ACLs)
- Principle of the least privileges

## Privileged Accounts

- Privileged accounts like admins of Windows services have direct or indirect access to most or all assets in an IT organization.
- Admins will configure Windows to manage access control to provide security for multiple roles and uses.

### Access Control

Key concepts that make up access control are:
- Permissions
- Ownership of objects
- Inheritance of permissions
- User rights
- Object auditing

## Local User Accounts

Default local user accounts:
- Administrator account
- Guest account
- HelpAssistant account
- DefaultAccount

Default local system accounts:
- SYSTEM
- Network Service
- Local Service

### Management of Local Users accounts and Security Considerations

- Restrict and protect local accounts with administrative rights
- Enforce local account restrictions for remote access
- Deny network logon to all local Administrator accounts
- Create unique passwords for local accounts with administrative rights

# Features of Active Directory

## What is AD?

Active Directory Domain Services (AD DS) stores information about objects on the network and makes this information easy for administrators and users to find and use.
- Servers
- Volumes
- Printers
- Network user and computer accounts
- Security is integrated with AD through authentication and access control to objects in the directory via policy-based administration.

### Features of AD DS

- A set of rules, the schema
- A global catalog
- A query and index mechanism
- A replication service

## Active Directory Accounts and Security Considerations

### AD Accounts

- Default local accounts in AD:
	- Administrator account
	- Guest Account
	- HelpAssistant Account
	- KRBTGT account (system account)
- Settings for default local accounts in AD
- Manage default local accounts in AD
- Secure and Manage domain controllers

### Restrict and Protect sensitive domain accounts

**Separate admin accounts from user accounts**

- **Privileged accounts**: Allocate admin accounts to perform the following
	- **Minimum:** Create separate accounts for domain admins, enterprise admins, or the equivalent with appropriate admin.
	- **Better:** Create separate accounts for admins that have reduced admin rights, such as accounts for workstation admins, account with user rights over designated AD organizational units (OUs)
	- **Ideal:** Create multiples, separate accounts for an administrator who has a variety of job responsibilities that require different trust levels
- **Standard User account:** Grant standard user rights for standard user tasks, such as email, web browsing, and using line-of-business (LOB) applications.

**Create dedicated workstation hosts without Internet and email access**

- Admins need to manage job responsibilities that require sensitive admin rights from a dedicated workstation because they don’t have easy physical access to the servers.
	- **Minimum:** Build dedicated admin workstations and block Internet Access on those workstations, including web browsing and email.
	- **Better:** Don’t grant admins membership in the local admin group on the computer in order to restrict the admin from bypassing these protections.
	- **Ideal:** Restrict workstations from having any network connectivity, except for the domain controllers and servers that the administrator accounts are used to manage.

**Restrict administrator logon access to servers and workstations**

- It is a best practice to restrict admins from using sensitive admin accounts to sign-in to lower-trust servers and workstations.
- Restrict logon access to lower-trust servers and workstations by using the following guidelines:
	- **Minimum:** Restrict domain admins from having logon access to servers and workstations. Before starting this procedure, identify all OUs in the domain that contain workstations and servers. Any computers in OUs that are not identified will not restrict admins with sensitive accounts from signing-in to them.
	- **Better:** Restrict domain admins from non-domain controller servers and workstations.
	- **Ideal:** Restrict server admins from signing in to workstations, in addition to domain admins.

**Disable the account delegation right for administrator accounts**

- Although user accounts are not marked for delegation by default, accounts in an AD domain can be trusted for delegation. This means that a service or a computer that is trusted for delegation can impersonate an account that authenticates to the to access other resources across the network.
- It is a best practice to configure the user objects for all sensitive accounts in AD by selecting the **Account is sensitive and cannot be delegated** check box under **Account options** to prevent accounts from being delegated.

![](images/Pasted%20image%2020230311152936.png)

# Overview of Server Management with Windows Admin Center

## Active Directory Groups

Security groups are used to collect user accounts, computer accounts, and other groups into manageable units.

- For AD, there are two types of admin responsibilities:
	- Server Admins
	- Data Admins
- There are two types of groups in AD:
	- **Distribution groups:** Used to create email distribution lists.
	- **Security groups:** Used to assign permissions to shared resources.

### Groups scope

Groups are characterized by a scope that identifies the extent to which the group is applied in the domain tree or forest.

The following three group scopes are defined by AD:
- Universal
- Global
- Domain Local

Default groups, such as the Domain Admins group, are security groups that are created automatically when you create an AD domain. You can use these predefined groups to help control access to shared resources and to delegate specific domain-wide admin roles.

### What is Windows Admin Center?

- Windows Admin Center is a new, locally-deployed, browser-based management tool set that lets you manage your Windows Servers with no cloud dependency.
- Windows Admin Center gives you full control over all aspects of your server infrastructure and is useful for managing servers on private networks that not connected to the Internet.

# Windows Security and Compliance Topics

## Kerberos Authentication and Logs

### Kerberos Authentication

Kerberos is an authentication protocol that is used to verify the identity of a user or host.
- The Kerberos Key Distribution Center (KDC) is integrated with other Windows Server security services and uses the domain’s AD DS database.
- The key Benefits of using Kerberos include:
	- Delegated authentication
	- Single sign on
	- Interoperability
	- More efficient authentication to servers
	- Mutual authentication

### Windows Server Logs

- **Windows Event Log**, the most common location for logs on Windows.
- Windows displays its event logs in the **Windows Event Viewer**. This application lets you view and navigate the Windows Event Log, search and filter on particular types of logs, export them for analysis, and more.

## Windows Auditing Overview

### Audit Policy

- Establishing audit policy is an important facet of security. Monitoring the creation o modification of objects gives you a way to track potential security problems, helps to ensure user accountability, and provides evidence in the event of a security breach.
- There are nine different kinds of events you can audit. If you audit any of those kinds of events, Windows records the events in the Security log, which you can find in the **Event Viewer**.
	- Account logon Events
	- Account Management
	- Directory service Access
	- Logon Events
	- Object access
	- Policy change
	- Privilege use
	- Process tracking
	- System events

# Linux Components

## Common Shells

#### Bash:

The GNU Bourne Again Shell (BASH) is based on the earlier Bourne Again shell for UNIX. On Linux, bash is the most common default shell for user accounts.

#### Sh:

The Bourne Shell upon which bash is based goes by the name sh. It’s not often used on Linux, often a pointer to the bash shell or other shells.

#### Tcsh:

This shell is based on the earlier C shell (CSH). Fairly popular, but no major Linux distributions make it the default shell. You don’t assign environment variables the same way in TCSH as in bash.

#### CSH:

The original C shell isn’t used much on Linux, but if a user is familiar with CSH, TCSh makes a good substitute.

#### Ksh:

The Korn shell (ksh) was designed to take the best features of the Bourne shell and the C shell and extend them. It has a small but dedicated following among Linux users.

#### ZSH:

The Z shell (zsh) takes shell evolution further than the Korn shell, incorporating features from earlier shells and adding still more.

## Linux Internal and External Commands

### Internal Commands:

- Built into the shell program and are shell dependent. Also called built-in commands.
- Determine if a command is a built-in command by using the `type` command.

### External commands:

- Commands that the system offers, are totally shell-independent and usually can be found in any Linux distribution
- They mostly reside in `/bin` and `/usr/bin`.

### Shell command Tricks:

- **Command completion:** Type part of a command or a filename (as an option to the command), and then press `TAB` key.
- **Use Ctrl+A or Ctrl+E:** To move the cursor to the start or end of the line, respectively.

# Samba

Samba is an Open Source/Free software suite that provides seamless file and print services. It uses the TCP/IP protocol that is installed on the host server.

When correctly configured, it allows that host to interact with an MS Windows client or server as if it is a Windows file and print server, so it allows for interoperability between Linux/Unix servers and Windows-based clients.
