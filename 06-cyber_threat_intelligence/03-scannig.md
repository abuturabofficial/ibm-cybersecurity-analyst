
# Vulnerability Assessment Tools

## Tools

“Vulnerability scanning identifies hosts and host attributes (e.g., OSs, applications, open ports), but it also attempts to identify vulnerabilities rather than relying on human interpretation of the scanning results. Vulnerability scanning can help identify outdated software versions, missing patches, and misconfigurations, and validate compliance with or deviation from an organization’s security policy.”  **— NIST SP 800-115**

### What is a Vulnerability Scanner?

**Capabilities:**
- Keeping an up-to-date database of vulnerabilities.
- Detection of genuine vulnerabilities without an excessive number of false positives.
- Ability to conduct multiple scans at the same time.
- Ability to perform trend analyses and create clear reports of the results.
- Provide recommendations for effective countermeasures to eliminate discovered vulnerabilities.

#### Components of Vulnerability Scanners

There are 4 main components of most scanners:
1) **Engine Scanner**
Performs security checks according to its installed plug-ins, identifying system information, and vulnerabilities.
2) **Report Module**
Provides scan result reporting such as technical reports for system administrators, summary reports for security managers, and high-level graph and trend reports for corporate executives' leadership.
3) **Database**
Stores vulnerability information, scan results, and other data used by the scanner.
4) **User interface**
Allows the admin to operate the scanner. It may be either a GUI, or just a CLI.

#### Host & Network

**Internal Threats:**
- It can be through Malware or virus that is downloaded onto a network through internet or USB.
- It can be a disgruntled employee who has the internal network access.
- It can be through the outside attacker who has gained access to the internal network.
- The internal scan is done by running the vulnerability scanner on the critical components of the network from a machine which is a part of the network. This important component may include core router, switches, workstations, web server, database, etc.

**External Threats:**
- The external scan is critical as it is required to detect the vulnerabilities to those internet facing assets through which an attacker can gain internal access.

#### Common Vulnerability Scoring Systems (CVSS)

The CVSS is a way of assigning severity rankings to computer system vulnerabilities, ranging from zero (least severe) to 10 (most severe).
- It provides a standardized vulnerability score across the industry, helping critical information flow more effectively between sections within an organization and between organizations.
- The formula for determining the score is public and freely distributed, providing transparency.
- It helps prioritize risk — CVSS rankings provide both a general score and more specific metrics.

![](images/Pasted%20image%2020230428072136.png)

**Score Breakdown:**

The CVSS score has three values for ranking a vulnerability:
1) **A base score**, which gives an idea of how easy it is to exploit targeting that vulnerability could inflict.
2) **A temporal score**, which ranks how aware people are of the vulnerability, what remedial steps are being taken, and whether threat actors are targeting it.
3) **An environmental score**, which provides a more customized metric specific to an organization or work environment.

![](images/Pasted%20image%2020230428072530.png)

### STIGS – Security Technical Implementation Guides

- The Defense Information Systems Agency (DISA) is the entity responsible for maintaining the security posture of the DoD IT infrastructure.
- Default configurations for many applications are inadequate in terms of security, and therefore DISA felt that developing a security standard for these applications would allow various DoD agencies to utilize the same standard – or STIG – across all application instances that exist.
- STIGs exist for a variety of software packages including OSs, DBAs, OSS, Network devices, Wireless devices, Virtual software, and, as the list continues to grow, now even include Mobile Operating Systems.

### Center for Internet Security (CIS)

**Benchmarks:**
- CIS benchmarks are the only consensus-based, best-practice security configuration guides both developed and accepted by government, business, industry, and academia.
- The initial benchmark development process defines the scope of the benchmark and begins the discussion, creation, and testing process of working drafts. Using the CIS WorkBench community website, discussion threads are established to continue dialogue until a consensus has been reached on proposed recommendations and the working drafts. Once consensus has been reached in the CIS Benchmark community, the final benchmark is published and released online.

**Controls:**
The CIS Controls<sup>TM</sup> are a prioritized set of actions that collectively form a defense-in-depth set of best practices that mitigate the most common attacks against systems and networks. The CIS Controls are developed by a community of IT experts who apply their first-hand experience as cyber defenders to create these globally accepted security best practices.

The five critical tenets of an effective cyber defense systems as reflected in the CIS Controls are:
1) Offense informs defense
2) Prioritization
3) Measurements and metrics
4) Continuous diagnostics and mitigation
5) Automation

