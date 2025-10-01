---
title: Cisco Talos attributes Asian telecom and manufacturing attacks to Naikon PlugX campaign
date: 2025-09-29
categories: [CYBERSECURITY]
tags: [CISCO TALOS,NAIKON,PLUGX,CYBERSECURITY,MALWARE]
---

Cisco Talos uncovered an ongoing campaign, active since 2022, targeting telecommunications and manufacturing sectors in Central and South Asia. The activity is assessed with medium confidence to be linked to Naikon, a Chinese-speaking threat actor operating since 2010. This attribution is supported by the PlugX configuration format observed in the campaign and an infection chain that mirrors Naikon’s earlier RainyDay malware. The operation deploys a new PlugX variant that shares features with both RainyDay and Turian backdoors, including the abuse of legitimate applications for DLL sideloading, use of the ‘XOR-RC4-RtlDecompressBuffer’ algorithm for payload encryption and decryption, and reliance on identical RC4 keys.

“During the investigation and hunting efforts for RainyDay backdoors, Talos uncovered two significant findings,” Joey Chen and Takahiro Takeda, Cisco Talos researchers, wrote in a blog post last week. “First, we found that several instances of the Turian backdoor and newly identified variants of the PlugX backdoor were abusing the same legitimate Mobile Popup Application as RainyDay to load themselves into memory. Second, we observed that the three malware families leverage loaders which not only have a similar XOR decryption function but also use the same RC4 key to decrypt the encrypted payload.”

“The other final payload Talos identified is a customized variant of the PlugX backdoor, which we believe has become the primary backdoor used by the threat actor in recent campaigns,” according to the researchers. “While this variant of PlugX is not particularly new and its plug-in functionalities have been documented in previous reports, it stands out for a key reason: its configuration differs significantly from the previously-identified PlugX configuration. Instead, it adopts the same configuration structure as the RainyDay backdoor.”

“Additionally, by pivoting on several keylogger log files discovered on VirusTotal, Talos observed timestamps indicating that these files were actively generated throughout 2022,” the post added. “Notably, one of the log files demonstrated successful persistence within the victim’s environment, recording activity from late 2022 through December 2024 — spanning nearly two years of ongoing compromise.”

To read the complete article see: [Cisco Talos article](https://industrialcyber.co/ransomware/cisco-talos-attributes-asian-telecom-and-manufacturing-attacks-to-naikon-plugX-campaign/)  
