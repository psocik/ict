---
title: New Windows Security Check Could Let Apps Block Access
date: 2026-11-24
categories: [TECHNOLOGY]
tags: [WINDOWS,SECURITY,MICROSOFT,SOFTWARE]
---

## New Windows Security Check Could Let Apps Block Access 🚀

Microsoft has announced plans to introduce **Windows baseline protection**, a feature that consolidates eight existing safeguards into a single, verifiable security status. Expected to become generally available in 2027, this feature aims to simplify a familiar Windows security issue. 

### What’s New? 
The Windows baseline protection will inform users about missing protections and assist in fixing them. However, it may also lead to more notifications from software indicating that your PC isn't secure enough for use. The innovative aspect is how Windows evaluates these protections collectively and shares the results.

### Key Features: 
- **Baseline Protection Page:** A new section in Windows Settings will display which protections are lacking. 
- **One-Click Fix:** Where applicable, a single button will enable missing protections and restart the computer. 
- **Guidance for Firmware Settings:** If changes to your PC's firmware settings are necessary, such as enabling Secure Boot or the Trusted Platform Module (TPM), Windows will provide guidance.

### Intended Uses: 
Applications can utilize Windows' baseline protection signal to check a computer's security configuration, rather than maintaining their own checks. This is particularly useful for:
- Exam services verifying a student's device before a test.
- Games checking anti-cheat measures.
- Organizations requiring devices to meet security standards before granting access.

### Initial Requirements: 
The first version checks the following eight requirements:
1. **Security Processor:** Dedicated hardware like a TPM to protect sensitive information.
2. **Secure Boot:** Protection against malicious software during startup.
3. **Virtualization-Based Security:** Hardware-assisted isolation for critical processes.
4. **Memory Integrity:** Protection against malicious code in protected Windows areas.
5. **Signed Drivers Only:** Drivers must have digital signatures.
6. **Windows-Certified Drivers:** Drivers must meet Windows hardware signing requirements.
7. **Kernel Debugger Protection:** Restrictions to prevent debugging tools from bypassing security.
8. **Vulnerable Driver Protection:** Safeguards against known vulnerable drivers that could compromise security.

This feature is currently in preview, and Microsoft is seeking feedback to refine it before its general availability.

For more details, you can read the full article here: [Read full article](https://www.malwarebytes.com/blog/news/2026/11/new-windows-security-check-could-let-apps-block-access)