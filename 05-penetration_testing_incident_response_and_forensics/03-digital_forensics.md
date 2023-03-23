<!-- START doctoc generated TOC please keep comment here to allow auto update -->
<!-- DON'T EDIT THIS SECTION, INSTEAD RE-RUN doctoc TO UPDATE -->
**Table of Contents**

- [Forensics Overview](#forensics-overview)
  - [What are Forensics?](#what-are-forensics)
    - [Types of Data](#types-of-data)
    - [The Need for Forensics](#the-need-for-forensics)
    - [Objectives of Digital Forensics](#objectives-of-digital-forensics)
    - [Forensic Process – NIST](#forensic-process--nist)
- [The Forensic Process](#the-forensic-process)
  - [Data Collection and Examination](#data-collection-and-examination)
    - [Examination](#examination)
      - [Steps to Collect Data](#steps-to-collect-data)
      - [Overview of Chain of Custody](#overview-of-chain-of-custody)
    - [Examination](#examination-1)
  - [Analysis & Reporting](#analysis--reporting)
    - [Analysis](#analysis)
      - [Putting the pieces together](#putting-the-pieces-together)
    - [Writing your forensic report](#writing-your-forensic-report)
      - [Report Composition](#report-composition)
      - [SANS Institute Best Practices](#sans-institute-best-practices)
- [Forensic Data](#forensic-data)
  - [Data Files](#data-files)
    - [What's not there](#whats-not-there)
    - [MAC data](#mac-data)
    - [Tools for Techniques](#tools-for-techniques)
  - [Operating System Data](#operating-system-data)
    - [Collection & Prioritization of Volatile Data](#collection--prioritization-of-volatile-data)
    - [Collecting Non-Volatile Data](#collecting-non-volatile-data)
      - [Logs](#logs)
    - [Windows](#windows)
    - [macOS](#macos)
    - [Linux](#linux)
  - [Application Data](#application-data)
    - [Application Components](#application-components)
    - [Types of Applications](#types-of-applications)
      - [Email](#email)
      - [Web Usage](#web-usage)
    - [Collecting the Application Data](#collecting-the-application-data)
  - [Network Data](#network-data)
    - [TCP/IP](#tcpip)
    - [Sources of Network Data](#sources-of-network-data)
      - [Data Value](#data-value)
    - [Attacker Identification](#attacker-identification)

<!-- END doctoc generated TOC please keep comment here to allow auto update -->

# Forensics Overview

## What are Forensics?

“Digital forensics, also known as computer and network forensics, has many definitions. Generally, it is considered the application of science to the identification, collection, examination, and analysis of data while preserving the integrity of the information and maintaining a strict chain of custody for the data.”

### Types of Data

The first step in the forensic process is to identify potential sources of data and acquire data from them. The most obvious and common sources of data are desktop computers, servers, network storage devices, and laptops.
- CDs/DVDs
- Internal & External Drives
- Volatile data
- Network Activity
- Application Usage
- Portable Digital Devices
- Externally Owned Property
- Computer at Home Office
- Alternate Sources of Data
- Logs
- Keystroke Monitoring

### The Need for Forensics

- Criminal Investigation
- Incident Handling
- Operational Troubleshooting
- Log Monitoring
- Data Recovery
- Data Acquisition
- Due Diligence/Regulatory Compliance

### Objectives of Digital Forensics

- It helps to recover, analyze, and preserve computer and related materials in such a manner that it helps the investigation agency to present them as evidence in a court of law. It helps to postulate the motive behind the crime and identity of the main culprit.
- Designing procedures at a suspected crime scene, which helps you to ensure that the digital evidence obtained is not corrupted.
- Data acquisition and duplication: Recovering deleted files and deleted partitions from digital media to extract the evidence and validate them.
- Help you to identify the evidence quickly, and also allows you to estimate the potential impact of the malicious activity on the victim.
- Producing a computer forensic report, which offers a complete report on the investigation process.
- Preserving the evidence by following the chain of custody.

### Forensic Process – NIST

**Collection**
Identify, label, record, and acquire data from the possible sources, while preserving the integrity of the data.

**Examination**
Processing large amounts of collected data to assess and extract of particular interest.

**Analysis**
Analyze the results of the examination, using legally justifiable methods and techniques.

**Reporting**
Reporting the results of the analysis.

# The Forensic Process

## Data Collection and Examination

### Examination

#### Steps to Collect Data

**Develop a plan to acquire the data**
Create a plan that prioritizes the sources, establishing the order in which the data should be acquired.

**Acquire the Data**
Use forensic tools to collect the volatile data, duplicate non-volatile data sources, and securing the original data sources.

**Verify the integrity of the data**
Forensic tools can create hash values for the original source, so the duplicate can be verified as being complete and untampered with.

#### Overview of Chain of Custody

A clearly defined chain of custody should be followed to avoid allegations of mishandling or tampering of evidence. This involves keeping a log of every person who had physical custody of the evidence, documenting the actions that they performed on the evidence and at what time, storing the evidence in a secure location when it is not being used, making a copy of the evidence and performing examination and analysis using only the copied evidence, and verifying the integrity of the original and copied evidence.

### Examination

**Bypassing Controls**
OSs and applications may have data compression, encryption, or ACLs.

**A Sea of Data**
Hard drives may have hundreds of thousands of files, not all of which are relevant.

**Tools**
There are various tools and techniques that exist to help filter and exclude data from searches to expedite the process.

## Analysis & Reporting

### Analysis

“The analysis should include identifying people, places, items, and events, and determining how these elements are related so that a conclusion can be reached.”

#### Putting the pieces together

Coordination between multiple sources of data is crucial in making a complete picture of what happened in the incident. NIST provides the example of an IDS log linking an event to a host. The host audit logs linking the event to a specific user account, and the host IDS log indicating what actions that user performed.

### Writing your forensic report

A case summary is meant to form the basis of opinions. While there are a variety of laws that relate to expert reports, the general rules are:
- If it is not in your report, you cannot testify about it.
- Your report needs to detail the basis for your conclusions.
- Detail every test conducted, the methods and tools used, and the results.

#### Report Composition

1) Overview/Case Summary
2) Forensic Acquisition & Examination Preparation
3) Finding & report (analysis)
4) Conclusion

#### SANS Institute Best Practices

1) Take Screenshots
2) Bookmark evidence via forensic application of choice
3) Use built-in logging/reporting options within your forensic tool
4) Highlight and exporting data items into .csv or .txt files
5) Use a digital audio recorder vs. handwritten notes when necessary

# Forensic Data

## Data Files

### What's not there

**Deleted files**
When a file is deleted, it is typically not erased from the media; instead, the information in the directory’s data structure that points to the location of the file is marked as deleted.

**Slack Space**
If a file requires less space than the file allocation unit size, an entire file allocation unit is still reserved for the file.

**Free Space**
Free space is the area on media that is not allocated to any partition, the free space may still contain pieces of data.

### MAC data

It's important to know as much information about relevant files as possible. Recording the modification, access, and creation times of files allows analysts to help establish a timeline of the incident.
1) Modification Time
2) Access Time
3) Creation Time

| Logical Backup                                                                                                                                                                                             | Imaging                                                                                                                                                                                 |
| ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| A logical data backup copies the directories and files of a logical volume. It does not capture other data that may be present on the media, such as deleted files or residual data stored in slack space. | Generates a bit-for-bit copy of the original media, including free space and slack space. Bit stream images require more storage space and take longer to perform than logical backups. |
| Can be used on live systems if using a standard backup software                                                                                                                                            | If evidence is needed for legal or HR reasons, a full bit stream image should be taken, and all analysis done on the duplicate                                                          |
| May be resource intensive                                                                                                                                                                                  | Disk-to-disk vs Disk-to-File                                                                                                                                                            |
|                                                                                                                                                                                                            | Should not be use on a live system since data is always chaning                                                                                                                         | 

### Tools for Techniques

Many forensic products allow the analyst to perform a wide range of processes to analyze files and applications, as well as collecting files, reading disk images, and extracting data from files.
- File Viewers
- Uncompressing Files
- GUI for Data Structure
- Identifying Known Files
- String Searches & Pattern Matches
- Metadata

## Operating System Data

“OS data exists in both non-volatile and volatile states. Non-volatile data refers to data that persists even after a computer is powered down, such as a filesystem stored on a hard drive. Volatile data refers to data on a live system that is lost after a computer is powered down, such as the current network connections to and from the system.”

| Volatile                          | Non-Volatile        |
| --------------------------------- | ------------------- |
| Slack Space                       | Configuration Files |
| Free Space                        | Logs                |
| Network configuration/connections | Application files   |
| Running processes                 | Data Files          |
| Open Files                        | Swap Files          |
| Login Sessions                    | Dump Files          |
| Operating System Time             | Hibernation Files   |
|                                   | Temporary Files     | 

### Collection & Prioritization of Volatile Data

1) Network Connections
2) Login Sessions
3) Contents of Memory
4) Running Processes
5) Open Files
6) Network Configuration
7) Operating System Time

### Collecting Non-Volatile Data

1) Consider Power-Down Options
2) File System Data Collected
3) Users and Groups
4) Passwords
5) Network Shares
6) Logs

#### Logs

Other logs can be collected depending on the incident under analysis:
1) **In case of a network hack**:
Collect logs of all the network devices lying in the route of the hacked devices and the perimeter router (ISP router). Firewall rule base may also be required in this case.
2) **In case it is unauthorized access**:
Save the web server logs, application server logs, application logs, router or switch logs, firewall logs, database logs, IDS logs etc.
3) **In case of a Trojan/Virus/Worm attack**:
Save the antivirus logs apart from the event logs (pertaining to the antivirus).

### Windows

- The file systems used by Windows include FAT, exFAT, NTFS, and ReFS.

Investigators can search out evidence by analyzing the following important locations of the Windows:
- Recycle Bin
- Registry
- Thumbs.db
- Files
- Browser History
- Print Spooling

### macOS

- Mac OS X is the UNIX bases OS that contains a Mach 3 microkernel and a FreeBSD based subsystem. Its user interface is Apple like, whereas the underlying architecture is UNIX like.
- Mac OS X offers novel techniques to create a forensic duplicate. To do so, the perpetrator’s computer should be placed into a “Target Disk Mode”. Using this mode, the forensic examiner creates a forensic duplicate of the perpetrator’s hard disk with the help of a FireWire cable connection between the two PCs.

### Linux

Linux can provide an empirical evidence of if the Linux embedded machine is recovered from a crime scene. In this case, forensic investigators should analyze the following folders and directories.
- /etc[%SystemRoot%/System32/config]
- /var/log
- /home/$USER
- /etc/passwd

## Application Data

OSs, files, and networks are all needed to support applications: OSs to run the applications, networks to send application data between systems, and files to store application data, configuration settings, and the logs. From a forensic perspective, applications bring together files, OSs, and networks. — NIST 800-86

### Application Components

- Config Settings
	- Configuration file
	- Runtime Options
	- Added to Source Code
- Authentication
	- External Authentication
	- Proprietary Authentication
	- Pass-through authentication
	- Host/User Environment
- Logs
	- Event
	- Audit
	- Error
	- Installation
	- Debugging
- Data
	- Can live temporary in memory and/or permanently in files
	- File format may be generic or proprietary
	- Data may be stored in databases
	- Some applications create temp files during session or improper shutdown
- Supporting Files
	- Documentation
	- Links
	- Graphics
- App Architecture
	- Local
	- Client/Server
	- Peer-to-Peer

### Types of Applications

Certain of application are more likely to be the focus of forensic analysis, including email, Web usage, interactive messaging, file-sharing, document usage, security applications, and data concealment tools.

![](images/Pasted%20image%2020230323123847.png)

#### Email

“From end to end, information regarding a single email message may be recorded in several places – the sender’s system, each email server that handles the message, and the recipient’s system, as well as the antivirus, spam, and content filtering server.” — NIST 800-45

#### Web Usage

| Web Data from Host                                                                                        | Web Data from Server                                                                                                 |
| --------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------- |
| Typically, the richest sources of information regarding web usage are the hosts running the web browsers. | Another good source of web usage information is web servers, which typically keep logs of the requests they receive. |
|                                                                                                           |                                                                                                                      |
| Favorite websites                                                                                         | Timestamps                                                                                                           |
| History w/timestamps of websites visited                                                                  | IP Addresses                                                                                                         |
| Cached web data files                                                                                     | Web browesr version                                                                                                  |
| Cookies                                                                                                   | Type of request                                                                                                      |
|                                                                                                           | Resource requested                                                                                                   | 

### Collecting the Application Data

Overview
![](images/Pasted%20image%2020230323124544.png)

## Network Data

“Analysts can use data from network traffic to reconstruct and analyze network-based attacks and inappropriate network usage, as well as to troubleshoot various types of operational problems. The term network traffic refers to computer network communications that are carried over wired or wireless networks between hosts.” — NIST 800-86

### TCP/IP

![](images/Pasted%20image%2020230323124827.png)

### Sources of Network Data

These sources collectively capture important data from all four TCP/IP layers.

![](images/Pasted%20image%2020230323125108.png)

#### Data Value

- IDS Software
- SEM Software
- NFAT Software (Network Forensic Analysis Tool)
- Firewall, Routers, Proxy Servers, & RAS
- DHCP Server
- Packet Sniffers
- Network Monitoring
- ISP Records

### Attacker Identification

“When analyzing most attacks, identifying the attacker is not an immediate, primary concern: ensuring that the attack is stopped and recovering systems and data are the main interests.” — NIST 800-86

1) **Contact IP Address Owner**
Can help identify who is responsible for an IP address, Usually an escalation.

2) **Send Network Traffic**
Not recommended for organizations

3) Application Content
Data packets could contain information about the attacker’s identity.

4) **Seek ISP Assistance**
Requires court order and is only done to assist in the most serious of attacks.

5) **History of IP address**
Can look for trends of suspicious activity.
