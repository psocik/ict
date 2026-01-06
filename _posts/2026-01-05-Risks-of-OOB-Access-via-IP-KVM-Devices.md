---
title: Risks of OOB Access via IP KVM Devices
date: 2026-01-05
categories: [SECURITY]
tags: [IP KVM,SECURITY VULNERABILITIES,FIRMWARE,CONSUMER DEVICES]
---

Recently, a new "breed" of IP-based KVM devices has been released. In the past, IP-based KVM devices required dedicated "server-grade" hardware using IPMI. They often cost several $100 per server and are only available for specific systems that support the respective add-on cards. These cards are usually used to provide "Lights Out" access to servers, allowing a complete reboot and interaction with the pre-boot environment via simple web-based tools. 

The first "non-datacenter grade" device that provided similar capabilities to arbitrary systems was the "PIKVM," with hardware costs around $100-$200. More recently, a Chinese company, Sipeed, started offering a "NanoKVM" for as low as $30 for a bare bones version ($60 for a more full-featured assembled version). The NanoKVM uses a very minimal RISC CPU and runs a stripped-down Linux variant providing just enough features to act as a serviceable KVM. Consumer-oriented device manufacturers like GL-INET and others have released similar devices competing directly with the NanoKVM, often offering some additional capabilities.

However, turning these devices into a ubiquitous commodity has not come without problems. Some have accused Sipeed of installing deliberate backdoors in their devices and delaying addressing security vulnerabilities. Ultimately, you should never deploy a device from a vendor you do not trust. A device like an IP KVM will always have direct access to your system and will be able to intercept keystrokes and video output. Many of the alleged vulnerabilities, like insecure firmware updates, are sadly very common in consumer devices. The NanoKVM will download firmware updates from Sipeed's servers in China and will report some system status with these requests. 

Here are some tips to consider when installing one of these devices: Just like any administrative interface, do not expose the KVM to the internet. Luckily, these KVMs often support Tailscale out of the box or can support it with simple additional installs. Tailscale provides a simple VPN and NAT bypass solution to access systems even if your IP is dynamic. PiKVM at least offers MFA via one-time passwords; NanoKVM considers MFA a "TODO Item." Even running over a VPN, you should still use TLS to connect to your KVM to avoid MitM issues. This requires a valid certificate, either issued by an internal or public CA. If you are unable to automatically renew certificates, use an internal CA, which can issue certificates with a longer lifetime. Avoid self-signed certificates that are not recognized as valid by your browser. One thing often missing is a decent logging or alerting solution to track use of the OOB access. At least log to a central syslog server. 

Once you are using a KVM to access your system, it is important to implement authentication on the system connected to the KVM. You should have the standard login and auto-logout/screen lock features enabled, just as you would on a system sitting in an office. It is important to verify that the system is working and configure alerts in case they are not. Some simple monitoring scripts should check that the system is operating correctly.  

To read the complete article see: [Complete Article](https://isc.sans.edu/forums/diary/Risks%20of%20OOB%20Access%20via%20IP%20KVM%20Devices/32598/) 
