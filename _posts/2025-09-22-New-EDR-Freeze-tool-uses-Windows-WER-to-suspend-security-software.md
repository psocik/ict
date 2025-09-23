---
title: New EDR-Freeze tool uses Windows WER to suspend security software
date: 2025-09-22
categories: [SECURITY]
tags: [EDR-FREEZE,WINDOWS WER,SECURITY SOFTWARE,ANTIVIRUS]
---

A new method and proof-of-concept tool called EDR-Freeze demonstrates that evading security solutions is possible from user mode with Microsoft's Windows Error Reporting (WER) system. The technique eliminates the need of a vulnerable driver and puts security agents like endpoint detection and response (EDR) tools into a state of hibernation. By using the WER framework together with the MiniDumpWriteDump API, security researcher TwoSevenOneThree (Zero Salarium) found a way to suspend indefinitely the activity of EDR and antivirus processes indefinitely.

EDR-Freeze is described as a much stealthier method that requires no kernel driver, works entirely from the user mode, and leverages legitimate Windows components that are present by default in the operating system.

WerFaultSecure is a Windows Error Reporting component that runs with Protected Process Light (PPL) privileges, designed to collect crash dumps of sensitive system processes for debugging and diagnostic purposes. MiniDumpWriteDump is an API in the DbgHelp library that generates a snapshot ("minidump") of a process’s memory and state. While doing so, it suspends all threads of the target process and resumes them after completing the job. EDR-Freeze leverages the WerFaultSecure to trigger MiniDumpWriteDump, which temporarily suspends all threads in the target process while the dump is written. During this process, the attacker suspends the WerFaultSecure process itself, so the dumper never resumes the target, leaving the AV process in a "coma" state.

The researcher describes this as a race condition attack that can be reproduced in four steps:

1. Spawn WerFaultSecure as a PPL.
2. Pass arguments to WerFaultSecure so it calls MiniDumpWriteDump on the target PID.
3. Poll the target until it becomes suspended by the dump operation.
4. Immediately open WerFaultSecure (PROCESS_SUSPEND_RESUME) and call NtSuspendProcess to freeze the dumper.

To read the complete article see:

[Read more](https://www.bleepingcomputer.com/news/security/new-edr-freeze-tool-uses-windows-wer-to-suspend-security-software/)  
