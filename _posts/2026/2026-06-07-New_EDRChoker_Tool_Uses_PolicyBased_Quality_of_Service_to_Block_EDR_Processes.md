---
title: New EDRChoker Tool Uses Policy-Based Quality of Service to Block EDR Processes
date: 2026-06-07
categories: [CYBERSECURITY]
tags: [EDR,TOOL,CYBERSECURITY,QUALITY-OF-SERVICE]
---

## New EDRChoker Tool 🚀

A newly released open-source red team tool called **EDRChoker** introduces a novel technique for silencing cloud-connected Endpoint Detection and Response (EDR) agents. Instead of killing their processes or injecting code, it quietly chokes their network bandwidth to near-zero using Windows' native Policy-Based Quality of Service (QoS) engine.

Developed by security researcher @TwoSevenOneT, the tool exploits Windows Policy-Based Quality of Service (QoS) to throttle EDR processes to near-zero bandwidth, effectively isolating them from their command infrastructure. Modern EDR platforms rely on a persistent, low-latency connection between the endpoint agent and a cloud-based management server. Severing that connection causes the EDR agent to go dark, unable to report detections, receive updated policies, or accept remote commands from administrators. This architectural dependency is precisely what EDRChoker exploits.

### Historical Context 📜
Red teams have historically used two primary methods to interrupt EDR communications: Windows Defender Firewall rules and Windows Filtering Platform (WFP) API calls. Tools like EDRSilencer weaponize the FwpmFilterAdd0 API to register outbound network filters that selectively drop EDR agent packets. However, the critical limitation is that forensic visibility from WFP-based blocking generates packet-block and packet-drop events that security platforms like Elastic Defend actively detect, raising immediate alerts.

In contrast, EDRChoker utilizes policies such as `New-NetQosPolicy -Name "EDRProcess_<GUID>" -AppPathNameMatchCondition "agent.exe" -ThrottleRateActionBitsPerSecond 8 -PolicyStore ActiveStore`. At 8 bps, a standard TLS handshake becomes impossible to complete, causing the EDR agent to continuously time out before exchanging a single packet.

### Technical Advantages ⚙️
The technical advantage of EDRChoker is architectural. QoS throttling is enforced by pacer.sys, an NDIS Lightweight Filter Driver that operates directly above the physical NIC. Because it operates at a lower privilege tier in the stack, pacer.sys rules govern packets that WFP-level EDR monitoring tools never reach.

Researcher @TwoSevenOneT stated that EDRChoker accepts an input file of EDR process names and auto-generates uniquely named QoS policies to ensure no two deployments produce identical rule signatures.

### Modes of Operation 🔄
The tool operates in two modes:
- **Remove mode**: Executed with no parameters to cleanly purge all installed QoS policies.
- **Install mode**: Accepts an input file of EDR process names and creates uniquely named QoS policies that survive system reboots.

The EDRChoker technique underscores a critical architectural reality: EDR tools that depend entirely on cloud connectivity carry an inherent single point of failure. As attackers delve deeper into the Windows network stack to evade detection, defenders must extend monitoring equally deep or risk operating blind precisely when it matters most.

[Read full article](https://cybersecuritynews.com/edrchoker-tool/)