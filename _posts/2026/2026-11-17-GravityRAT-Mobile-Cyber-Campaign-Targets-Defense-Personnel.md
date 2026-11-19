---
title: GravityRAT Mobile Cyber-Campaign Targets Defense Personnel
date: 2026-11-17
categories: [CYBERSECURITY]
tags: [GRAVITYRAT,CYBERSECURITY,MALWARE,DEFENSE,THREATS]
---

## GravityRAT Mobile Cyber-Campaign Targets Defense Personnel 🚨

Lookout has uncovered an active cyber-surveillance campaign deploying **GravityRAT** malware to target defense industry and military personnel. Based on Lookout telemetry, primary targets are individuals from India who are seeking lucrative positions at foreign defense contractors. Over the past 12 months, Lookout detected GravityRAT across 14 devices from India. 

GravityRAT is a long-running, multi-platform surveillance framework active since at least 2015. It is attributed to Pakistan-aligned threat actors tracked under names such as SpaceCobra and Cosmic Leopard. While initially it was a Windows-based tool, GravityRAT has expanded into a cross-platform framework capable of targeting Android, Windows, and macOS operating systems.

### Key Findings 🔍
Lookout discovered several live, single-page portals that mimic recruitment firms and commercial software utilities to distribute GravityRAT payloads. A notable example is the recruitment portal at recruitersglobal.net, which delivers the GravityRAT payload mobile application **GlobalRecruiters.apk** (com.resumee.resumebuilder). Posing as "Global Recruiter," the site offers automated resume-building tools and job connections to entice applicants. To build credibility, the site's "Our Clients" section prominently displays logos of major international defense and aerospace leaders, including Airbus SE, BAE Systems PLC, Thales, Lockheed Martin Corporation, Rheinmetall AG, Northrop Grumman Corporation, Saab AB, Rolls-Royce, and Safran. Explicitly targeting this sector aligns directly with GravityRAT's historical focus on government and defense personnel.

When users click the Google Play download button on these malicious landing pages, a custom pop-up dialog appears with a notice stating: "The Google Play version is currently under review. Please download the APK for now." This technique provides a plausible explanation for the need to sideload this app to bypass an alleged delay.

### Data Exfiltration 📊
GravityRAT is designed for extensive and periodic data exfiltration, functioning autonomously to upload collected data to C2 servers on their PHP endpoints at intervals ranging from 1 to 30 minutes. Collected victim data types include:
- Complete contact directory dumps
- Incoming, outgoing, and missed call logs
- Historical and real-time SMS messages
- GPS location coordinates
- External storage directory trees and files
- Document, image & audio files with various extensions
- Encrypted WhatsApp backup databases
- Connected Wi-Fi network details, device accounts, and hardware IMEI identifiers.

By pivoting across live infrastructure associated with mobile builds that shared identical name servers and registration dates, other malicious domains like dropdeckx.com were uncovered. This domain advertises a Windows executable file with a similar single-page website and a cloud storage utility lure identical to those previously utilized by GravityRAT threat actors. It is an Electron-based cloud storage utility called **DropDeckX** that evades virtual machines, harvests system telemetry and credentials, establishes persistence via Task Scheduler, and downloads secondary payloads. The sample uses the subdomain web.dropdeckx.com as its C2 server. Similar variants of this malware have been tracked publicly as **HeavyLift**.

### Conclusion 🔒
GravityRAT command infrastructure uses Cloudflare-protected domains. Implants route exfiltrated log data to PHP backend handling scripts hosted on subdomains disguised as legitimate Android frameworks.

For more detailed insights, [Read full article](https://www.lookout.com/threat-intelligence/article/gravityrat-spyware).