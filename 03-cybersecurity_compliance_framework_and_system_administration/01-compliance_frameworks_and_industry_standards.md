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

