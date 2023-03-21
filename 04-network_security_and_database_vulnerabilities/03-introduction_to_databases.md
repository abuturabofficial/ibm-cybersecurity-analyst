<!-- START doctoc generated TOC please keep comment here to allow auto update -->
<!-- DON'T EDIT THIS SECTION, INSTEAD RE-RUN doctoc TO UPDATE -->
**Table of Contents**

- [Types of Data](#types-of-data)
  - [Data Source Types](#data-source-types)
  - [Data Model Types](#data-model-types)
    - [Structured Data](#structured-data)
    - [Semi-Structured Data](#semi-structured-data)
    - [Unstructured Data](#unstructured-data)
      - [Types of Unstructured Data](#types-of-unstructured-data)
  - [Structured Data](#structured-data-1)
    - [Flat File Databases](#flat-file-databases)
    - [Relational Databases](#relational-databases)
- [Securing Databases](#securing-databases)
  - [Securing your “Crown Jewels”](#securing-your-crown-jewels)
  - [Leveraging Security Industry Best Practices](#leveraging-security-industry-best-practices)
  - [Structured Data and Relational Databases](#structured-data-and-relational-databases)
  - [Anatomy of a Vulnerability Assessment Test Report](#anatomy-of-a-vulnerability-assessment-test-report)
  - [Securing Data Sources by Type](#securing-data-sources-by-type)
- [A Data Protection Solution Example, IBM Security Guadium Use Cases](#a-data-protection-solution-example-ibm-security-guadium-use-cases)
  - [Data Monitoring](#data-monitoring)
    - [Data Activity Monitoring/Auditing/Logging](#data-activity-monitoringauditinglogging)

<!-- END doctoc generated TOC please keep comment here to allow auto update -->

# Types of Data

## Data Source Types

- Distributed Databases
	- Microsoft SQL Server, DB2, Oracle, MySQL, SQLite, Postgres etc.
	- Structured Data
- Data Warehouses
	- Amazon’s redshift, Netezza, Exadata, Apache Hive etc.
	- Structured Data
- Big Data
	- Google BigTable, Hadoop, MongoDB etc.
	- Semi-Structured Data
- File Shares
	- NAS (Network Attached Storage), Network fileshares such as EMC or NetApp; and Cloud Shares such as Amazon S3, Google Drive, Dropbox, Box.com etc.
	- Unstructured-Data

![](images/Pasted%20image%2020230321094918.png)

## Data Model Types

### Structured Data

“Structured data is data that has been organized into a formatted repository, typically a database, so that its elements can be made addressable for more effective processing and analysis.”

### Semi-Structured Data

“Semi-structured data is data that has not been organized into a specialized repository, such as a database, but that nevertheless has associated information, such as metadata, that makes it more amenable to processing than raw data.”
- A Word document with tags and keywords.

### Unstructured Data

“Unstructured data is information, in many forms, that doesn’t hew to conventional data models and thus typically isn’t a good fit for a mainstream relational database.”
- A Word Document, transaction data etc.

#### Types of Unstructured Data

- Text (most common type)
- Images
- Audio
- Video

## Structured Data

### Flat File Databases

Flat-file databases take all the information from all the records and store everything in one table. 
- This works fine when you have some records related to a single topic, such as a person’s name and phone numbers.
- But if you have hundreds or thousands of records, each with a number of fields, the database quickly becomes difficult to use.

### Relational Databases

Relational databases separate a mass of information into numerous **tables**. All columns in each table should be about one topic, such as “student information”, “class Information”, or “trainer information”.
- The tables for a relational database are linked to each other through the use of **Keys**. Each table may have one **primary key** and any number of **foreign keys**. A **foreign key** is simply a **primary key** from one table that has been placed in another table.
- The most important rules for designing relational databases are called **Normal Forms**. When databases are designed properly, huge amounts of information can be kept under control. This lets you **query** the database (search for information section) and quickly get the answer you need.

![](images/Pasted%20image%2020230321095449.png)

# Securing Databases

## Securing your “Crown Jewels”

![](images/Pasted%20image%2020230321100228.png)

## Leveraging Security Industry Best Practices

**Enforce:**
- DOD STIG
- CIS (Center for Internet Security)
- CVE (Common Vulnerability and Exposures)

**Secure:**
- Privileges
- Configuration settings
- Security patches
- Password policies
- OS level file permission

**Established Baseline:**
User defined queries for custom tests to meet baseline for;
- Organization
- Industry
- Application
- Ownership and access for your files

**Forensics:**
Advanced Forensics and Analytics using custom reports
- Understand your sensitive data risk and exposure

## Structured Data and Relational Databases

Perhaps the most common day-to-day use case for a database is using it as the backend of an application, such as your organization HR system, or even your organization's email system!

![](images/Pasted%20image%2020230321103028.png)

## Anatomy of a Vulnerability Assessment Test Report

![](images/Pasted%20image%2020230321103259.png)

## Securing Data Sources by Type

![](images/Pasted%20image%2020230321103622.png)

# A Data Protection Solution Example, IBM Security Guadium Use Cases

## Data Monitoring

### Data Activity Monitoring/Auditing/Logging

- Does your product log all key activity generation, retrieval/usage, etc.?
- Demo data access activity monitoring and logging of the activity monitoring?
- Does your product monitor for unique user identities (including highly privileged users such as admins and developers) with access to the data?
- At the storage level, can it detect/identify access to highly privileged users such as database admins, system admins or developers?
- Does your product generate real time alerts of policy violations while recording activities?
- Does your product monitor user data access activity in real time with customizable security alerts and blocking unacceptable user behavior, access patterns or geographic access, etc.? If yes, please describe.
- Does your product generate alerts?
- Demo the capability for reporting and metrics using information logged.
- Does your product create auditable reports of data access and security events with customizable details that can address defined regulations or standard audit process requirements? If yes, please describe.
- Does your product support the ability to log security events to a centralized security incident and event management (SIEM) system?
- Demo monitoring of non-Relational Database Management Systems (nRDBMS) systems, such as Cognos, Hadoop, Spark, etc.
