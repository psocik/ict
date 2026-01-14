---
title: CastleLoader Analysis - A Deep Dive into Stealthy Loader Targeting Government Sector
date: 2026-01-13
categories: [MALWARE]
tags: [CASTLELOADER,MALWARE,CYBERSECURITY,ANALYSIS]
---

ANY.RUN’s team conducted an extensive malware analysis of CastleLoader, the first link in the chain of attacks impacting various industries, including government agencies and critical infrastructures. CastleLoader is a stealthy malware loader used as the first stage in attacks against government entities and multiple industries. This loader has commonly occurred in cyber attacks since early 2025.

One of CastleLoader’s malicious campaigns is known to impact a total of 469 devices. It became a significant threat to organizations, especially US-based government entities. Its broader scope includes industries like IT, logistics, travel, and critical infrastructures across Europe. CastleLoader is dangerous as a link in the chain delivering information stealers and RATs, making credential theft and persistent network access a high risk.

The loader relies on a multi-stage execution chain ({Inno Setup} → {AutoIt} → {process hollowing}) to evade detection. The final malicious payload only manifests in memory after the controlled process has been altered, making traditional static detection ineffective. CastleLoader is a malicious loader malware built to deliver and install other malicious components. It lays the groundwork for the attack, becoming its starting point.

In several observed campaigns, CastleLoader is delivered through the ClickFix social engineering technique, where victims are tricked into manually executing malicious commands via fake verification or update prompts. In these cases, ClickFix acts as the initial access vector, while CastleLoader serves as the second-stage loader that deploys follow-on payloads directly in memory, helping attackers evade traditional file-based detection.

An initial analysis revealed a system process chain, at the end of which a request to 94[.]159[.]113[.]32:80 was sent. Static analysis shows the binary consists of Object Pascal (Delphi) and Inno Setup Module (installer). Archive extraction reveals several executables, including {Autolt3.exe} and the compiled script {freely.a3x}, which directly participate in the calling chain. {Autolt-Ripper} was used to extract compiled Autolt scripts, resulting in a file {script.au3} containing 24,402 code lines, the majority of which is unreadable.

Several WinAPI wrappers may potentially participate in attacks for further system infection, because it’s the Autolt script that prepares the environment and control handover. Key function calls hinting at cross-process manipulations include {kernel32.GetProcAddress}, {kernel32.CreateFileW}, {kernel32.CreateProcessW}, {kernel32.CreateMutextW}, {kernel32.OpenProcess}, {kernel32.ReadProcessMemory}, {kernerl32.DuplicateTokenEx}, {kernelbased.AdjustTokenPrivileges}, and {kernel32.WriteFile}.

Dynamic analysis showed that soon after the initialization of {Autolt3.exe}, a {kernel32.CreateProcessW} call was made, where {jsc.exe}, the final link of our chain, is located. What’s unusual is that no extra data is transmitted to {lpCommanLine}, and there’s a {CREATE_SUSPENDED} flag in {dwCreationFlags}, which points to an uncommon use of {jsc.exe}. The execution flow reveals {kernel32.CreateProcessW} creating the {jsc.exe} process flagged as {CREATE_SUSPENDED}. Additionally, {kernel32.GetThreadContext} delivers registries — the context of the main flow, which is typical for the preparation to process hollowing. {kernel32.VirtualAllocEX} allocates a 0x3B000-sized memory area in {jsc.exe} process with {MEM_COMMIT | MEM_RESERVE} flags and {PAGE_EXECUTE_READWRITE} protection.