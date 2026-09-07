---
title: Plex Issues Urgent Patch Warning for 300,000 Media Servers
date: 2026-09-04
categories: [SECURITY]
tags: [PLEX,SECURITY,VULNERABILITY,UPDATE]
---

## Urgent Patch Warning for Plex Media Servers 🚨

Plex has issued an urgent warning to update **Plex Media Servers** and the **Desktop client app** to the latest versions. Thousands of Plex owners haven't patched their servers to address previous severe vulnerabilities. Plex urges users to update **Plex Media Server 1.43.2** and earlier, plus Plex Desktop, as these updates fix several security issues.

Public scans by ShadowServer Foundation reveal nearly **300,000 exposed Plex instances** worldwide, with the largest number, **134,800**, in the US, followed by **21,300** in the UK, **19,500** in Canada, **13,600** in both France and Canada, **12,700** in Australia, and **10,700** in the Netherlands.

More than **2,400 Plex instances** remain vulnerable to **CVE-2025-34158**, a severe vulnerability from 2025, that allows privilege escalation, persistent unauthorized access, and difficulty in properly revoking compromised credentials. China-Nexus cyber espionage actors have previously been observed leveraging a hacked Plex instance as a command-and-control server to target and control routers.

Plex issued a security notice this week, warning users that it is important to update **Plex Media Server v1.43.2** and earlier to the latest version. "We recently released **Plex Media Server 1.43.3** and **Plex Desktop 1.115.0** to address a number of security issues. We recommend all server owners and Desktop users update to the latest version as soon as possible," the Plex notice reads.

The actual patches have been available for weeks or months now, with PMS version **1.43.3** first released in the Beta channel on **June 22nd, 2026**, and made available to everyone in **July**.

The changelogs listed several bugs that the latest releases addressed, including accepting crafted API requests with invalid URIs (Uniform Resource Identifiers), a potential vulnerability in the **CompanionProxy** component, which handles network traffic, and the ability to modify **TranscoderH264Options** and **TranscoderH264OptionsOverride** preferences over the network.

Plex says **CVE (Common Vulnerabilities and Exposures)** IDs have been requested, hinting that more details will be available once they're published. However, Plex currently deliberately withholds technical details about the types of vulnerabilities affecting the unpatched later versions of its software.

Plex advisory contains guides on updating Plex servers across various platforms, including **Windows**, **macOS**, **Linux**, **Android (Nvidia Shield)**, **Docker**, and **NAS systems**. If the updated version is not available in the package manager for a specific NAS device, Plex recommends downloading and updating it manually.

For more details, check out the full article here: [Read full article](https://cybernews.com/security/plex-security-alert-urges-servers-update/) 