---
title: ToolShell An all-you-can-eat buffet for threat actors
date: 2025-07-24
categories: [SECURITY]
tags: [VULNERABILITIES,THREAT ACTORS,SHAREPOINT,CYBERSECURITY]
---

On July 19, 2025, Microsoft confirmed that a set of zero-day vulnerabilities in SharePoint Server called ToolShell is being exploited in the wild. ToolShell is comprised of CVE-2025-53770, a remote code execution vulnerability, and CVE-2025-53771, a server spoofing vulnerability. These attacks target on-premises Microsoft SharePoint servers, specifically those running SharePoint Subscription Edition, SharePoint 2019, or SharePoint 2016. SharePoint Online in Microsoft 365 is not impacted. Exploiting these vulnerabilities enables threat actors to gain entry to restricted systems and steal sensitive information.

Starting from July 17, ToolShell has been widely exploited by all sorts of threat actors, from petty cybercriminals to nation-state APT groups. Since SharePoint is integrated with other Microsoft services, such as Office, Teams, OneDrive, and Outlook, this compromise can provide the attackers a staggering level of access across the affected network.

As part of the attack, the threat actors often chain together four vulnerabilities: the previously patched CVE‑2025‑49704 and CVE-2025-49706, alongside the already mentioned CVE-2025-53770 and CVE-2025-53771. As of July 22, CVE‑2025‑53770 and CVE-2025-53771 have also been patched.

To read the complete article see: [ESET Research](https://www.welivesecurity.com/en/eset-research/toolshell-an-all-you-can-eat-buffet-for-threat-actors/)

More research on the vulnerability is here: [BitSight Blog](https://www.bitsight.com/blog/toolshell-threat-brief-sharepoint-rce-vulnerabilities-cve-2025-53770-53771-explained)