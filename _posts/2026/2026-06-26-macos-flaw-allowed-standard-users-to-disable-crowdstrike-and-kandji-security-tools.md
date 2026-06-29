---
title: macOS Flaw Allowed Standard Users to Disable CrowdStrike and Kandji Security Tools
date: 2026-06-26
categories: [CYBERSECURITY]
tags: [MACOS,SECURITY,VULNERABILITY,CROWDSTRIKE,KANDJI]
---

## Major macOS Vulnerability Discovered! 🚨

Cybersecurity defense firm **XM Cyber** has identified a significant security flaw in the Apple macOS operating system. This vulnerability lies within the core communication architecture utilized by leading enterprise protective software, creating a structural gap that allows standard user accounts to bypass essential security boundaries.

Many Mac applications rely on a background communication system known as **XPC** to facilitate communication between different software components. XM Cyber's researchers found that these background services typically trust messages appearing to originate from their own applications by verifying a code signature called **CDHash**. However, they discovered that hackers could exploit this setup by combining **CDHash cache exploitation** with a **NIB payload injection**. This method enables an unprivileged threat actor to hijack a trusted application, launch a legitimate security program to gain the system's trust, and manipulate the application bundle structure to inject a malicious interface file.

Once inside, the malicious code utilizes a tool called **JavaScript for Automation (JXA)** to bypass standard scripting limits and control low-level system memory. The background service unwittingly accepts these fake instructions, allowing the hacker to invoke built-in functions such as **runProcessWithCommand** and **terminateAppsAndAgents**. Consequently, the targeted security products may end up disabling, unloading, or removing themselves.

XM Cyber successfully demonstrated this technique against notable endpoint tools on the macOS platform. For instance, a standard user account (UID 502) managed to fully unload the **CrowdStrike Falcon Sensor** through an unprotected XPC interface, effectively terminating detection, process monitoring, and network visibility. Similarly, researchers targeted the **Kandji MDM Agent**, where an unprivileged user could permanently deactivate the agent via a two-phase XPC chain by impersonating the Kandji Menu app. This action clears the EDR guard pointer and permanently disables the **Endpoint Security Framework (ESF)** extension, erasing all telemetry.

A third unnamed enterprise EDR vendor was also successfully targeted. Since this technique exploits legitimate OS behavior, it does not trigger standard security alerts and leaves minimal forensic traces.

XM Cyber researchers emphasized, "Organizations must treat this as a major gap in modern endpoint security models, particularly concerning insider threat vectors and post-compromise scenarios." The issue was promptly addressed after the companies were notified. CrowdStrike issued a patch immediately, rewarded a bounty, and enhanced detection and prevention across all supported macOS sensor versions. Kandji also patched its software and officially logged the flaw as **CVE-2026-39118**. The unnamed third company is currently working on a patch.

To assist in resolving this issue across the entire Mac network, XM Cyber has developed an open-source automated framework called **XPC Hunter** to scan for and identify these vulnerabilities. This tool is set to be released at the **Black Hat US security conference** in August 2026.

For more details, check out the full article: [Read full article](https://hackread.com/macos-flaw-users-disable-crowdstrike-kandji-security-tools/)