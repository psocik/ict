---
title: Critical Vulnerabilities in GE Vernova Enervista UR Setup
date: 2026-02-17
categories: [SECURITY]
tags: [GE,VULNERABILITIES,ENERVISTA,SECURITY,CISA]
---

## Critical Vulnerabilities in GE Vernova Enervista UR Setup 🚨

The recent advisory from ICS-CERT highlights significant vulnerabilities in the **GE Vernova Enervista UR Setup**. Successful exploitation of these vulnerabilities may allow code execution with elevated privileges. The affected versions are those prior to **8.70** (CVE-2026-1762, CVE-2026-1763).

### Impacted Sectors 🌍
These vulnerabilities impact critical infrastructure sectors, including:
- **Critical Manufacturing**
- **Energy**
- **Water and Wastewater**

### Vulnerability Details 🔍
1. **DLL Hijacking**: The installer for versions prior to 8.70 is vulnerable to DLL hijacking. Running the installer in a location with untrusted DLLs could allow an attacker to gain code execution with administrative privileges. The relevant CWE is **CWE-427 Uncontrolled Search Path Element**.
2. **Directory Traversal**: There is also a vulnerability related to directory traversal when opening certain firmware update files, which could allow an attacker to write to files on the filesystem with the privileges of the logged-in user. The relevant CWE is **CWE-35 Path Traversal**.

### Recommendations ✅
GE Vernova recommends that affected users upgrade to patched versions of Enervista UR Setup: **Versions 8.70 or later**. Currently, there are no known public exploitations targeting these vulnerabilities reported to CISA.

### Defensive Measures 🛡️
CISA advises users to take defensive measures to minimize the risk of exploitation:
- Minimize network exposure for all control system devices.
- Ensure devices are not accessible from the internet.
- Use firewalls to isolate control system networks from business networks.
- When remote access is necessary, utilize secure methods such as **Virtual Private Networks (VPNs)**.

For more detailed information, please refer to the full advisory: [Read full article](https://www.cisa.gov/news-events/ics-advisories/icsa-26-048-03)