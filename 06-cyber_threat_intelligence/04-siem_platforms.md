
# SIEM Concepts

## SIEM Concepts, Benefits, Optimization, & Capabilities

“At its core, System Information Event Management (SIEM) is a data aggregator, search and reporting system. SIEM gathers immense amounts of data from your entire networked environment, consolidates and makes that data human accessible. With the data categorized and laid out at your fingertips, you can research data security breaches with as much detail as needed.”

**Key Terms:**
- Log collection
- Normalization
- Correlation
- Aggregation
- Reporting

### SIEM

1) A SIEM system collects logs and other security-related documentation for analysis.
2) The core function to manage network security by monitoring flows and events.
3) It consolidates log events and network flow data from thousands of devices, endpoints, and applications distributed throughout a network. It then uses an advanced Sense Analytics engine to normalize and correlate this data and identifies security offenses requiring investigation.
4) A SIEM system can be rules-based or employ a statistical correlation between event log entries.
5) Capture log event and network flow data in near real time and apply advanced analytics to reveal security offenses.
6) It can be available on premises and in a cloud environment.


### Events & Flows

| Events                                                                                                                                       | Flows                                                                                                                                                                                                                |
| -------------------------------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Typically is a log of a specific action such as a user login, or a FW permit, occurs at a specific time and the event is logged at that time | A flow is a record of network activity between two hosts that can last for seconds to days depending on the activity within the session.                                                                             |
|                                                                                                                                              | For example, a web request might download multiple files such as images, ads, video, and last for 5 to 10 seconds, or a user who watches a NetFlix movie might be in a network session that lasts up to a few hours. | 

### Data Collection

- It is the process of collecting flows and logs from different sources into a common repository.
- It can be performed by sending data directly into the SIEM or an external device can collect log data from the source and move it into the SIEM system on demand or scheduled.

To consider:
- Capture
- Memory
- Storage capacity
- License
- Number of sources

### Normalization

- The normalization process involves turning raw data into a format that has fields such as IP address that SIEM can use.
- Normalization involves parsing raw event data and preparing the data to display readable information.
- Normalization allows for predictable and consistent storage for all records, and indexes these records for fast searching and sorting.

### License Throttling

- Monitors the number of incoming events to the system to manage input queues and EPS licensing.

### Coalescing

- Events are parsed and then coalesced based on common attributes across events. In QRadar, Event coalescing starts after three events have been found with matching properties within a 10-second period.
- Event data received by QRadar is processed into normalized fields, along with the original payload. When coalescing is enabled, the following five properties are evaluated.
	- QID
	- Source IP
	- Destination IP
	- Destination port
	- Username

![](images/Pasted%20image%2020230430090152.png)

## SIEM Deployment

### SIEM Deployment Considerations

- Compliance
- Cost-benefit
- Cybersecurity

**QRadar Deployment Examples**

![](images/Pasted%20image%2020230430091044.png)

### Events

**Event Collector:**
- The event collector collects events from local and remote log sources, and normalize raw log source events to format them for use by QRadar. The Event Collector bundles or coalesces identical events to conserve system usage and send the data to the Event Processor.
- The Event Collector can use bandwidth limiters and schedules to send events to the Event Processor to overcome WAN limitations such as intermittent connectivity.

**Event Processor:**
- The Event Processor processes events that are collected from one or more Event Collector components.
- Processes events by using the Custom Rules Engine (CRE).

### Flows

**Flow Collector:**
- The flow collector generates flow data from raw packets that are collected from monitor ports such as SPANS, TAPS, and monitor sessions, or from external flow sources such as netflow, sflow, jflow.
- This data is then converted to QRadar flow format and sent down the pipeline for processing.

**Flow Processor:**
- Flow deduplication: is a process that removes duplicate flows when multiple Flow Collectors provide data to Flow Processors appliances.
- Asymmetric recombination: Responsible for combining two sides of each flow when data is provided asymmetrically. This process can recognize flows from each side and combine them in to one record. However, sometimes only one side of the flow exists.
- License throttling: Monitors the number of incoming flows to the system to manage input queues and licensing.
- Forwarding: Applies routing rules for the system, such as sending flow data to offsite targets, external Syslog systems, JSON systems, other SIEMs.

#### Reasons to add event or flow collectors to an All-in-One deployment

- Your data collection requirements exceed the collection capability of your processor.
- You must collect events and flows at a different location than where your processor is installed.
- You are monitoring packet-based flow sources.
- As your deployment grows, the workload exceeds the processing capacity of the All-in-One appliance.
- Your security operations center employs more analytics who do more concurrent searches.
- The types of monitored data, and the retention period for that data, increases, which increases processing and storage requirements.
- As your security analyst team grows, you require better search performance.

### Security Operations Center (SOC)

**Triad of Security Operations: People, Process and Technology.**

![](images/Pasted%20image%2020230430100721.png)

### SOC Data Collection

![](images/Pasted%20image%2020230430101118.png)

## SIEM Solutions – Vendors

“The security information and event management (SIEM) market is defined by customers’ need to analyze security event data in real-time, which supports the early detection of attacks and breaches. SIEM systems collect, store, investigate, support mitigation and report on security data for incident response, forensics and regulatory compliance. The vendors included in this Magic Quadrant have products designed for this purpose, which they actively market and sell to the security buying center.”

#### Deployments

**Small:**
Gartner defines a small deployment as one with around 300 log sources and 1500 EPS.

**Medium:**
A midsize deployment is considered to have up to 1000 log sources and 7000 EPS.

**Large:**
A large deployment generally covers more than 1000 log sources with approximately 15000 EPS.

### Important Concepts

![](images/Pasted%20image%2020230430102001.png)

![](images/Pasted%20image%2020230430102102.png)

#### IBM QRadar

![](images/Pasted%20image%2020230430102227.png)

**IBM QRadar Components**

![](images/Pasted%20image%2020230430102339.png)

#### ArcSight ESM

![](images/Pasted%20image%2020230430102515.png)

#### Splunk

![](images/Pasted%20image%2020230430102551.png)

**Friendly Representation**

![](images/Pasted%20image%2020230430102648.png)

#### LogRythm’s Security Intelligence Platform

![](images/Pasted%20image%2020230430102737.png)

# User Behavior Analytics

### Security Ecosystem

- Detecting insider threats requires a 360 degree view of both logs and flows.

![](images/Pasted%20image%2020230430105415.png)

### Advantages of an integrated UBA Solution

- Complete visibility across end point, network and cloud infrastructure with both log and flow data.
- Avoids reloading and curating data faster time to insights, lowers opex, frees valuable resources.
- Out-of-the-box analytics models that leverage and extend the security operations platform.
- Single Security operation processes with integration of workflow system and other security solutions.
- Easily extend to third-party analytic models, including existing insider threats use cases already implemented.
- Leverage UBA insights in other integrated security analytics solutions.
- Get more from your QRadar ecosystem.
