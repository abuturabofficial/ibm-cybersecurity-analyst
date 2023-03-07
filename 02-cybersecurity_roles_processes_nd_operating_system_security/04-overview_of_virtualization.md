<!-- START doctoc generated TOC please keep comment here to allow auto update -->
<!-- DON'T EDIT THIS SECTION, INSTEAD RE-RUN doctoc TO UPDATE -->
**Table of Contents**

- [Virtualization Basics and Cloud Computing](#virtualization-basics-and-cloud-computing)
  - [An Overview of Virtualization](#an-overview-of-virtualization)
    - [Hypervisor](#hypervisor)
    - [Virtual Machine](#virtual-machine)
  - [Virtualization to Cloud](#virtualization-to-cloud)
    - [Cloud Deployments](#cloud-deployments)
    - [Cloud Computing Reference Model](#cloud-computing-reference-model)

<!-- END doctoc generated TOC please keep comment here to allow auto update -->

# Virtualization Basics and Cloud Computing

## An Overview of Virtualization

- Allows you to create multiple simulated environments or dedicated resources from a single, physical hardware system.
- Hypervisor/Host
- Virtual Machine/Guest

### Hypervisor

- Separate the physical resources from the virtual environments
- Hypervisors can sit on top of an OS (end user) or be installed directly onto hardware (enterprise).

### Virtual Machine

- The virtual machine functions as a single data file.
- The hypervisor relays requests from the VM to the actual hardware, is necessary.
- VMs doesn’t interact directly with the host machine.
- Physical hardware is assigned to VMs.

## Virtualization to Cloud

![](images/Pasted%20image%2020230307164421.png)

### Cloud Deployments

![](images/Pasted%20image%2020230307164531.png)

### Cloud Computing Reference Model

![](images/Pasted%20image%2020230307165152.png)
