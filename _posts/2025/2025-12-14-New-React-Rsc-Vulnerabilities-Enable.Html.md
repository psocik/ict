---
title: New React Rsc Vulnerabilities Enable.Html
date: 2025-12-14
categories: [VULNERABILITIES]
tags: [REACT,SECURITY,VULNERABILITY,CVE]
---

The React team has issued critical fixes addressing two new categories of vulnerabilities within React Server Components (RSC), which could lead to denial-of-service (DoS) or exposure of source code. These flaws were uncovered by the security community during attempts to exploit patches for CVE-2025-55182, a critical vulnerability with a CVSS score of 10.0 that is currently being exploited in the wild. This pattern of post-patch vulnerability discovery highlights the continuous scrutiny applied to critical security updates.

Specifically, two denial-of-service vulnerabilities have been identified. CVE-2025-55184, with a CVSS score of 7.5, is a pre-authentication DoS vulnerability stemming from unsafe deserialization of payloads in HTTP requests directed at Server Function endpoints. This can trigger an infinite loop, causing the server process to hang and potentially preventing future HTTP requests from being served. An incomplete fix for this initial vulnerability led to the discovery of CVE-2025-67779, also rated 7.5, which exhibits the same DoS impact.

A third vulnerability, CVE-2025-55183 (CVSS score: 5.3), presents an information leak risk. A specially crafted HTTP request sent to a vulnerable Server Function could return the source code of any Server Function. However, successful exploitation of CVE-2025-55183 requires a Server Function that explicitly or implicitly exposes an argument converted into a string format. These flaws affect various versions of `react-server-dom-parcel`, `react-server-dom-turbopack`, and `react-server-dom-webpack`. CVE-2025-55184 and CVE-2025-55183 impact versions 19.0.0, 19.0.1, 19.1.0, 19.1.1, 19.1.2, 19.2.0, and 19.2.1, while CVE-2025-67779 affects 19.0.2, 19.1.3, and 19.2.2.

Security professionals are strongly advised to update to versions 19.0.3, 19.1.4, and 19.2.3 immediately to mitigate these risks. This recommendation is particularly urgent given the active exploitation of the related CVE-2025-55182, which indicates a heightened threat landscape for React Server Components. The React team emphasized that when a critical vulnerability is disclosed, researchers often scrutinize adjacent code paths for variant exploit techniques, a common industry pattern that, while leading to additional disclosures, signifies a healthy and proactive security response cycle.

To read the complete article see: [The Hacker News](https://thehackernews.com/2025/12/new-react-rsc-vulnerabilities-enable.html)