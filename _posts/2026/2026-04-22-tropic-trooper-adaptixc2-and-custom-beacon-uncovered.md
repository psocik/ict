---
title: Tropic Trooper AdaptixC2 and Custom Beacon Uncovered
date: 2026-04-22
categories: [CYBERSECURITY]
tags: [TROPIC TROOPER,ADAPTIXC2,CYBERSECURITY,MALWARE,THREAT ANALYSIS]
---

## Tropic Trooper: AdaptixC2 and Custom Beacon Uncovered 🚀

On **March 12, 2026**, Zscaler ThreatLabz discovered a malicious ZIP archive containing military-themed document lures targeting Chinese-speaking individuals. Our analysis of this sample uncovered a campaign leveraging a multi-stage attack chain where a trojanized SumatraPDF reader deploys an AdaptixC2 Beacon agent, ultimately leading to the download and abuse of Visual Studio (VS) Code tunnels for remote access. 

During our analysis, we observed that the threat actor likely targeted Chinese-speaking individuals in Taiwan, as well as individuals in South Korea and Japan. Based on the tactics, techniques, and procedures (TTPs) observed in this attack, ThreatLabz attributes this activity to **Tropic Trooper** (also known as Earth Centaur and Pirate Panda) with high confidence. The staging server involved in this attack also hosted CobaltStrike Beacon and an EntryShell backdoor. Both malware types and configurations are known to have been used by Tropic Trooper.

The ZIP archive contained documents, with one notable lure being "Comparative Analysis of US-UK and US-Australia Nuclear Submarine Cooperation (2025).exe", which is actually a trojanized version of the SumatraPDF reader binary. When executed, this loader triggers a multi-stage attack: it downloads and displays a new decoy PDF that is shown to the victim while discreetly downloading and running an AdaptixC2 Beacon agent in the background. The trojanized executable resembles the open-source SumatraPDF reader at first glance, featuring identical certificates and PDB paths to those of the legitimate SumatraPDF executable. However, the signature of this binary is invalid because it has been trojanized with TOSHIS loader. This shellcode is an AdaptixC2 Beacon agent, marking a departure from earlier TOSHIS versions, which delivered either a Cobalt Strike Beacon or a Merlin Mythic agent.

An analysis of the InjectedCode function shows that it is largely identical to the TOSHIS loader described in TrendMicro's TAOTH report, with clear similarities observed such as the use of the same User-Agent and a similar .dat file extension.

The second-stage backdoor employed in this attack is the open-source AdaptixC2 Beacon agent, which incorporates a customized Beacon Listener. The threat actors created a custom AdaptixC2 Beacon listener, leveraging GitHub as their command-and-control (C2) platform. This custom listener differs from typical AdaptixC2 HTTP/TCP listeners because the server cannot identify the agent's external IP address when using GitHub, so the agent retrieves its external IP address by sending a request to ipinfo.io. This external IP address is then included and sent back to the C2 with every beacon. The agent then sends a beacon to the C2 by performing a POST request to GitHub Issue #1 to establish a session. After beaconing, the agent checks for tasks to be executed by making a GET request to '/repos/cvaS23uchsahs/rss/issues?state=open'. The API returns a JSON list of open issues, and the agent uses substring matching, rather than a full JSON parser, to extract the issue number, title, and body fields for each issue retrieved. Depending on the issue title, the agent uses varying logic to process the issue and extract the actual task, which is RC4 encrypted using the session key.

[Read full article](https://www.zscaler.com/blogs/security-research/tropic-trooper-pivots-adaptixc2-and-custom-beacon-listener)