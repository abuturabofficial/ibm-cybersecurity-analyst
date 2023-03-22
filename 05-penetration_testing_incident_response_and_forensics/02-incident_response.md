<!-- START doctoc generated TOC please keep comment here to allow auto update -->
<!-- DON'T EDIT THIS SECTION, INSTEAD RE-RUN doctoc TO UPDATE -->
**Table of Contents**

- [Incident Response Overview](#incident-response-overview)
  - [What is Incident Response?](#what-is-incident-response)
    - [**Events**](#events)
    - [**Incident**](#incident)
      - [Why Incident Response is Important](#why-incident-response-is-important)
    - [IR Team Models](#ir-team-models)
      - [Coordinating Teams](#coordinating-teams)
    - [Common Attack Vectors](#common-attack-vectors)
    - [Baseline Questions](#baseline-questions)
      - [Incident Response Phases](#incident-response-phases)
- [Incident Response Process](#incident-response-process)
  - [Incident Response Preparation](#incident-response-preparation)
    - [Incident Response Policy](#incident-response-policy)
      - [Resources](#resources)
      - [The Best Defense](#the-best-defense)
    - [Checklist](#checklist)
  - [Incident Response Detection and Analysis](#incident-response-detection-and-analysis)
    - [Precursors and Indicators](#precursors-and-indicators)
      - [Monitoring Systems](#monitoring-systems)
      - [Documentation](#documentation)
      - [Functional Impact Categories](#functional-impact-categories)
      - [Information Impact Categories](#information-impact-categories)
      - [Recoverability Effort Categories](#recoverability-effort-categories)
      - [Notifications](#notifications)
  - [Containment, Eradication & Recovery](#containment-eradication--recovery)
    - [Containment](#containment)
      - [Forensics in IR](#forensics-in-ir)
    - [Eradication and Recovery](#eradication-and-recovery)
    - [Checklist](#checklist-1)
  - [Post Incident Activities](#post-incident-activities)
    - [Lessons Learned](#lessons-learned)
      - [Other Activities](#other-activities)

<!-- END doctoc generated TOC please keep comment here to allow auto update -->

# Incident Response Overview

## What is Incident Response?

“Preventive activities based on the results of risk assessments can lower the number of incidents, but not all incidents can be prevented. An incident response is therefore necessary for rapidly detecting incidents, minimizing loss and destruction, mitigating the weaknesses that were exploited, and restoring IT services.”

### **Events**

“An event can be something as benign and unremarkable as typing on a keyboard or receiving an email.”

In some cases, if there is an Intrusion Detection System(IDS), the alert can be considered an event until validated as a threat.

### **Incident**

“An incident is an event that negatively affects IT systems and impacts on the business. It’s an unplanned interruption or reduction in quality of an IT service.”

An event can lead to an incident, but not the other way around.

#### Why Incident Response is Important

One of the benefit of having an incident response is that it supports responding to incidents systematically so that the appropriate actions are taken, it helps personnel to minimize loss or theft of information and disruption of services caused by incidents, and to use information gained during incident handling to better prepare for handling future incidents.

### IR Team Models

- Central teams
- Distributed teams
- Coordinating teams

#### Coordinating Teams

Incident don’t occur in a vacuum and can have an impact on multiple parts of a business. Establish relationships with the following teams:
![](images/Pasted%20image%2020230322113450.png)

### Common Attack Vectors

Organization should be generally prepared to handle any incident, but should focus on being prepared to handle incident that use common attack vectors:
1) External/Removable Media
2) Attrition
3) Web
4) Email
5) Impersonation
6) Loss or theft of equipment

### Baseline Questions

**Knowing the answers to these will help your coordination with other teams and the media**.

- Who attacked you? Why?
- When did it happen? How did it happen?
- Did this happen because you have poor security processes?
- How widespread is the incident?
- What steps are you taking to determine what happened and to prevent future occurrences?
- What is the impact of the incident?
- Was any PII exposed?
- What is the estimated cost of this incident?

#### Incident Response Phases

![](images/Pasted%20image%2020230322114821.png)

# Incident Response Process

## Incident Response Preparation

### Incident Response Policy

IR Policy needs to cover the following:
**IR Team**
- The composition of the incident response team within the organization.
**Roles**
- The role of each of the team members.
**Means, Tools, Resources**
- The technological means, tools, and resources that will be used to identify and recover compromised data.
**Policy Testing**
- The persons responsible for testing the policy.
**Action Plan**
- How to put the policy into the action?

#### Resources

**Incident Handler Communications and Facilities:**
- Contact information
- On-call information
- Incident reporting mechanisms
- Issue tracking system
- Smartphones
- Encryption software
- War room
- Secure storage facility

**Incident Analysis Hardware and Software:**
- Digital forensic workstations and/or backup devices
- Laptops
- Spare workstations, servers, and networking equipment
- Blank removable media
- Portable printer
- Packet sniffers and protocol analyzers
- Digital forensic software
- Removable media
- Evidence gathering accessories

**Incident Analysis Resources:**
- Port lists
- Documentation
- Network diagrams and lists of critical assets
- Current baselines
- Cryptographic hashes

#### The Best Defense

“Keeping the number of incidents reasonably low is very important to protect the business processes of the organization. It security controls are insufficient, higher volumes of incidents may occur, overwhelming the incident response team.”

So the best defense is:
- Periodic Risk Assessment
- Hardened Host Security
- Whitelist based Network Security
- Malware prevention systems
- User awareness and training programs

### Checklist

- [ ] Are all members aware of the security policies of the organization?
- [ ] Do all members of the Computer Incident Response Team know whom to contact?
- [ ] Do all incident responders have access to journals and access to incident response toolkits to perform the actual incident response process?
- [ ] Have all members participated in incident response drills to practice the incident response process and to improve overall proficiency on a regularly established basis?

## Incident Response Detection and Analysis

### Precursors and Indicators

**Precursors**
- A precursor is a sign that an incident may occur in the future.
	- Web server log entries that show the usage of a vulnerability scanner.
	- An announcement of a new exploit that targets a vulnerability of the organization’s mail server.
	- A threat from a group stating that the group will attack the organization.

**Indicators**
- An indicator is a sing that an incident may have occurred or may be occurring now.
	- Antivirus software alerts when it detects that a host is infected with malware.
	- A system admin sees a filename with unusual characters.
	- A host records an auditing configuration change in its log.
	- An application logs multiple failed login attempts from an unfamiliar remote system.
	- An email admin sees many bounced emails with suspicious content.
	- A network admin notices an unusual deviation from typical network traffic flows.

#### Monitoring Systems

- Monitoring systems are crucial for early detection of threats.
- These systems are not mutually exclusive and still require an IR team to document and analyze the data.

**IDS vs IPS**
Both are parts of the network infrastructure. The main difference between them is that IDS is a monitoring system, while IPS is a control system.

**DLP**
Data Loss Prevention (DLP) is a set of tools and processes used to ensure that sensitive data is not lost, misused, or accessed by unauthorized users.

**SIEM**
Security Information and Event Management solutions combine Security Event Management (SEM) – which carries out analysis of event and log data in real-time, with Security Information Management (SIM).

#### Documentation

Regardless of the monitoring system, highly detailed, thorough documentation is needed for the current and future incidents.

- The current status of the incident
- A summary of the incident
- Indicators related to the incident
- Other incident related to this incident
- Actions taken by all incident handlers on this incident.
- Chain of custody, if applicable
- Impact assessments related to the incident
- Contact information for other involved parties
- A list of evidence gathered during the incident investigation
- Comments from incident handlers
- Next steps to be taken (e.g., rebuild the host, upgrade an application)

#### Functional Impact Categories

![](images/Pasted%20image%2020230322144953.png)

#### Information Impact Categories

![](images/Pasted%20image%2020230322145054.png)

#### Recoverability Effort Categories

![](images/Pasted%20image%2020230322145144.png)

#### Notifications

- CIO
- Local and Head of information security
- Other incident response teams within the organization
- External incident response teams (if appropriate)
- System owner
- Human resources
- Public affairs
- Legal department
- Law enforcement (if appropriate)

## Containment, Eradication & Recovery

### Containment

“Containment is important before an incident overwhelms resources or increases damage. Containment strategies vary based on the type of incident. For example, the strategy for containing an email-borne malware infection is quite different from that of a network-based DDoS attack.”

An essential part of containment is decision-making. Such decisions are much easier to make if there are predetermined strategies and procedures for containing the incident.
1) Potential damage to and theft of resources
2) Need for an evidence preservation
3) Service availability
4) Time and resources needed to implement the strategy
5) Effectiveness of the strategy
6) Duration of the solution

#### Forensics in IR

“Evidence should be collected to procedures that meet all applicable laws and regulations that have been developed from previous discussions with legal staff and appropriate law enforcement agencies so that any evidence can be admissible in court.” — NIST 800-61
1) Capture a backup image of the system as-is
2) Gather evidence
3) Follow the Chain of custody protocols

### Eradication and Recovery

1) After an incident has been contained, eradication may be necessary to eliminate components of the incident, such as deleting malware and disabling breached user accounts, as well as identifying and mitigating all vulnerabilities that were exploited.
2) Recovery may involve such actions as restoring systems from clean backups, rebuilding systems from scratch, replacing compromised files with clean versions, installing patches, changing passwords, and tightening network perimeter security.
3) A high level of testing and monitoring are often deployed to ensure restored systems are no longer impacted by the incident. This could take weeks or months, depending on how long it takes to bring back compromised systems into production.

### Checklist

- [ ] Can the problem be isolated? Are all affected systems isolated from non-affected systems? Have forensic copies of affected systems been created for further analysis?
- [ ] If possible, can the system be reimaged and then hardened with patches and/or other countermeasures to prevent or reduce the risk of attacks? Have all malware and other artifacts left behind by the attackers been removed, and the affected systems hardened against further attacks?
- [ ] What tools are you going to use to test, monitor, and verify that the systems being restored to productions are not compromised by the same methods that cause the original incident?

## Post Incident Activities

Holding a “lessons learned” meeting with all involved parties after a major incident, and optionally periodically after lesser incidents as resources permit, can be extremely helpful in improving security measures and the incident handling process itself.

### Lessons Learned

- Exactly what happened, and at what times?
- How well did staff and management perform in dealing with the incident? Were the documented procedures followed? Were they adequate?
- What information was needed sooner?
- Were any steps or actions taken that might have inhibited the recovery?
- What would the staff and management do differently the next time a similar incident occurs?
- How could information sharing with other organizations have been improved?
- What corrective actions can prevent similar incidents in the future?
- What precursors or indicators should be watched in the future to detect the similar incidents?

#### Other Activities

- Utilizing data collected
- Evidence Retention
- Documentation
