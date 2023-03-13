<!-- START doctoc generated TOC please keep comment here to allow auto update -->
<!-- DON'T EDIT THIS SECTION, INSTEAD RE-RUN doctoc TO UPDATE -->
**Table of Contents**

- [Introduction to the TCP/IP Protocol Framework](#introduction-to-the-tcpip-protocol-framework)
  - [Stateless Inspection](#stateless-inspection)
    - [Stateless Inspection Use Cases](#stateless-inspection-use-cases)
  - [Stateful Inspection](#stateful-inspection)
    - [What if we have both types of inspection?](#what-if-we-have-both-types-of-inspection)
  - [Firewall Filters – IDS and IPS System](#firewall-filters--ids-and-ips-system)
    - [Firewall Filter (ACLs) / Security Policies Demo…](#firewall-filter-acls--security-policies-demo)
    - [IDS](#ids)
    - [Basics of an Intrusion Prevention System (IPS)](#basics-of-an-intrusion-prevention-system-ips)
    - [How does it detect a threat?](#how-does-it-detect-a-threat)
  - [The Difference between IDS and IPS Systems](#the-difference-between-ids-and-ips-systems)
  - [Network Address Translation (NAT)](#network-address-translation-nat)
    - [Types of NAT](#types-of-nat)
- [Network Protocols over Ethernet and Local Area Networks](#network-protocols-over-ethernet-and-local-area-networks)
  - [An Introduction to Local Area Networks](#an-introduction-to-local-area-networks)
    - [Network Addressing](#network-addressing)
    - [Introduction to Ethernet Networks](#introduction-to-ethernet-networks)
  - [Ethernet and LAN – Ethernet Operations](#ethernet-and-lan--ethernet-operations)
    - [How do devices know when the data if for them?](#how-do-devices-know-when-the-data-if-for-them)
      - [MAC Address](#mac-address)
    - [Preamble and delimiter (SFD)](#preamble-and-delimiter-sfd)
    - [What if I need to send data to multiple devices?](#what-if-i-need-to-send-data-to-multiple-devices)
  - [Ethernet and LAN – Network Devices](#ethernet-and-lan--network-devices)
    - [Twisted Pair Cabling](#twisted-pair-cabling)
    - [Repeater](#repeater)
    - [Bridge](#bridge)
    - [Difference between a Bridge and a Switch](#difference-between-a-bridge-and-a-switch)
    - [Limitations of Switches:](#limitations-of-switches)
- [Basics of Routing and Switching, Network Packets and Structures](#basics-of-routing-and-switching-network-packets-and-structures)
  - [Layer 2 and Layer 3 Network Addressing](#layer-2-and-layer-3-network-addressing)
  - [Address Resolution Protocol (ARP)](#address-resolution-protocol-arp)
  - [Routers and Routing Tables](#routers-and-routing-tables)
    - [Routing Action](#routing-action)

<!-- END doctoc generated TOC please keep comment here to allow auto update -->

# Introduction to the TCP/IP Protocol Framework

## Stateless Inspection

- Stateless means that each packet is inspected one at a time with no knowledge of the previous packets.

![](images/Pasted%20image%2020230313092022.png)

![](images/Pasted%20image%2020230313092216.png)

### Stateless Inspection Use Cases

- To protect routing engine resources.
- To control traffic going in or your organization.
- For troubleshooting purposes.
- To control traffic routing (through the use of routing instances).
- To perform QoS/CoS (marking the traffic).

## Stateful Inspection

- A stateful inspection means that each packet is inspected with knowledge of all the packets that have been sent or received from the same session.
- A session consists of all the packets exchanged between parties during an exchange.

![](images/Pasted%20image%2020230313092703.png)

### What if we have both types of inspection?

![](images/Pasted%20image%2020230313092831.png)

## Firewall Filters – IDS and IPS System

### Firewall Filter (ACLs) / Security Policies Demo…

![](images/Pasted%20image%2020230313093141.png)

### IDS

An Intrusion Detection System (IDS) is a network security technology originally built for detecting vulnerability exploits against a target application or computer.
- By default, the IDS is a listen-only device.
- The IDS monitor traffic and reports its results to an administrator.
- Cannot automatically take action to prevent a detected exploit from taking over the system.

### Basics of an Intrusion Prevention System (IPS)

An IPS is a network security/threat prevention technology that examines network traffic flows to detect and prevent vulnerability exploits.
- The IPS often sites directly behind the firewall, and it provides a complementary layer of analysis that negatively selects for dangerous content.
- Unlike the IDS – which is a passive system that scans traffic and reports back on threats – the IPS is placed inline (in the direct communication path between source and destination), actively analyzing and taking automated actions on all traffic flows that enter the network.

### How does it detect a threat?

![](images/Pasted%20image%2020230313093817.png)

## The Difference between IDS and IPS Systems

![](images/Pasted%20image%2020230313094058.png)

## Network Address Translation (NAT)

Method of remapping one IP address space into another by modifying network address information in Internet Protocol (IP) datagram packet headers, while they are in transit across a traffic routing device.
- Gives you an additional layer of security.
- Allows the IP network of an organization to appear from the outside to use a different IP address space than what it is actually using. Thus, NAT allows an organization with non-globally routable addresses to connect to the Internet by translating those addresses into a globally routable addresses space.
- It has become a popular and essential tool in conserving global address space allocations in face of IPv4 address exhaustion by sharing one Internet-routable IP address of a NAT gateway for an entire private network.

![](images/Pasted%20image%2020230313094257.png)

### Types of NAT

1) **Static Address translation (static NAT)**: Allows one-to-one mapping between local and global addresses.
2) **Dynamic Address Translation (dynamic NAT)**: Maps unregistered IP addresses to registered IP addresses from a pool of registered IP addresses.
3) **Overloading**: Maps multiple unregistered IP addresses to a single registered IP address (many to one) using different ports. This method is also known as **Port Address Translation (PAT)**. By using overloading, thousands of users can be connected to the Internet by using only one real global IP address.

# Network Protocols over Ethernet and Local Area Networks

## An Introduction to Local Area Networks

### Network Addressing

- Layer 3 or network layer adds an address to the data as it flows down the stack; then layer 2 or the data link layer adds another address to the data.

![](images/Pasted%20image%2020230313100032.png)

### Introduction to Ethernet Networks

For a LAN to function, we need:
- Connectivity between devices
- A set of rules controlling the communication

**The most common set of rules is called Ethernet.**

- To send a packet from one host to another host within the same network, we need to know the **MAC address**, as well as the **IP address** of the destination device.

## Ethernet and LAN – Ethernet Operations

### How do devices know when the data if for them?

![](images/Pasted%20image%2020230313102544.png)

**Destination Layer 2 address:** MAC address of the device that will receive the frame.

**Source Layer 2 address:** MAC address of the device sending the frame.

**Types**: Indicates the layer 3 protocol that is being transported on the frame such as IPv4, IPv6, Apple Tall, etc.

**Data:** Contains original data as well as the headers added during the encapsulation process.

**Checksum:** This contains a Cyclic Redundancy Check to check if there are errors on the data.

#### MAC Address

A MAC address is a 48-bits address that uniquely identifies a device’s NIC. The first 3 bytes are for the OUI and the last 3 bytes are reserved to identify each NIC.

![](images/Pasted%20image%2020230313103438.png)

### Preamble and delimiter (SFD)

Preamble and delimiter (SFD) are 7 byte fields in an Ethernet frame. **Preamble** informs the receiving system that a frame is starting and enables synchronization, while **SFD** (Start Frame Delimiter) signifies that the Destination MAC address field begin with the next byte.


![](images/Pasted%20image%2020230313103432.png)

### What if I need to send data to multiple devices?

![](images/Pasted%20image%2020230313103552.png)

## Ethernet and LAN – Network Devices

### Twisted Pair Cabling

![](images/Pasted%20image%2020230313104246.png)

### Repeater

- Regenerates electrical signals.
- Connects 2 or more separate physical cables.
- Physical layer device.
- Repeater has no mechanism to check for collision.

![](images/Pasted%20image%2020230313104855.png)

![](images/Pasted%20image%2020230313105054.png)

### Bridge

Ethernet bridges have 3 main functions:
- Forwarding frames
- Learning MAC addresses
- Controlling traffic

![](images/Pasted%20image%2020230313105305.png)

![](images/Pasted%20image%2020230313105400.png)

### Difference between a Bridge and a Switch

![](images/Pasted%20image%2020230313105446.png)

- VLANs provide a way to separate LANs on the same switch.
- Devices in one VLAN don’t receive broadcast from devices that are on another VLAN.

![](images/Pasted%20image%2020230313105648.png)

### Limitations of Switches:

- Network loops are still a problem.
- Might not improve performance with multicast and broadcast traffic.
- Can’t connect geographically dispersed networks.

# Basics of Routing and Switching, Network Packets and Structures

## Layer 2 and Layer 3 Network Addressing

![](images/Pasted%20image%2020230313110911.png)

![](images/Pasted%20image%2020230313110917.png)

## Address Resolution Protocol (ARP)

The process of using layer 3 addresses to determine layer 2 addresses is called ARP or Address Resolution Protocol.

## Routers and Routing Tables

### Routing Action

![](images/Pasted%20image%2020230313113412.png)
