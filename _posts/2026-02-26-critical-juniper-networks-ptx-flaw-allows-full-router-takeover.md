---
title: Critical Juniper Networks PTX Flaw Allows Full Router Takeover
date: 2026-02-26
categories: [SECURITY]
tags: [JUNIPER,VULNERABILITY,ROUTER,SECURITY]
---

## Critical Juniper Networks PTX Flaw Allows Full Router Takeover 🚨

A critical vulnerability in the **Junos OS Evolved** network operating system running on **PTX Series routers** from Juniper Networks could allow an unauthenticated attacker to execute code remotely with root privileges. PTX Series routers are high-performance core and peering routers built for high throughput, low latency, and scale. They are commonly used by internet service providers, telecommunication services, and cloud network applications.

The security issue is identified as **CVE-2026-21902** and is caused by incorrect permission assignment in the ‘On-Box Anomaly Detection’ framework, which should be exposed to internal processes only over the internal routing interface. However, the glitch allows accessing the framework over an externally exposed port, as explained by Juniper Networks in a security advisory. Because the service runs as root and is enabled by default, successful exploitation would allow an attacker who is already on the network to take full control of the device without authentication.

### Affected Versions
The issue affects **Junos OS Evolved** versions before **25.4R1-S1-EVO** and **25.4R2-EVO**, on PTX Series routers. Juniper Networks has delivered fixes in versions **25.4R1-S1-EVO**, **25.4R2-EVO**, and **26.2R1-EVO** of the product.

### Recommendations
If immediate patching is not possible, the vendor's recommendation is to restrict access to the vulnerable endpoints to trusted networks only using firewall filters or Access Control Lists (ACLs). Alternatively, administrators may disable the vulnerable service entirely using: `request pfe anomalies disable`.

Juniper Networks products are typically an attractive target for advanced hackers as the network equipment is used by service providers requiring high bandwidth, such as cloud data centers and large enterprises. 

For more details, see the complete article: [Read full article](https://www.bleepingcomputer.com/news/security/critical-juniper-networks-ptx-flaw-allows-full-router-takeover/)