### Implementation Groups

![](images/Pasted%20image%2020230428073950.png)

#### 20 CIS Controls

![](images/Pasted%20image%2020230428074147.png)

# Port Scanning

“Network port and service identification involves using a port scanner to identify network ports and services operating on active hosts–such as FTP and HTTP–and the application that is running each identified service, such as Microsoft Internet Information Server (IIS) or Apache for the HTTP service. All basic scanners can identify active hosts and open ports, but some scanners are also able to provide additional information on the scanned hosts.” —**NIST SP 800-115**

### Ports

- Managed by IANA.

### Responses

- A port scanner is a simple computer program that checks all of those doors – which we will start calling ports – and responds with one of three possible responses:
1) Open — Accepted
2) Close — Not Listening
3) Filtered — Dropped, Blocked

### Types of Scans

Port scanning is a method of determining which ports on a network are open and could be receiving or sending data. It is also a process for sending packets to specific ports on a host and analyzing responses to identify vulnerabilities.

1)**Ping:**
Simplest port scan sending ICMP echo request to see who is responding
2) **TCP/Half Open:**
A popular, deceptive scan also known as SYN scan. It notes the connection and leaves the target hanging.
3) **TCP Connect:**
Takes a step further than half open by completing the TCP connection. This makes it slower and noisier than half open.
4) **UDP:**
When you run a UDP port scan, you send either an empty packet or a packet that has a different payload per port, and will only get a response if the port is closed. It's faster than TCP, but doesn’t contain as much data.
5) **Stealth:**
These TCP scans are quieter than the other options and can get past firewalls. They will still get picked by the most recent IDS.

#### Tools – NMAP

NMAP (Network Mapper) is an open source tool for network exploration and security auditing.
- Design to rapidly scan large networks, though work fine against single hosts.
- Uses raw IP packets.
- Used to know, service type, OS type and version, type of packet filter/firewall in use, and many other things.
- Also, useful for network inventory, managing service upgrade schedules, and monitoring host or service uptime.
- ZenMap is a GUI version of NMAP.

# Network Protocol Analyzers 

“A protocol analyzer (also known as a **sniffer, packet analyzer, network analyzer, or traffic analyzer**) can capture data in transit for the purpose of analysis and review. Sniffers allow an attacker to inject themselves in a conversation between a digital source and destination in hopes of capturing useful data.”

### Sniffers

Sniffers operate at the data link layer of the OSI model, which means they don’t have to play by the same rules as the applications and services that reside further up the stack. Sniffers can capture everything on the wire and record it for later review. They allow user’s to see all the data contained in the packet.

- Wireshark

![](images/Pasted%20image%2020230428082002.png)

#### WireShark

Wireshark intercepts traffics and converts that binary traffic into human-readable format. This makes it easy to identify what traffic is crossing your network, how much of it, how frequently, how much latency there is between certain hops, and so on.

- Network Admins use it to troubleshoot network problems.
- Network Security Engineers use it to examine security issues.
- QA engineers use it to verify network applications.
- Developers use it to debug protocol implementations.
- People use it to learn network protocol internals.

##### WireShark Features

- Deep inspection of hundred of protocols, with more being added all the time
- Live capture and offline analysis
- Standard three pane packet browser
- Cross-platform
- GUI or TTY-mode – TShark utility
- Powerful display filters
- Rich VoIP analysis
- Read/write to different formats
- Capture compressed file with gzip
- Live data from any source
- Decryption support for many protocols
- Coloring rules
- Output can be exported to different formats

#### Packet Capture (PCAP)

PCAP is a valuable resource for file analysis and to monitor network traffic.
- Monitoring bandwidth usage
- Identify rogue DHCP servers
- Detecting Malware
- DNS resolution
- Incident Response

Wireshark is the most popular traffic analyzer in the world. Wireshark uses `.pcap` files to record packet data that has been pulled from a network scan. Packet data is recorded in files with the `.pcap` file extension and can be used to find performance issues and cyberattacks on the network.

![](images/Pasted%20image%2020230428083510.png)

# Security Architecture considerations

## Characteristics of a Security Architecture

**The foundation of robust security is a clearly communicated structure with a systematic analysis of the threats and controls.**
- Build with a clearly communicated structure
- Use systematic analysis of threats and controls

**As IT systems increase in complexity, they require a standard set of techniques, tools, and communications.**

