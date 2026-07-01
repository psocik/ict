---
title: Vulnerabilities in OFFIS DCMTK Toolkit
date: 2026-06-30
categories: [SECURITY]
tags: [OFFIS,DCMTK,VULNERABILITIES,SECURITY,HEALTHCARE]
---

## Vulnerabilities in OFFIS DCMTK Toolkit

The **OFFIS DCMTK Toolkit** has been found to have several vulnerabilities that could be exploited by attackers. 🚨

### Key Vulnerabilities:
- **CVE-2026-50003**: A path traversal vulnerability that allows unauthorized file writing.
- **CVE-2026-50254** and **CVE-2026-35505**: Memory leak vulnerabilities that can crash the service.
- **CVE-2026-52868**: Another path traversal vulnerability that allows unauthorized access to worklist records.
- **CVE-2026-44628**: A vulnerability that can crash the worklist server with a crafted query.

### Impact:
These vulnerabilities affect critical infrastructure sectors, particularly **Healthcare and Public Health**, and the toolkit is deployed worldwide. 🌍

### Recommendations:
The maintainer, OFFIS, has been notified and a fix is available in the latest commits. Users are encouraged to download the latest GitHub release once it becomes available. 🔧

For more details, you can read the full article [here](https://www.cisa.gov/news-events/ics-medical-advisories/icsma-26-181-01).