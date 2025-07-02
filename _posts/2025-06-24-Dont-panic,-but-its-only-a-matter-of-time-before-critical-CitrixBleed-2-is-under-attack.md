---
title: Don't panic, but it's only a matter of time before critical 'CitrixBleed 2' is under attack
date: 2025-06-24
categories: [SECURITY]
tags: [CITRIX,SECURITY,VULNERABILITY]
---

Citrix patched a critical vulnerability in its NetScaler ADC and NetScaler Gateway products that is already being compared to the infamous CitrixBleed flaw exploited by ransomware gangs and other cyber scum, although there haven't been any reports of active exploitation. Yet. 

Security analyst Kevin Beaumont dubbed the vulnerability "CitrixBleed 2." As The Register's readers likely remember, that earlier flaw (CVE-2023-4966) allowed attackers to access a device's memory, find session tokens, and then use those to impersonate an authenticated user while bypassing multi-factor authentication — which is also possible with this new bug.

The more recent out-of-bounds read flaw, tracked as CVE-2025-5777, received a 9.3 severity rating and affects the following builds, according to Citrix's security bulletin:
- NetScaler ADC and NetScaler Gateway 14.1 before 14.1-43.56
- NetScaler ADC and NetScaler Gateway 13.1 before 13.1-58.32
- NetScaler ADC 13.1-FIPS and 13.1-NDcPP before 13.1-37.235
- NetScaler ADC 12.1-FIPS before 12.1-55.328

To read the complete article see: [The Register](https://www.theregister.com/2025/06/24/critical_citrix_bug_citrixbleed/) 