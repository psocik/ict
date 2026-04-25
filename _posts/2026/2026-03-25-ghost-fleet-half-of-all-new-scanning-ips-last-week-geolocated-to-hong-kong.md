---
title: Ghost Fleet Half of All New Scanning IPs Last Week Geolocated to Hong Kong
date: 2026-03-25
categories: [CYBERSECURITY]
tags: [GHOST FLEET,SCANNING IPS,HONG KONG,GREY NOISE]
---

## Ghost Fleet: Half of All New Scanning IPs Last Week Geolocated to Hong Kong 🚀

Last week, the GreyNoise Observation Grid (GOG) observed something unusual: **242,666 new scanning IPs** geolocating to Hong Kong appeared in just seven days -- nearly half of all new scanning IPs observed by GreyNoise that week. And **99.7%** of them never completed a single TCP connection. These IPs are ghosts -- they appeared in GreyNoise data but never proved they were real. Because they never completed a TCP handshake, GreyNoise cannot verify that the traffic actually originated from those addresses. They carried no payloads, triggered no detection signatures, and performed no exploitation. All they left behind were a quarter-million unverified IP addresses now sitting in observation datasets.

### Key Observations:
- Between March 12 and 18, GreyNoise observed **242,666 new IPs** geolocating to Hong Kong.
- Of these, **241,964 are spoofable**. One organization, **GNET INC. (AS9294)**, is the single largest contributor, adding **28.9%** of all new IPs observed by GreyNoise in a single week.
- No exploitation, no brute-force activity, and no web crawling were detected. Just incomplete connections.

The ghost fleet is the noise. The signal is **UCLOUD (AS135377)**. UCLOUD contributes just **1,746 IPs** -- **0.4%** of the active IPs geolocating to Hong Kong in GreyNoise data. But it accounts for an outsized share of observed scanning and exploitation attempts. The entity generating **82x more IPs** (GNET INC.) has zero classified malicious activity, while UCLOUD has **663** observed scanning attempts targeting MySQL, SSH, SMB, and RDP, with traffic reaching GOG sensors in more than **20 countries**.

### Recommendations for Defenders:
- Review detection stacks that don't distinguish spoofable IPs from confirmed scanners.
- Update blocklists, as the sources that dominated scanning the prior week declined or disappeared, replaced by infrastructure geolocating to Hong Kong, Poland, and Germany.
- Monitor **UCLOUD (AS135377)** for multi-protocol scanning activity targeting MySQL (3306), SSH (22), SMB (445), and RDP (3389).
- Track the ghost fleet ASNs for behavioral changes: AS9294, AS138415, AS55933, AS135097, AS17561, AS45753.

GreyNoise is not attributing this activity to a named threat actor or state sponsor. The geographic references in this post describe where IPs are registered, not necessarily where the operators are located.

[Read full article](https://www.greynoise.io/blog/ghost-fleet-half-new-scanning-ips-geolocated-to-hong-kong)