---
title: Were Telcos Warned About the Ancient Telnet Bug?
date: 2026-02-11
categories: [SECURITY]
tags: [TELNET,VULNERABILITY,CYBERSECURITY,THREAT-INTELLIGENCE]
---

## Were Telcos Warned About the Ancient Telnet Bug? 🚨

According to threat intelligence firm GreyNoise, it appears that telecommunications companies may have received advance warning regarding a critical Telnet vulnerability disclosed in January. 📉

### Key Findings:
- **Traffic Drop:** Global Telnet traffic saw a drastic decline on January 14, just six days before the security advisories for CVE-2026-24061 were made public on January 20. 
- **Exploitation Risk:** This decade-old bug in GNU InetUtils telnetd has a CVSS score of 9.8, allowing for trivial root access exploitation.
- **Session Decline:** Telnet sessions plummeted by 65% within one hour on January 14, and by 83% within two hours. Daily sessions dropped from an average of 914,000 to around 373,000, marking a 59% decrease that continues to this day.

GreyNoise's Bob Rudis and "Orbie" noted that such a rapid decline in traffic suggests a configuration change rather than a natural behavioral shift. They theorize that infrastructure operators might have received pre-advisory notifications about the vulnerability, prompting them to implement port 23 filtering on transit links starting January 14.

### Supporting Evidence:
- **Operators Affected:** 18 operators, including BT, Cox Communications, and Vultr, reported a drop from hundreds of thousands of Telnet sessions to zero by January 15.
- **Cloud Providers:** Major cloud providers were largely unaffected, with some, like AWS, experiencing a 78% increase in sessions.

While GreyNoise acknowledges that correlation does not imply causation, the timing of the traffic drop and the subsequent advisory releases, along with the ongoing port 23 filtering, warrant further investigation. 🔍

For more details, [Read full article](https://www.theregister.com/2026/02/11/were_telcos_tipped_off_to/)