---
title: Coordinated Cloud-Based Scanning Operation Targets 75 Known Exposure Points in One Day
date: 2025-05-27
categories: [RESEARCH]
tags: [VULNS,DNB]
---

Key Takeaways

251 malicious IPs, all hosted by Amazon and geolocated in Japan, launched a coordinated one-day scan on May 8.

These IPs triggered 75 distinct behaviors, including CVE exploits, misconfiguration probes, and recon activity.

All IPs were silent before and after the surge, indicating temporary infrastructure rental for a single operation.

Overlap analysis confirms tight coordination, not random scanning.

Targeted technologies included ColdFusion, Apache Struts, Elasticsearch, WebLogic, Tomcat, and more.

All 251 IPs are classified as malicious by GreyNoise.

This activity reflects patterns outlined in GreyNoise’s latest study, which tracks the reemergence of long-dormant threats.

Defenders should take action now: check May 8 logs, block the 251 IPs, dynamically block IPs targeting these 75 tags, and monitor for follow-up exploitation.

Similar scanning behavior preceded the discovery of two zero-days in Ivanti EPMM, reinforcing the need to treat coordinated scanning as an early warning signal.

To read the complete article see:

[Coordinated Cloud-Based Scanning Operation Targets 75 Known Exposure Points](https://www.greynoise.io/blog/coordinated-cloud-based-scanning-operation-targets-75-known-exposure-points) 