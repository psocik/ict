---
title: Linux Process Name Masquerading
date: 2026-06-24
categories: [RESEARCH]
tags: [LINUX,SECURITY,PROCESS,MALWARE]
---

## Linux Process Name Masquerading

When you list running processes on a computer, can you trust what you see? 🤔 If you're facing a rootkit, malicious processes can be simply hidden (the API calls or commands to list processes have been tampered). But a malicious process can also mimic a non-suspicious name by masquerading their name. This technique (T1036 in the MITRE ATT&CK framework) has been used by attackers in many campaigns. The goal is to hide the "malware" process name by replacing it with something that won't attract the Security Analyst's eyes or defeat security controls.

### Understanding Process Name Storage

First of all, you need to remember that the process name can be stored in different locations:
- In `/proc/<pid>/comm`: This file contains the process name (max 15 characters). This is what the default 'ps' and 'top' commands show.
- In `/proc/<pid>/cmdline`: We find the full command line (read: we see the argv array). This is used by the 'ps aux', 'pf -f' or 'pgrep -f' commands.

To alter the process name in 'comm', you just have to call `prctl(PR_SET_NAME)`. To alter the process name in 'cmdline' but... there is a limitation in this case! argv[0] is a fixed-size buffer! You can't just point it somewhere else, because the kernel reports the original memory region. To bypass this constraint, you have to spill into the contiguous argv[1..n] / environ block.

### Detection Tools

A good news is that tools like Kunai (based on eBPF) will catch the real command line but won't be able to find back the exec name. This is a nice way to detect process name masquerading. Kunai's logs reveal the true `"command_line": "./ps-masquerade"` and `"exe": { "path": "/home/remnux/ps-masquerade" }` for a masqueraded process.

### Windows Operating Systems

What about Windows operating systems? It's a bit tricky because the kernel is involved. Process names are stored in the Process Environment Block (PEB) which can be modified by the process itself (in user land). The PEB holds ImagePathName and CommandLine as UNICODE_STRINGs. These are writable from within the process. Task Manager, WMI's CommandLine, and a lot of tooling read from here. In kernel model, EPROCESS holds ImageFileName (a 15-char ASCII field like the Linux comm) and SeAuditProcessCreationInfo.ImageFileName (the full NT path). These are populated by the kernel from the image that was actually mapped, so from user mode you can't simply rewrite them.

To read the complete article see: [Read full article](https://isc.sans.edu/forums/diary/Linux%20Process%20Name%20Masquerading/33102/)