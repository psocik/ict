---
title: Mitsubishi Electric MELSOFT Update Manager Vulnerabilities
date: 2026-06-30
categories: [CYBERSECURITY]
tags: [MITSUBISHI,MELSOFT,VULNERABILITIES,CYBERSECURITY,UPDATE]
---

## Mitsubishi Electric MELSOFT Update Manager Vulnerabilities 🚨

Mitsubishi Electric has announced critical vulnerabilities in the MELSOFT Update Manager SW1DND-UDM-M. Successful exploitation of these vulnerabilities could allow a local attacker to tamper with or destroy information, cause a denial-of-service condition, or execute arbitrary code when a specially crafted archive file is decompressed by the 7-Zip component included in the software.

### Affected Versions
The following versions are affected:
- >=1.000A
- <=1.014Q

### Vulnerabilities Identified
These vulnerabilities are tracked as:
- **CVE-2025-53816**: Heap-based buffer overflow vulnerability.
- **CVE-2025-53817**: NULL pointer dereference vulnerability.
- **CVE-2025-55188**: Link following vulnerability.
- **CVE-2025-11001**: Additional vulnerability.

### Recommended Actions
Mitsubishi Electric is releasing a fixed version 1.015R or later to address these issues. Users are advised to download and install the update from the following link:
[Download Update](https://www.mitsubishielectric.co.jp/fa/download/index.html) (This site is in Japanese).

For more information on the fixed version, refer to the Mitsubishi Electric security advisory:
[Read full advisory](https://www.mitsubishielectric.com/psirt/vulnerability/pdf/2026-004_en.pdf).

### Additional Recommendations
For users unable to update immediately, Mitsubishi Electric recommends:
- Using the affected product within a LAN.
- Blocking remote logins from untrusted networks.
- Implementing firewalls or VPNs to prevent unauthorized access.
- Restricting physical access to the affected PC.
- Avoiding clicking on untrusted links or opening attachments.
- Installing anti-virus software on the affected PC.

Stay safe and ensure your systems are updated! 🚀