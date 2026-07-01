---
title: RPG Maker MV and MZ Vulnerable to OS Command Injection
date: 2026-06-30
categories: [SECURITY]
tags: [RPG MAKER,VULNERABILITY,OS COMMAND INJECTION,SECURITY]
---

## RPG Maker MV and MZ Vulnerable to OS Command Injection 🚨

RPG Maker MV and MZ, provided by Gotcha Gotcha Games Inc., contain a critical OS command injection vulnerability. These game development tools allow users to save their game status and related parameters. However, when loading a save-file, RPG Maker MV and MZ fail to properly handle crafted contents, potentially leading to OS command injection. If a user loads a specially crafted save-file, arbitrary OS commands may be executed.

### Affected Versions
- RPG Maker MV versions 1.6.3 and earlier
- RPG Maker MZ versions 1.10.0 and earlier

### Vulnerability Details
This vulnerability has been identified as **CVE-2026-56137** and is classified under OS Command Injection (CWE-78). The vulnerability has a **CVSS:4.0 Base Score of 8.4** with the vector AV:L/AC:L/AT:N/PR:N/UI:A/VC:H/VI:H/VA:H/SC:N/SI:N/SA:N. Additionally, a **CVSS:3.0 Base Score of 7.8** has been reported.

### Recommended Actions
As a primary solution, users are advised **not to load untrusted save-files**. Gotcha Gotcha Games Inc. has issued a 'Notice Regarding the Handling of Games, Save Data, and Assets from Unknown Sources' concerning this vulnerability. The issue was initially reported to IPA by Shuta Ide of GMO Flatt Security Inc., and JPCERT/CC coordinated with the developer under the Information Security Early Warning Partnership.

For further details, you can read the complete article here: [Read full article](https://jvn.jp/en/jp/JVN69681784/)