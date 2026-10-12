---
title: Matchboil New Tricks Same Old Evil Intentions
date: 2026-10-09
categories: [CYBERSECURITY]
tags: [MALWARE,CYBERSECURITY,APT,UAC-0099]
---

## Matchboil New Tricks Same Old Evil Intentions

ESET researchers have documented the evolution of the MATCHBOIL malware, a custom C# downloader wielded by the Russia-aligned UAC-0099 APT group. This malware is designed to download a payload from the group's C&C server, install it, and establish its persistence. Although MATCHBOIL was first documented by CERT-UA in August 2025, our research indicates that it has been in development since at least 2024. The earliest versions of the malware that we analyzed are from April 2024 and the latest from April 2026.

The analyzed MATCHBOIL versions show a change in code obfuscation from originally using Unicode symbol renaming to now employing the Eziriz .NET Reactor obfuscator. Various techniques to determine whether it is being executed in a sandboxed environment have been implemented in MATCHBOIL over time.

### Victims and Targeting

All the MATCHBOIL victims that we have seen in our telemetry were in Ukraine, across various sectors. From July to August 2025, we saw samples of the downloader at multiple transportation companies. In December of the same year, they were seen at a manufacturing company. Later, in June 2026, ESET telemetry registered further MATCHBOIL samples, this time at a company in the energy sector. UAC-0099 is a cyberespionage group targeting governmental organizations, financial institutions, and media, all in Ukraine. Based on the targeting, we believe with medium confidence that the group is aligned with Russian interests. UAC-0099 can act as an initial access broker for Sandworm, a Russia-aligned group best known for its destructive attacks in Ukraine.

### Functionality of MATCHBOIL

MATCHBOIL is a C# downloader whose purpose is to download another payload from its C&C server, install it, and then establish its persistence. The malware is distributed via malicious links in spearphishing emails. Clicking the link downloads an archive file with a VBScript file payload that downloads and executes MATCHBOIL on the victim machine. During execution, MATCHBOIL obtains the CPUID, BIOS serial number, and other basic information about the victim machine, which is used to identify the victim during C&C communication.

MATCHBOIL then performs three HTTPS requests to the C&C server; each with a different purpose. The first request receives a numeric value from the C&C server. The C&C server response to the second request is a piece of code, expected to be formatted as HTML. Embedded within the code is a hex-encoded payload that gets installed on the victim's machine. The third request receives a string from the C&C server that is saved into a file in the same directory where the payload is installed. This file can act as the payload's configuration.

From our analysis, we have discovered that in most cases, the hex-encoded payload to be installed on the victim machine is a C# backdoor known as MATCHWOK, used exclusively by UAC-0099 and first documented by CERT-UA. Once communication with the C&C server has finished, MATCHBOIL persists the installed payload, a PE file, for later execution. The persistence mechanism can be set up via scheduled tasks or by adding a value to the Windows registry.

### Evolution of the Malware

UAC-0099 has made many improvements to the downloader's code, with main changes concerning its overall logic switching from a one-shot downloader executed only once to, at the end of 2025, being executed on a two-minute timer, becoming able to retrieve the latest payload from the C&C. Obfuscation techniques evolved from using unprintable Unicode characters and string encryption algorithms to the Eziriz .NET Reactor obfuscator. Changes also include the persistence mechanism, which moved from using a combination of a specific registry value and a scheduled task (2024), to using a Windows registry value in the Run key exclusively (July 2025), to a scheduled task (late 2025). Defense evasion methods were gradually added, starting in late 2025, to check whether the malware is running in a sandbox environment. Despite the continuous changes to the malware's code, its task remains the same: download and persist a payload from the C&C.

For more detailed information, you can read the full article here: [Read full article](https://www.welivesecurity.com/en/eset-research/matchboil-new-tricks-same-old-evil-intentions/) 
