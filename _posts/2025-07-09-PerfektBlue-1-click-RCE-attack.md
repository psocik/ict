---
title: PerfektBlue 1-click RCE attack
date: 2025-07-09
categories: [SECURITY]
tags: [RCE,PERFEKTBLUE,BLUETOOTH,CYBER SECURITY]
---

**Affected Devices. Impact**

Turned out that OpenSynergy BlueSDK framework is widely used in the automotive industry in particular. BlueSDK is used in other domains as well (for example, in mobile phones and portable devices) but most of the potentially vulnerable devices are automotive-related.

Public resources containing Bluetooth certification information were used to identify vendors and products using BlueSDK framework. The following is a non-extensive list of affected vendors: Mercedes-Benz AG, Volkswagen, Skoda.

Having code execution on IVI device, it's possible for an attacker to track GPS coordinates, record audio inside a car, obtain personal phonebook information, and finally perform lateral movement to other ECUs - legitimately or by exploiting other software components - and obtain access to critical elements of a car.

To protect against PerfektBlue, you can update your system or disable the Bluetooth functionality entirely.

To read the complete article see:

[PerfektBlue Full Article](https://perfektblue.pcacybersecurity.com/) 

---