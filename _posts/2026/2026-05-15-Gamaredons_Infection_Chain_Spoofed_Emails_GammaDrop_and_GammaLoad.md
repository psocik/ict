---
title: Gamaredon's Infection Chain Spoofed Emails, GammaDrop and GammaLoad
date: 2026-05-15
categories: [CYBERSECURITY]
tags: [GAMAREDON,MALWARE,CYBERSECURITY,UKRAINE]
---

## Gamaredon's Infection Chain: Spoofed Emails, GammaDrop and GammaLoad 🚀

Investigating Gamaredon's abuse of CVE-2025-8088, we identified a dozen waves of spearphishing emails targeting Ukrainian state institutions in a campaign that is still active, dating back to September 2025. These emails, either spoofed or sent from compromised government accounts, deliver persistent, multi-stage VBScript downloaders that profile the infected system. This report documents Gamaredon's GammaDrop and GammaLoad downloader variants, the infrastructure behind them, and the methods used to deliver the spearphishing emails.

Both variants function as downloaders, while GammaLoad additionally establishes persistence and beacons victim data to the C2 server, enabling the operator to selectively deliver a tailored payload. The supporting infrastructure combines Cloudflare Workers domains, fast flux DNS, dynamic DNS providers, and attacker-controlled email relays—all constantly evolving.

Gamaredon, also known as Aqua Blizzard, Primitive Bear, Shuckworm, or UAC-0010, has been exploiting CVE-2025-8088 to target Ukrainian organizations. This path traversal vulnerability, documented by ESET, has been leveraged by multiple threat actors since the summer of 2025, and Gamaredon is known to have been using it since at least September 2025.

An example spearphishing email was sent from a compromised email account belonging to a local government official in Odessa Oblast on March 18, 2026. The email's body, written in Ukrainian, translates to: "Case number: 2/1369-26... Document: Court summons for appearance in court... Document date: 18.03.2026".

The email contains a RAR archive as an attachment named Судова_повістка_1_13_4_1882_18.03.2026.rar that exploits CVE-2025-8088, a WinRAR directory traversal vulnerability (up to v7.13). The archive contains a single file entry accompanied by an NTFS alternate data stream (ADS) service record. The VBS payload, GammaDrop, is stored as an ADS of the PDF. The stream name contains a path traversal sequence that, upon extraction, causes WinRAR to write the VBS payload to the Windows Startup folder.

This heavily obfuscated VBS payload fetches a remote HTA (GammaLoad) from a Cloudflare Workers C2 server, drops it to %TEMP%\brushedGpI.hta, and executes it. The script uses randomized variable names, junk functions, and string building techniques consistent with Gamaredon's auto-generated tooling. The URL structure is consistent across the GammaDrop samples we analyzed.

For example, a more recent wave from April 27, 2026, uses: hxxp://thre6d.rfgah07ggr.workers[.]dev////. In some cases, we observed the RAR archives skip GammaDrop entirely and deploy GammaLoad directly. GammaLoad is executed by GammaDrop via Wscript.Shell.Run, which launches mshta.exe in a hidden window. Its purpose is to serve as a persistent C2 beacon that profiles the infected host, downloads a next-stage payload, and executes it.

[Read full article](https://harfanglab.io/insidethelab/gamaredon-gammadrop-gammaload/)