---
title: MaaS operation using Emmenhtal and Amadey linked to threats against Ukrainian entities
date: 2025-07-17
categories: [RESEARCH]
tags: [MAAS,EMMENHTAL,AMADEY,UKRAINIAN THREATS]
---

In April 2025, Cisco Talos identified a Malware-as-a-Service (MaaS) operation that utilized Amadey to deliver payloads. The MaaS operators used fake GitHub accounts to host payloads, tools, and Amadey plug-ins, likely as an attempt to bypass web filtering and for ease of use. Several operator tactics, techniques, and procedures (TTPs) overlap with a SmokeLoader phishing campaign, identified in early 2025, that targeted Ukrainian entities. The same variant of Emmenhtal identified in the SmokeLoader campaign was used by the MaaS operation to download Amadey payloads and other tooling.

In early February 2025, Talos observed a cluster of invoice payment and billing-themed phishing emails that appeared to target Ukrainian entities. These emails included compressed archive attachments (e.g., ZIP, 7Zip, or RAR) containing at least one JavaScript file that used several layers of obfuscation to disguise a PowerShell downloader. The execution of the JavaScript and PowerShell script resulted in the download and execution of SmokeLoader on the victim system. Talos assessed the JavaScript downloaders to be the Emmenhtal loader, based on notable similarities between the obfuscation methods observed in the collected samples and those described by Orange Cyberdefense.

During analysis of the Emmenhtal loaders collected from this phishing campaign, Talos identified additional samples on VirusTotal that were highly similar in structure but did not appear to be part of the original activity cluster. Most notably, these samples were not delivered via email but were instead found in several public GitHub repositories. They also did not deliver SmokeLoader as a next-stage payload. Instead, the Emmenhtal samples were being used to deliver Amadey, which in turn downloaded a variety of custom payloads from certain public GitHub repositories.

To read the complete article see:
[Full Article](https://blog.talosintelligence.com/maas-operation-using-emmenhtal-and-amadey-linked-to-threats-against-ukrainian-entities/).