**Architectural thinking is about creating and communicating good structure and behavior with the intent of avoiding chaos.**

Architecture need to be:
- Described before it can be created
- With different level of elaboration for communication
- Include a solution for implementation and operations
- That is affordable
- And is secure

> Architecture: “The architecture of a system describes its overall static structure and dynamic behavior. It models the system’s elements (which for IT systems are software, hardware and its human users), the externally manifested properties of those elements, and the static and dynamic relationships among them.”

> ISO/IEC 422010:20071 defines Architecture as “the fundamental organization of a system, embodied in its components, their relationships to each other and the environment, and the principles governing its design and evolution.”

## High-level Architectural Models

**Enterprise and Solution Architecture break down the problem, providing different levels of abstraction.**

![](images/Pasted%20image%2020230428091238.png)

**High-level architectures are described through Architectural Building Blocks (ABBs) and Solution Building Blocks (SBBs).**

![](images/Pasted%20image%2020230428091419.png)

**Here are some example Security ABBs and SBBs providing different levels of abstraction aimed at a different audience.**

![](images/Pasted%20image%2020230428091550.png)

**Here is a high level example of an Enterprise Security Architecture for hybrid multicloud showing security domains.**
s
![](images/Pasted%20image%2020230428091706.png)

**The Enterprise Security Architecture domains could be decomposed to show security capabilities… without a context.**

![](images/Pasted%20image%2020230428091759.png)

**Adding context gives us a next level Enterprise Architecture for hybrid multi-cloud, but without specific implementation.**

![](images/Pasted%20image%2020230428091912.png)

## Solution Architecture

**Additional levels of abstraction are used to describe architectures down to the physical operational aspects.**

![](images/Pasted%20image%2020230428092148.png)

**Start with a solution architecture with an Architecture Overview giving an overview of the system being developed.**

![](images/Pasted%20image%2020230428092344.png)

**Continue by clearly defining the external context describing the boundary, actors and use that process data.**

![](images/Pasted%20image%2020230428092452.png)

**Examine the system internally looking at the functional components and examine the threats to the data flows.**

![](images/Pasted%20image%2020230428092600.png)

**Finally, look at where the function is hosted, the security zones and the specific protection required to protect data.**

![](images/Pasted%20image%2020230428092707.png)

**As the architecture is elaborated, define what is required and how it will be delivered?**

![](images/Pasted%20image%2020230428092829.png)

## Security Patterns

**The use of security architecture patterns accelerate the creation of a solution architecture.**

A security Architecture pattern is
- a reusable solution to a commonly occurring problem
- it is a description or template for how to solve a problem that can be used in many different situations
- is not a finished design as it needs conext
- it can be represented in many different formats
- Vendor specific or agnostic
- Available at all levels of abstraction

![](images/Pasted%20image%2020230428093530.png)

**There are many security architecture patterns available to provide a good starting point to accelerate development.**

# Application Security Techniques and Risks

## Application Security Overview

![](images/Pasted%20image%2020230428094644.png)

### Software Development Lifecycle

![](images/Pasted%20image%2020230428094806.png)

### Penetration Testing Tools

![](images/Pasted%20image%2020230428094855.png)

### Source Code Analysis Tools

![](images/Pasted%20image%2020230428094947.png)

## Application Security Threats and Attacks

### Third Party Software

- Standards
- Patching
- Testing

**Supplier Risk Assessment**

- Identify how any risks would impact your organization's business. It could be a financial, operational or strategic risk.
- Next step would be to determine the likelihood the risk would interrupt the business 
- And finally there is a need to identify how the risk would impact the business.

### Web Application Firewall (WAF)

![](images/Pasted%20image%2020230428100602.png)

### Application Threats/Attacks

**Input Validation:**
- Buffer overflow
- Cross-site scripting
- SQL injection
- Canonicalization

**Authentication:**
- Network eavesdropping
- Brute force attack
- Dictionary attacks
- Cookie replay
- Credential theft

**Authorization:**
- Elevation of privilege
- Disclosure of confidential data
- Data tampering
- Luring Attacks

**Configuration Management:**
- Unauthorized access to admin interface
- Unauthorized access to configuration stores
- Retrieval of clear text configuration data
- Lack of individual accountability; over-privileged process and service accounts

**Exception Management:**
- Information disclosure
- DoS

**Auditing and logging:**
- User denies performing an operation
- Attacker exploits an application without trace
- Attacker covers his tracks

