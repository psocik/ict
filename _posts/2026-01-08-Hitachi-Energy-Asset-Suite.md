---
title: Hitachi Energy Asset Suite
date: 2026-01-08
categories: [VULNERABILITY]
tags: [CVE-2025-10492,REMOTE CODE EXECUTION,ENERGY,CRITICAL INFRASTRUCTURE]
---

Hitachi Energy is aware of a Jasper Report vulnerability that affects Asset Suite product versions 9.7 and prior. This vulnerability can be exploited to carry out a remote code execution (RCE) attack on the product. **CWE-502 Deserialization of Untrusted Data** is related to this issue. \n\nThe relevant advisory was initially released on `2025-12-09`. **Hitachi Energy PSIRT** has reported this vulnerability to **CISA**. Users are encouraged to update to version **9.8** to address this vulnerability. In the meantime, organizations should restrict the loading of external custom reports created by end users to only trusted Jasper reports. \n\n**CISA** recommends minimizing network exposure for all control system devices and ensuring they are not accessible from the internet. Control systems should be protected by firewalls and security best practices. Users should conduct a proper impact analysis and risk assessment before deploying any defensive measures. \n\nFor complete article, visit [CISA Advisory](https://www.cisa.gov/news-events/ics-advisories/icsa-26-008-01).