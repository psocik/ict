---
title: "Eye" Spy Cyclops Blink Returns with Extended Capabilities
date: 2026-09-11
categories: [CYBERSECURITY]
tags: [MALWARE,CYBERSECURITY,LINUX,THREATS]
---

## "Eye" Spy: Cyclops Blink Returns with Extended Capabilities 🚀

In August 2026, Counter Threat Unit™ (CTU) researchers analyzed a malicious 64-bit Linux executable named **timezone_check** that was discovered on multiple compromised Cisco Firewall Management Center (FMC) devices. This sophisticated modular implant provides persistent remote access to a compromised Linux system. CTU™ analysis indicates that it is a variant of the **Cyclops Blink** malware previously analyzed by the UK National Cyber Security Centre (NCSC) in 2022 and is likely associated with the Russia-based **IRON VIKING** threat group (also known as Sandworm and Seashell Blizzard).

Unlike the WatchGuard-focused samples documented in 2022, the 2026 variant runs on x86-64 Linux and uses generic System V (SysV) persistence rather than vendor-specific firmware modification. This change broadens the range of potentially compatible network-edge appliances. The implant's expanded capabilities include:
- Active network and service discovery
- Programmable packet surveillance
- File transfer
- Payload execution

This allows a compromised device to serve as a platform for internal reconnaissance, intelligence collection, and follow-on operations.

### Modular Structure of Cyclops Blink

Cyclops Blink is a modular botnet and malware framework organized around a parent controller and five child-process worker modules. The controller masquerades as a process named **[kworker/0:1]** to blend into Linux process listings and reduce the likelihood of casual discovery. During initialization, the controller adds ACCEPT rules to the Linux iptables OUTPUT chain for TCP destination ports 43856 and 49172, which are the two ports used for its C2 communications.

The implant analyzed by CTU researchers contains five worker modules that perform:
- Host reconnaissance
- File transfer and payload execution
- Active network discovery
- Selective packet capture
- Persistence

### Detailed Insights from Module 0x08

Module 0x08 profiles the compromised Linux system and its immediate network environment, giving the operator detailed insight into the device's configuration, privileges, operational role, and connectivity. The module collects information such as:
- Operating system
- Kernel
- Hostname
- Uptime
- Processor
- Memory
- Filesystem
- Storage details
- Local users
- Groups
- Processes
- Command lines
- Network interfaces
- Addresses
- ARP data
- Resolver configuration

If the implant instance has sufficient privileges, the module may also access **/etc/shadow**, potentially exposing password hashes for offline analysis.

### File Transfer Capabilities of Module 0x0F

Module 0x0F provides the implant's principal mechanism for transferring files and deploying additional capabilities. The module can:
- Upload local files to C2 infrastructure
- Download content over HTTP or HTTPS
- Save retrieved payloads to an operator-specified path
- Execute downloaded files as child processes

The module can also write downloaded code directly into executable memory, allowing a payload to run without being stored as a conventional file. Retrieved Linux ELF executables can be registered as additional Cyclops Blink modules, extending the implant's functionality while it remains active.

### Internal Network Discovery with Module 0x11

Additionally, Module 0x11 provides internal network and service-discovery capabilities. It enumerates locally connected IPv4 networks and probes either an operator-defined port range or an embedded list of ports associated with commonly targeted infrastructure and management services. This capability is particularly significant when the implant is deployed on a network-edge device.

For more details, you can read the full article [here](https://www.sophos.com/en-us/blog/-eye-spy-cyclops-blink-returns-with-extended-capabilities).