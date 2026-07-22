---
title: Vulnerabilities in Tycon Systems TPDIN-Monitor-WEB2
date: 2026-07-21
categories: [SECURITY]
tags: [TYCON,VULNERABILITIES,SECURITY,CISA]
---

## Vulnerabilities in Tycon Systems TPDIN-Monitor-WEB2

🚨 **Attention!** Recent vulnerabilities have been disclosed in **Tycon Systems TPDIN-Monitor-WEB2** that could lead to serious security risks. Successful exploitation may allow attackers to access sensitive credentials, disrupt connected infrastructure, or manipulate physical equipment, posing a potential safety risk. The affected version is **2.3.9**.

### Key Vulnerabilities

1. **CVE-2026-61884**: This critical flaw allows unauthenticated remote attackers to bypass authentication checks by submitting empty values for credential fields. This grants full access to device controls, including power relay management and network settings.

2. **CVE-2026-55985**: This vulnerability reveals that system credentials are stored in cleartext on a configuration page accessible to authenticated users, which can be exploited to compromise other systems on the local network.

### Recommendations

CISA recommends users take defensive measures to minimize the risk of exploitation:
- Minimize network exposure for all control system devices.
- Ensure devices are not accessible from the internet.
- Use firewalls to isolate control system networks from business networks.
- When remote access is necessary, utilize secure methods like **VPNs**.

CISA has not reported any known public exploitation targeting these vulnerabilities at this time. Users are encouraged to keep their systems up to date and contact Tycon Systems for further assistance.

For more details, [Read full article](https://www.cisa.gov/news-events/ics-advisories/icsa-26-202-01).