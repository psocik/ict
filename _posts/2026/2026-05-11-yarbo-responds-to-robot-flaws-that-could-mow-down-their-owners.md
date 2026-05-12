---
title: Yarbo Responds to Robot Flaws That Could Mow Down Their Owners
date: 2026-05-11
categories: [TECHNOLOGY]
tags: [YARBO,ROBOTICS,SECURITY,VULNERABILITIES]
---

## Yarbo Responds to Robot Flaws That Could Mow Down Their Owners 🚜

A researcher found that Yarbo yard robots came with a host of vulnerabilities which, among others, allowed an attacker to harvest WiFi passwords. Security researcher **Andreas Makris** found he could remotely hijack thousands of Yarbo yard robots worldwide, and proved it by having his mower run him over. The root cause was a cluster of "legacy" design choices: every robot shared the same hardcoded root password, remote tunnels were left open, and Message Queuing Telemetry Transport (MQTT) messaging was so weakly protected that once you had one device, you effectively had the worldwide fleet. An attacker could pull GPS coordinates, email addresses, and Wi-Fi passwords, turn cameras into remote spying tools, and even re-arm the mower after someone hit the emergency stop. All of this was enabled by a persistent backdoor tunnel that users could neither see nor meaningfully control.

### The Risks 🚨

The risks fell into three very different buckets: A heavy mower with remotely controllable blades and an emergency stop that can be bypassed is a real-world safety hazard. Exposed telemetry meant attackers could map where devices were, see who owned them, and in some reports even view camera feeds. Network abuse through shared root credentials meant compromised robots could scan local networks, steal more data, or be folded into a botnet.

### Yarbo's Response 🔒

Yarbo's public response is unusually detailed for a consumer Internet of Things (IoT) vendor. It's also refreshingly blunt in admitting that the researcher's core findings were accurate. The company temporarily disabled the remote diagnostic tunnels, reset root passwords, locked down unauthenticated endpoints, and began ripping out unnecessary legacy access paths. More importantly, Yarbo promises structural changes: Unique per-device credentials, Over-the-Air (OTA) credential rotation, Audited, allowlist-based remote diagnostics, and a Dedicated security contact, with a possible bug bounty to follow. But Yarbo has explicitly chosen to keep a remote access tunnel, although wrapped in better controls and logs, instead of offering users the option to remove or fully opt out of it.

### Conclusion 📝

The vulnerabilities uncovered in the Yarbo case present an almost live-action demo of what the IoT Cybersecurity Improvement Act is trying to prevent in US government deployments. While the Act doesn't apply to Yarbo directly, its National Institute of Standards and Technology (NIST)-driven requirements map neatly onto what went wrong here. It's still up to users to make sure they: Change the default credentials, check if the vendor will make updates available and how easy it is to install them before buying an IoT product, and then install the updates when available. Additionally, users should put their IoT devices on a separate network, use a guest Wi-Fi or separate VLAN when available, and disable what they don't need, such as UPnP, remote access, cloud control, and unnecessary services. Finally, if a router or security suite logs connections from IoT devices, users should skim those logs for odd spikes or unknown destinations.

[Read full article](https://www.malwarebytes.com/blog/news/2026/05/yarbo-responds-to-robot-flaws-that-could-mow-down-their-owners)