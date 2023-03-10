<!-- START doctoc generated TOC please keep comment here to allow auto update -->
<!-- DON'T EDIT THIS SECTION, INSTEAD RE-RUN doctoc TO UPDATE -->
**Table of Contents**

- [Compliance and Regulation for Cybersecurity](#compliance-and-regulation-for-cybersecurity)
  - [What Cybersecurity Challenges do Organizations Face?](#what-cybersecurity-challenges-do-organizations-face)
    - [Event, attacks, and incidents defied](#event-attacks-and-incidents-defied)
      - [Security – How to stop “bad guys”](#security--how-to-stop-bad-guys)
  - [Compliance Basics](#compliance-basics)
    - [Security, Privacy, and Compliance](#security-privacy-and-compliance)
      - [Compliance: Specific Checklist of Security Controls, Validated](#compliance-specific-checklist-of-security-controls-validated)
    - [Compliance Basics](#compliance-basics-1)
      - [Any typical compliance process](#any-typical-compliance-process)
  - [Overview of US Cybersecurity Federal Law](#overview-of-us-cybersecurity-federal-law)
    - [Computer Fraud and Abuse Act (CFAA)](#computer-fraud-and-abuse-act-cfaa)
    - [US Federal Laws](#us-federal-laws)
  - [National Institute of Standards and Technology (NIST) Overview](#national-institute-of-standards-and-technology-nist-overview)
  - [General Data Protection Regulation (GDPR) Overview](#general-data-protection-regulation-gdpr-overview)
    - [Key terms for understanding](#key-terms-for-understanding)
  - [Internation Organization for Standardization (ISO) 2700x](#internation-organization-for-standardization-iso-2700x)
- [System and Organization Controls Report (SOC) Overview](#system-and-organization-controls-report-soc-overview)
  - [SOC Reports](#soc-reports)
    - [Why SOC reports?](#why-soc-reports)
    - [Compared with ISO 27001](#compared-with-iso-27001)
    - [SOC1 vs SOC2 vs SOC3](#soc1-vs-soc2-vs-soc3)
      - [Type 1 vs Type 2](#type-1-vs-type-2)
        - [Selecting the appropriate report type](#selecting-the-appropriate-report-type)
      - [Scoping Considerations – SOC 2 Principles](#scoping-considerations--soc-2-principles)
  - [SOC Reports – Auditor Process Overview](#soc-reports--auditor-process-overview)
    - [What are auditors looking for:](#what-are-auditors-looking-for)
    - [What does SOC1/SOC2 Test](#what-does-soc1soc2-test)
      - [Continuous Monitoring – Between audits](#continuous-monitoring--between-audits)
- [Industry Standards](#industry-standards)
  - [Health Insurance Portability and Accountability Act (HIPAA)](#health-insurance-portability-and-accountability-act-hipaa)
    - [What is HIPAA-HITECH](#what-is-hipaa-hitech)
    - [HIPAA Definitions](#hipaa-definitions)
      - [Why is Compliance Essential?](#why-is-compliance-essential)
      - [HIPAA is a U.S. Regulation, so be aware…](#hipaa-is-a-us-regulation-so-be-aware)
      - [HIPAA Security Rule](#hipaa-security-rule)
        - [Administrative Safeguards](#administrative-safeguards)
        - [Technical Safeguards](#technical-safeguards)
        - [Physical Safeguards](#physical-safeguards)
  - [Payment Card Industry Data Security Standard (PCI DSS)](#payment-card-industry-data-security-standard-pci-dss)
    - [The PCI Data Security Standard](#the-pci-data-security-standard)
      - [Goals and Requirements](#goals-and-requirements)
      - [Scope](#scope)
      - [Determining Scope](#determining-scope)
      - [PCI Requirements](#pci-requirements)
- [Critical Security Controls](#critical-security-controls)
  - [Center for Internet Security (CIS) Critical Security Controls](#center-for-internet-security-cis-critical-security-controls)
    - [CIS Critical Security Controls](#cis-critical-security-controls)
    - [CIS Control<sup>TM</sup> 7](#cis-controlsuptmsup-7)
    - [CIS Control<sup>TM</sup> 7.1 Implementation Groups](#cis-controlsuptmsup-71-implementation-groups)
    - [Structure of the CIS Control<sup>TM</sup> 7.1](#structure-of-the-cis-controlsuptmsup-71)
- [Compliance Summary](#compliance-summary)

<!-- END doctoc generated TOC please keep comment here to allow auto update -->

# Compliance and Regulation for Cybersecurity

## What Cybersecurity Challenges do Organizations Face?

### Event, attacks, and incidents defied

**Security Event**
An event on a system or network detected by a security device or application.

**Security attack**
A security event that has been identified by correlation and analytics tools as malicious activity that attempting to collect, disrupt, deny, degrade, or destroy information system resources or the information itself.

**Security Incident**
An attack or security event that has been reviewed by security analysts and deemed worthy of deeper investigation.

#### Security – How to stop “bad guys”

**Outsider**
- They want to “get-in” – steal data, steal compute time, disrupt legitimate use
- Security baseline ensures we design secure offerings but setting implementation standards
- E.g. Logging, encryption, development, practices, etc.
- Validated through baseline reviews, threat models, penetration testing, etc.

**Inadvertent Actor**
- They are “in” – but are human and make mistakes
- Automate procedures to reduce error-technical controls
- Operational/procedural manual process safeguards
- Review logs/reports to find/fix errors. Test automation regularly for accuracy.

**Malicious Insiders**
- They are “in” – but are deliberately behaving badly
- Separation of duties – no shared IDs, limit privileged IDs
- Secure coding, logging, monitoring access/operations

## Compliance Basics

### Security, Privacy, and Compliance

**Security**
- Designed protection from theft or damage, disruption or misdirection
- Physical controls – for the servers in the data centers
- Technical controls
	- Features and functions of the service (e.g., encryption)
	- What log data is collected?
- Operational controls
	- How a server is configured, updated, monitored, and patched?
	- How staff are trained and what activities they perform?

**Privacy**
- How information is used, who that information is shared with, or if the information is used to track users?

**Compliance**
- Tests that security measures are in place.
- Which and how many depend on the specific compliance.
- It Will Often cover additional non-security requirements such as business practices, vendor agreements, organized controls etc.

#### Compliance: Specific Checklist of Security Controls, Validated

![](images/Pasted%20image%2020230308103313.png)

### Compliance Basics

**Foundational**
General specifications, (not specific to any industry) important, but generally not legally required.
Ex: SOC, ISO.

**Industry**
Specific to an industry, or dealing with a specific type of data. Often legal requirements.
Ex: HIPAA, PCI DSS

#### Any typical compliance process

![](images/Pasted%20image%2020230308103752.png)

- General process for any compliance/audit process
	- Scoping
		- “Controls” are based on the goal/compliance – 50–500.
		- Ensure all components in scope are compliant to technical controls.
		- Ensure all processes are compliant to operation controls.
	- Testing and auditing may be:
		- Internal/Self assessments
		- External Audit
	- Audit recertification schedules can be quarterly, bi-quarterly, annually, etc.

## Overview of US Cybersecurity Federal Law

### Computer Fraud and Abuse Act (CFAA)

- Enacted in 1984

### US Federal Laws

- Federal Information Security Management Act of 2002 (FISMA)
- Federal Information Security Modernization Act of 2014 (FISMA 2014)

FISMA assigns specific responsibilities to federal agencies, the National Institute of Standards and Technology (NIST) and the Office of Management and Budget (OMB) in order to strengthen information security systems.

## National Institute of Standards and Technology (NIST) Overview

**Cybersecurity and Privacy**
NIST’s cybersecurity and privacy activities strengthen the security digital environment. NIST’s sustained outreach efforts support the effective application of standards and best practices, enabling the adoption of practical cybersecurity and privacy.

## General Data Protection Regulation (GDPR) Overview

This is simply a standard for EU residence:
- Compliance
- Data Protection
- Personal Data
The GDPR cam into effect on **25 May 2018** and represents the biggest change in data privacy in two decades. The legislation aims to give control back to individuals located in EU over their Personal Data and simplify the regulatory environment for internation businesses.

5 Key GDPR Obligations:
1) Rights of EU Data subjects
2) Security of Personal Data
3) Consent
4) Accountability of Compliance
5) Data Protection by Design and by Default

### Key terms for understanding

![](images/Pasted%20image%2020230309101727.png)

## Internation Organization for Standardization (ISO) 2700x

- The ISO 2700 family of standards help organization keep information assets secure.
- ISO/IEC 27001 is the best-known standard in the family providing requirements for an information security management systems (ISMS).
	- The standard provides requirements for establishing, implementing, maintaining and continually improving an information security management system.
- Also becoming more common,
	- ISO 270018 – Privacy
- Other based on industry/application, e.g.,
	- ISO 270017 – Cloud Security
- ISO 27001 Certification can provide credibility to a client of an organization.
- For some industries, certification is a legal or contractual requirement.
- ISO develops the standards but does not issue certifications.
- Organizations that meet the requirements may be certified by **an accredited certification body** following successful completion of an audit.

# System and Organization Controls Report (SOC) Overview

## SOC Reports

### Why SOC reports?

- Some industry/jurisdictions require SOC2 or local compliance audit.
- Many organizations who know compliance, know SOC Type 2 consider it a stronger statement of operational effectiveness than ISO 27001 (continuous testing).
- Many organization’s clients will accept SOC2 in lieu of the right-to-audit.

### Compared with ISO 27001

![](images/Pasted%20image%2020230309105451.png)

### SOC1 vs SOC2 vs SOC3

**SOC1**
- Used for situations where the systems are being used for financial reporting.
- Also referenced as Statement on Standards for Attestation Engagements (SSAE)18 AT-C 320 (formerly SSAE 16 or AT 801).

**SOC2**
- Addresses a service organization’s controls that are relevant to their operations and compliance, more generally than SOC1.
- Restricted use report contains substantial detail on the system, security practices, testing methodology and results.
- Also, SSAE 18 standards, sections AT-C 105 and AT-C 205.

**SOC3**
- General use report to provide interested parties with a CPA’s opinion about same controls in SOC2.

#### Type 1 vs Type 2

**Type 1 Report**
- Consider this the starting line.
- The service auditor expresses an opinion on whether the description of the service organization’s systems is fairly presented and whether the controls included in the description are suitably designed to meet the applicable Trust Service criteria as of a point in time.

**Type 2 Report**
- Proof you’re maintaining the effectiveness over time
- Typically 6 month, renewed either every 6 months or yearly.
- The service auditor’s report contains the same opinions expressed in a Type 1 report, but also includes an opinion on the operating effectiveness of the service organization’s controls for a period of time. Includes description of the service auditor’s **tests of operation effectiveness and test results**.

##### Selecting the appropriate report type

- A type 1 is generally only issued if the service organization’s system has not been in operation for a significant period of time, has recently made significant system or control changes. Or if it is the first year of issuing the report.
- SOC1 and SOC2, each available as Type 1 or Type 2.

#### Scoping Considerations – SOC 2 Principles

Report scope is defined based on the Trust Service Principles and can be expanded to additional subject.

![](images/Pasted%20image%2020230309111257.png)

## SOC Reports – Auditor Process Overview

### What are auditors looking for:

1) **Accuracy** → are controls results being assessed for pass/fail.
2) **Completeness** → do controls implementation cover the entire offering: e.g., no gaps in inventory, personnel, etc.
3) **Timeliness** → are controls performed on time (or early) with no gaps in coverage.
	-  If a control cannot be performed on time, are there appropriate assessment (risk) approvals **BEFORE** the control is considered ‘late’.
4) **With Resilience notice** → are there checks/balances in place such that if a control does fail, would you be able to correct at all? Within a reasonable timeframe?
5) **Consistency** → Shifting control implementation raises concerns about above, plus increases testing.

![](images/Pasted%20image%2020230309112038.png)

### What does SOC1/SOC2 Test

**General Controls:**
- Inventory listing
- HR Employee Listing
- Access group listing
- Access transaction log

**A: Organization and Management**
- Organizational Chart
- Vendor Assessments

**B: Communications**
- Customer Contracts
- System Description
- Policies and Technical Specifications

**C: Risk Management and Design/Implementation of Controls**
- IT Risk Assessment

**D: Monitoring of Controls**
- Compliance Testing
- Firewall Monitoring
- Intrusion Detection
- Vulnerability Management
- Access Monitoring

**E: Logical and Physical Access Controls**
- Employment Verification
- Continuous Business Need

**F: System Operations**
- Incident Management
- Security Incident Management
- Customer Security Incident Management
- Customer Security Incident Reporting

**G: Change Management**
- Change Management
- Communication of Changes

**H: Availability**
- Capacity Management
- Business Continuity
- Backup or equivalent

#### Continuous Monitoring – Between audits

**Purpose:**
- Ensure controls are operating as designed.
- Identify control weaknesses and failure outside an audit setting.
- Communicate results to appropriate stakeholders.

**Scope:**
- All production devices

Controls will be tested for operating effectiveness over time, focusing on:
- Execution against the defined security policies.
- Execution evidence maintenance/availability
- Timely deviation from policy documentation.
- Timely temporary failures of a control or loss of evidence documentation and communication.

# Industry Standards

## Health Insurance Portability and Accountability Act (HIPAA)

Healthcare organizations use cloud services to achieve more than saving and scalability:
- Foster virtual collaboration across care environments
- Leverage full potential of existing patient data
- Address challenges in analyzing patient needs
- Provide platforms for care innovation
- Expand delivery network
- Reduce response time in the case of emergencies
- Integrate data silos and optimizes information flow
- Increase resource utilization
- Simplify processes, reducing administration cost

### What is HIPAA-HITECH

- The US Federal laws and regulations that define the control of most personal healthcare information (PHI) for companies responsible for managing such data are:
	- **Health insurance Portability and Accountability Act (HIPAA)**
	- **Health Information Technology for Economic Clinical Health Act (HITECH)**
- The **HIPAA Privacy Rule** establishes standards to protect individuals’ medical records and other personal health information and applies to health plans, health care clearinghouses, and those health care providers who conduct certain health care transactions electronically.
- The **HIPAA Security Rule** establishes a set of security standards for protecting certain health information that is held or transferred in electronic form. The Security Rule operationalizes the protections contained in the Privacy Rule by addressing the technical and non-technical safeguards that must be put in place to secure individuals’ “electronic protected health information” (e-PHI)

### HIPAA Definitions

**U.S. Department of Health and Human Services (HHS) Office of Civil Rights (OCR):**
Governing entity for HIPAA.

**Covered Entity:**
HHS-OCR define companies that manage healthcare data for their customers as a Covered Entity.

**Business Associate:**
Any vendor company that supports the Covered Entity.

**Protected Health Information (PHI):**
Any information about health status, provision of health care, or payment for health care that is maintained by a Covered Entity (or a Business Associate of a Covered Entity), and can be linked to a specific individual.

**HHS-OCR “Wall of Shame”:**
Breach Portal: Notice to the Secretary of HHS Breach of Unsecured Protected Health Information.

#### Why is Compliance Essential?

- U.S. Law states that all individuals have the right to expect that their private health information be kept private and only be used to help assure their health.
- There are significant enforcement penalties if a Covered Entity / Business Associate is found in violation.
- HHS-OCR can do unannounced audits on the **(CE+BA)** or just the **BA**.

#### HIPAA is a U.S. Regulation, so be aware…

- Other countries have similar regulations / laws:
	- Canada – Personal Information Protection and Electronic Documents Act
	- European Union (EU) Data Protection Directive (GDPR)
- Many US states address patient privacy issues and are stricter than those set forth in HIPAA and therefore supersedes the US regulations.
- Some international companies will require HIPAA compliance for an either a measure of confidence, or because they intend to do business with US data.

#### HIPAA Security Rule

The Security Rule requires, covered entities to maintain reasonable and appropriate **administrative, technical**, and **physical safeguards** for protecting **“electronic protected health information” (e-PHI)**.

Specifically, covered entities must:
- Ensure the confidentiality, integrity, and availability of all e-PHI they create, receive, maintain or transmit.
- Identify and protect against reasonably anticipated threats to the security or integrity of the information.
- Protect against reasonably anticipated, impermissible uses or disclosures; and
- ensure compliance by their workforce.

##### Administrative Safeguards

The Administrative Safeguards provision in the Security Rule require covered entities to perform risk analysis as part of their security management processes.

Administrative Safeguards include:
- Security Management Process
- Security Personnel
- Information Access Management
- Workforce Training and Management
- Evaluation

##### Technical Safeguards

Technical Safeguards include:
- Access Control
- Audit Controls
- Integrity Controls
- Transmission Security

##### Physical Safeguards

Physical Safeguards include:
- Facility Access and Control
- Workstation and Device Security

## Payment Card Industry Data Security Standard (PCI DSS)

### The PCI Data Security Standard

- The PCI DSS was introduced in **2004**, by A**merican Express, Discover, MasterCard and Visa** in response to security breaches and financial losses within the credit card industry.
- Since 2006 the standard has been evolved and maintained by the **PCI Security Standards Council**, a “global organization, (it) maintains, evolves and promotes Payment Card Industry Standards for the safety of cardholder data across the globe.”
- The PCI Security Standards Council is now comprised of American Express, Discover, JCB International MasterCard and Visa Inc.
- Applies to all entities that store, process, and/or transmit cardholder data.
- Covers technical and operational practices for system components included in or connected to environments with cardholder data.
- PCI DSS 3.2 includes a total of **264 requirements** grouped under **12 main requirements**.

#### Goals and Requirements

PCI DSS 3.2 includes a total of **264 requirements** grouped under **12 main requirements**:

![](images/Pasted%20image%2020230310112559.png)

#### Scope

**The Cardholder Data Environment (CDE): People, processes and technology that store, process or transmit cardholder data or sensitive authentication data.**
- Cardholder Data:
	- Primary Account Number (PAN)
	- PAN plus any of the following:
		- Cardholder name
		- expiration date and/or service mode.

**Sensitive Authentication Data:**
- Security-related information (including but not limited to card validation codes/values, full track data (from the magnetic stripe or equivalent on a chip), PINs, and PIN blocks) used to authenticate cardholder and/or authorize payment card transactions.

**Sensitive Areas:**
- Anything that accepts, processes, transmits or stores cardholder data.
- Anything that houses systems that contain cardholder data.

#### Determining Scope

| People                         | Processes                 | Technologies                          |
| ------------------------------ | ------------------------- | ------------------------------------- |
| Compliance Personnel           | IT Governance             | Internal Network Segmentation         |
| Human Resources                | Audit Logging             | Cloud Application platform containers |
| IT Personnel                   | File Integrity Monitoring |                                       |
| Developers                     | Access Management         | Virtual LAN                           |
| System Admins and Architecture | Patching                  |                                       |
| Network Admins                 | Network Device Management |                                       |
| Security Personnel             | Security Assessments      |                                       |
|                                | Anti-Virus                |                                       | 

#### PCI Requirements

Highlight New and Key requirements:
- Approved Scanning Vendor (ASV) scans (quarterly, external, third party).
- Use PCI scan policy in Nessus for internal vulnerability scans.
- File Integrity Monitoring (FIM)
- Firewall review frequency every 6 months
- Automated logoff of idle session after 15 minutes
- Responsibility Matrix

# Critical Security Controls

## Center for Internet Security (CIS) Critical Security Controls

### CIS Critical Security Controls

- The CIS Controls<sup>TM</sup> are a prioritized set of actions that collectively form a defense-in-depth set of best practices that mitigate the most common attacks against systems and networks.
- The CIS Controls<sup>TM</sup> are developed by a community of IT experts who apply their first-hand experience as cyber defenders to create these globally accepted security best practices.
- The experts who develop the CIS Controls come from a wide range of sectors including retail, manufacturing, healthcare, education, government, defense, and others.

### CIS Control<sup>TM</sup> 7

![](images/Pasted%20image%2020230310114916.png)

### CIS Control<sup>TM</sup> 7.1 Implementation Groups

![](images/Pasted%20image%2020230310115024.png)

### Structure of the CIS Control<sup>TM</sup> 7.1

The presentation of each Control in this document includes the following elements:
- A description of the importance of the CIS Control (**Why is this control critical?**) in blocking or identifying the presence of attacks, and an explanation of how attackers actively exploit the absence of this Control.
- A table of the specific actions (**“Sub-Controls”**) that organizations should take to implement the Control.
- **Procedures and Tools** that enable implementation and automation.
- Sample **Entity Relationship Diagrams** that show components of implementation.

# Compliance Summary

![](images/Pasted%20image%2020230310120258.png)