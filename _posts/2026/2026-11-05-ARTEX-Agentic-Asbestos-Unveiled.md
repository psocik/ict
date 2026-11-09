---
title: ARTEX Agentic Asbestos Unveiled
date: 2026-11-05
categories: [CYBERSECURITY]
tags: [ARTEX,ASBESTOS,CYBERSECURITY,PENETRATION-TESTING,THREAT-INTELLIGENCE]
---

## ARTEX - Agentic Asbestos 🚀

**Published on:** November 5, 2026  
**Source:** Censys  

ARTEX, an open-source, LLM-driven autonomous penetration testing framework, was released in July 2026. In October, two threat intelligence companies attributed its use as part of threat actor operations. CrowdStrike linked it to a campaign against South Korean financial institutions, while Microsoft connected it to Storm-0940's compromise of ConnectWise customer tenants.

ARTEX was published on GitHub as Autumn-27/ARTEX on July 26, 2026, under the AGPL-3.0 license. Its developer, Autumn-27, is also the author of ScopeSentry, a widely used Chinese asset-discovery and vulnerability-scanning platform. On October 8, the day after CrowdStrike released a report detailing observed malicious usage, the author posted a statement claiming they were not involved in the attacks and that ARTEX was meant for testing within authorized asset scopes. The project subsequently went closed-source with no further releases, and the repository has since been taken down. Archived copies, translations, and rebrands such as ScopeWeaver are still circulating.

Microsoft describes ARTEX as capable of running "from reconnaissance through data exfiltration" with minimal human input.  

On October 7, 2026, CrowdStrike reported that an unattributed actor using ARTEX targeted a South Korean finance company from late September to early October. The actor was assessed with moderate confidence to be a financially motivated Chinese speaker. This actor breached a broker-facing loan inquiry service at one bank and an employee mobile system at another, exfiltrating data. ARTEX ran on 38.244.50[REDACTED BY DNB EDITORS TO GET PAST GOOGLE FILTERS] with DeepSeek v4.1-flash. CrowdStrike found the activity because the actor left open directories exposing a .claude folder, prompts, session histories, and ARTEX configuration files.

Censys scan history for that host showed exposed file names revealing the actor working on targets beyond South Korean banks, including payment and gaming services. Additionally, Microsoft attributed the ConnectWise Cloud Backup supply-chain compromise to Storm-0940, a China state-aligned actor active since 2021. This group used ARTEX to automate scanning, password spraying, and OAuth application abuse, attempting sign-ins to more than 2,250 tenants.

As of November 4, 2026, Censys observed 1,465 hosts running an exposed ARTEX console. About 650 sit in two blocks of identically configured hosting, which leaves roughly 815 distinct-looking deployments. Censys observed 32 open directories on ARTEX hosts, exposing post-exploitation kits, stagers, and implants. Of the 1,465 ARTEX hosts, 155 (10.6%) also run at least one other threat that Censys detects. These include other AI attack frameworks, recon platforms, tunneling tools, and C2: Vshell, Cobalt Strike, and Adaptix C2.

Operators stack AI attack frameworks; CyberStrikeAI shares hosts with ARTEX on 70 hosts, and PentAGI, HexStrike AI, and RedAmon also appear. AI tooling also sits next to conventional C2, such as ARTEX and PentAGI alongside a Cobalt Strike teamserver on port 50050 and an Adaptix C2 listener on 4321 on 1.14.104[.]208. Furthermore, 43 ARTEX hosts run self-hosted LLM gateway or reseller software, mainly CLIProxyAPI (19) and New API (18). For defenders, unfamiliar LLM proxies and resellers in egress logs are worth investigating.

To identify ARTEX consoles, defenders can look for default port 8787/tcp, with 8790 and 443 also common. Pivots include co-located open directories, Vshell or FRP listeners, and LLM proxy software like CLIProxyAPI and New API on the same host. Historically, mitmproxy banners and short-lived Python SimpleHTTP servers on high ports often appear before the console does.

[Read full article](https://censys.com/blog/artex-agentic-asbestos)