---
title: Wave of Citrix NetScaler Scans Utilize Thousands of Residential Proxies
date: 2026-02-03
categories: [SECURITY]
tags: [CITRIX,NETSCALER,SCANNING,SECURITY,PROXIES]
---

## Wave of Citrix NetScaler Scans 🚀

A coordinated reconnaissance campaign targeting **Citrix NetScaler** infrastructure over the past week has utilized tens of thousands of residential proxies to discover login panels. This activity was observed between **January 28 and February 2**, indicating an organized discovery effort.

Threat monitoring platform **GreyNoise** traced the source of the scanning traffic to over **63,000 distinct IPs** that launched **111,834 sessions**. Notably, **79%** of the traffic was aimed at Citrix Gateway honeypots, with approximately **64%** coming from residential proxies, appearing as legitimate consumer ISP addresses and bypassing reputation-based filtering. The remaining **36%** originated from a single Azure IP address.

### Key Indicators of Malicious Intent 🔍

Two significant indicators of malicious intent were identified:
- The most active source generated **109,942 sessions** from **63,189 unique IPs**, targeting the authentication interface at `/logon/LogonPoint/index.html` to identify exposed Citrix login panels at scale.
- A second indicator, observed on **February 1st**, involved a six-hour sprint with **10 IPs** launching **1,892 sessions**, focusing on the URL path `/epa/scripts/win/nsepa_setup.exe` to enumerate Citrix versions via EPA artifacts.

GreyNoise notes that the attacker employed a user agent for **Chrome 50**, released in early 2016. This specific targeting suggests interest in version-specific exploit development or vulnerability validation against known Citrix ADC weaknesses.

### Recommendations for System Administrators 🛡️

GreyNoise recommends several detection opportunities for this latest activity:
- Monitor for the **blackbox-exporter** user agent from unauthorized sources.
- Alert on external access to `/epa/scripts/win/nsepa_setup.exe`.
- Flag rapid enumeration of `/logon/LogonPoint/` paths.
- Watch for HEAD requests against Citrix Gateway endpoints.
- Track outdated browser fingerprints, specifically **Chrome 50** (circa 2016).

Additionally, system administrators should review the necessity of internet-facing Citrix Gateways, restrict access to the `/epa/scripts/` directory, disable version disclosure in HTTP responses, and monitor for anomalous access from residential ISPs in unexpected regions.

For further details, you can read the complete article here: [Read full article](https://www.bleepingcomputer.com/news/security/wave-of-citrix-netscaler-scans-use-thousands-of-residential-proxies/)