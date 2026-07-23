---
title: Opening the Black Box Agentless Threat Detection for Virtual Appliances
date: 2026-07-22
categories: [CYBERSECURITY]
tags: [THREAT DETECTION,VIRTUAL APPLIANCES,CYBERSECURITY,FORTIGATE]
---

## Opening the Black Box: Agentless Threat Detection for Virtual Appliances

Virtual appliances are common in the cloud, with **51.9%** of cloud environments having at least one virtual appliance. 🚀 **46.4%** of those have exposed at least one virtual appliance to the Internet. These appliances often act as key network and security components, such as firewalls, gateways, WAFs, proxies, and SSL VPNs. However, they typically operate as "black boxes" and do not support traditional security tooling such as EDR or antivirus agents, creating a significant visibility gap for security teams. The combination of exposure and privilege makes them high-value targets for attackers. 🔒

FortiGate, Fortinet's series of next-generation firewalls (NGFW), is widely deployed, with at least one instance found as a virtual appliance in **12%** of cloud environments. Virtual appliances are systematically targeted by adversaries due to the high-value access they provide. The **2026 FortiBleed** campaign compromised credentials for approximately **75,000** FortiGate devices across **194** countries, roughly half of all internet-facing FortiGate firewalls. Additionally, FortiGate devices have been targeted by several campaigns involving vulnerability exploitation. 

To detect such activities, security teams should hunt for successful login events immediately following a burst of failed attempts from the same source. Authentication originating from high-risk infrastructure, such as VPS providers (e.g., DigitalOcean, Linode, Vultr), commercial VPNs, or IPs marked as malicious, is also a key indicator. Furthermore, "impossible travel" scenarios, where successive logins occur from geographically distant locations, should be monitored. Logins occurring outside of standard business hours or established patterns also warrant investigation. 

For more details, check out the full article: [Read full article](https://www.wiz.io/blog/agentless-threat-hunting-fortigate)