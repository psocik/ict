---
title: Process Trees in Livehunt YARA Rules That Know Who Launched What
date: 2026-10-27
categories: [SECURITY]
tags: [YARA,LIVEHUNT,PROCESS-TREES,SECURITY,ANALYSIS]
---

## Process Trees in Livehunt: YARA Rules That Know Who Launched What

🚀 **YARA-X v1.21.0 and v1.22.0** have introduced new fields: `parent_name` and `ancestor_names` in the `vt.behaviour.processes_list`. This enhancement allows VirusTotal to provide detailed insights for every sandbox report that includes a process tree, offering one entry per process that identifies its creator and ancestors.

This improvement significantly enhances analysis compared to the previous `vt.behaviour.processes_created`, which only provided a flat list. For instance, while it would report that `mshta.exe` and `powershell.exe` ran, it wouldn't indicate which process initiated the other. Understanding this hierarchy is crucial: **PowerShell** on its own may be considered noise, but **PowerShell launched by `mshta.exe`** is a significant indicator. Now, every file with sandbox reports reaching Livehunt includes `vt.behaviour.processes_list`, detailing each entry with its parent's name, ancestors' names, and the files it interacted with.

### Key Changes
- The addition of `parent_name`, `ancestor_names`, and per-process file lists fundamentally alters how rules are crafted, enabling specific detections such as "the PowerShell that `cmd.exe` started wrote a `.dll`". Rule writers should note that process names are not normalized; thus, `icontains` should be utilized for executable name matching. Processes must be linked by name rather than by PID. The `ancestor_names` is constructed independently per sandbox report, ensuring accuracy for lengthy process chains.

### Case Study
In a case study, porting a Sigma rule for "Suspicious MSHTA Child Process" illustrates the necessity of parent information. The Livehunt version maps ParentImage to `parent_name` and Image to `name`. Sigma checks `OriginalFileName` for renamed binaries, a feature that sandbox process names lack, meaning a renamed `mshta.exe` could bypass such a rule. An Excel file (d30a0a6c09f664446943d82982f0630e85c447cbe84be8a74b6db6d66effbe80, tagged CVE-2017-0199) demonstrated that Excel was not the direct parent of `mshta.exe`. The exploit utilized DCOM, with `mshta.exe` initiated by the DCOM launcher service. To detect this, analysts can check the grandparent using `p.ancestor_names[1] icontains "svchost.exe" and p.ancestor_names[1] icontains "dcomlaunch"`, as `ancestor_names[1]` identifies the grandparent.

### Investigation Alerts
A `services.exe` with any parent other than `wininit.exe` warrants investigation. However, a crucial lesson is to verify what sandboxes report for clean files before encoding parental "should-be" relationships. For example, an initial rule for `lsass.exe` resulted in false positives because sandboxes sometimes reported `lsass.exe` with `services.exe` as its parent. Furthermore, a sample (fe8357febe312ad58a448292f5f8a09075d7694c, Cd5KK.exe) initiated `C:\Windows\System32\NlsLexicons0c1a\services.exe` and replicated itself to eight locations.

[Read full article](https://blog.virustotal.com/2026/10/process-trees-in-livehunt-yara-rules.html)