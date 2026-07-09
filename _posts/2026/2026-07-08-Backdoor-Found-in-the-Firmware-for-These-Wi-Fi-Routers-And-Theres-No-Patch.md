---
title: Backdoor Found in the Firmware for These Wi-Fi Routers. And There's No Patch
date: 2026-07-08
categories: [CYBERSECURITY]
tags: [WI-FI,SECURITY,VULNERABILITY,ROUTER]
---

## Backdoor Found in the Firmware for These Wi-Fi Routers 🚨

An undocumented backdoor has been discovered in the firmware of certain Tenda Wi-Fi routers, allowing hackers an easy way to gain control over these devices. An unnamed security researcher identified this threat in five firmware versions, as reported by the CERT Coordination Center, a cybersecurity authority in the US.

Tenda's routers come with a web interface that enables owners to configure and manage their devices, even remotely. Typically, this interface requires a username and password for access. However, it turns out that authentication can be bypassed by supplying an alternate password, with no username needed.

This undocumented function checks for an "alternate password value from the device configuration." A successful match grants admin-level access and creates a valid session. The vulnerability report states, "This backdoor authentication mechanism is not documented or visible through any administrative interface." The alternate password appears to be "rzadmin," which has been noted in previous security research.

Another concerning issue is the lack of a patch. The CERT report mentions, "Unfortunately, we were unable to reach the vendor to coordinate this vulnerability." Tenda, based in China, has not responded to requests for comment, leaving the purpose of the backdoor unclear. Currently, the CERT vulnerability report indicates that this backdoor has been found in five firmware versions, which are in use on several older Tenda routers, some of which seem to have been discontinued. These include firmware for the following models:
- **FH1201 High Power AC1200 Dual Band Wireless Router**
- **W15E v2.0 AC1200 Wireless Hotspot Router**
- **AC10 v1.0 AC1200 Smart Dual-Band Gigabit Router**
- **AC5 v1.0 AC1200 Smart Dual-Band Router**
- **AC6 router v1.0 AC1200 Router**

To mitigate the problem, CERT advises affected owners to disable remote web management on their routers and change the default LAN IP address to prevent automated scanners from detecting the device. However, for less tech-savvy users, it might be easier to simply purchase a new router.

[Read full article](https://www.pcmag.com/news/backdoor-found-in-the-firmware-for-these-wi-fi-routers-and-theres-no-patch)