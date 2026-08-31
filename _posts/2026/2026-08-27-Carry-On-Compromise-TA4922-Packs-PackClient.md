---
title: Carry-On Compromise TA4922 Packs PackClient
date: 2026-08-27
categories: [CYBERSECURITY]
tags: [MALWARE,TA4922,PACKCLIENT,CYBERCRIME]
---

## Carry-On Compromise: TA4922 Packs PackClient

**Date Published:** August 27, 2026  
**Source:** Proofpoint  

🚨 Proofpoint researchers have recently uncovered a new RAT framework named **PackClient**. This malware is being utilized by the threat actor **TA4922**, who is known to be Chinese-speaking, and it appears to be actively marketed on Telegram. PackClient is a fully featured, modular command and control (C2) framework that enables data theft, surveillance, and the downloading of additional plugins and payloads. With this new payload, TA4922 is expanding its arsenal of initial-access malware, much of which originates from the Chinese-speaking cybercrime ecosystem. Given that PackClient is suspected to be marketed through Chinese-language Telegram channels, it is likely that additional Chinese-speaking threat actors may also adopt this malware in future campaigns.

In late May 2026, Proofpoint researchers identified a campaign attributed to TA4922 that targeted organizations operating in mainland China. This campaign delivered a payload identified as part of the PackClient framework, using a tax-themed lure that impersonated the **Shandong Provincial Tax Bureau**. The compliance language pressured recipients into action, with an embedded URL directing victims to download a ZIP archive named **数据资料.zip** from an actor-controlled domain. This archive contained an executable that initiated the installation of PackClient.

Since the initial identification of PackClient in the May 2026 campaign, researchers have observed at least two additional campaigns by TA4922 delivering the malware. In mid-July 2026, the actor targeted organizations in India using Hindi-language tax enforcement lures that impersonated the **Indian Income Tax Department**. Unlike the earlier China-focused activity, these messages delivered a ZIP archive named **Tax_Notice_23665.zip**, which contained an IMG disk image. When mounted, this image included an executable and a malicious DLL that leveraged DLL sideloading to execute **Donut Loader** and ultimately install PackClient.

Post-compromise traffic has been observed communicating with infrastructure at various IP addresses. Additionally, researchers noted C2 communications over TCP port 6666. The threat actor subsequently deployed **ManageEngine Remote Monitoring and Management (RMM)** software several hours after the initial infection, indicating additional post-compromise tooling.

PackClient consists of a first-stage loader executable, a second-stage loader DLL module, a core module, and several optional plugins that can be downloaded upon operator command. The core module, referred to as **PackClientCore**, has a modular plugin system capable of dynamically downloading and executing additional plugins. It supports two simultaneous C2 server connections with independent configurations for each. This core module accepts over 60 commands from the C2 server, enabling various actions like file system management, surveillance, data theft, payload and plugin installation, and remote configuration updates.

PackClient can enumerate running processes and report on security products, messaging apps, and browsers. It includes keylogger and clipper capabilities, alongside registry-based persistence and configuration storage. If a **Telegram Desktop** process is detected, the client reports this information to the C2. Based on code analysis, it appears that the C2 may deliver a special Telegram plugin that writes data to the local Telegram config file, potentially allowing the malware operator to intercept and man-in-the-middle Telegram traffic.

For more detailed insights, you can read the full article here: [Read full article](https://www.proofpoint.com/us/blog/threat-insight/carry-compromise-ta4922-packs-packclient) 
