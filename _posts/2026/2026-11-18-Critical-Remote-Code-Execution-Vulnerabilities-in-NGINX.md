---
title: Critical Remote Code Execution Vulnerabilities in NGINX
date: 2026-11-18
categories: [SECURITY]
tags: [NGINX,VULNERABILITIES,SECURITY,REMOTE-CODE-EXECUTION]
---

## Critical Remote Code Execution Vulnerabilities in NGINX 🚨

Wiz Research, Ikotas Labs, Metnir, Rapid7, and Xint have independently uncovered two critical remote code execution vulnerabilities in NGINX, the software widely used to manage traffic for production applications and APIs. As the world's most popular open-source web server, NGINX powers over 225 million websites. 

### Vulnerabilities Overview

Successful exploitation of these vulnerabilities could allow attackers to:
- Take control of affected NGINX servers
- Steal sensitive data
- Tamper with websites
- Disrupt services

The vulnerabilities, tracked as **CVE-2026-123633** and **CVE-2026-123007**, are both rated Critical, with a CVSS score of **9.2**. Both require HTTP/2 to be enabled on the affected NGINX server, and CVE-2026-123007 affects versions dating back to NGINX **1.9.5** from 2015.

### Discovery and Reporting

These vulnerabilities were reported to F5, the company behind NGINX, and collaboration with its security team led to remediation and coordinated disclosure. The responsible disclosure timeline indicates:
- On **October 21, 2026**, Wiz reported the HTTP/2 use-after-free vulnerability (CVE-2026-123633) to F5.
- On **November 16, 2026**, Wiz reported the second vulnerability (CVE-2026-123007).
- Public disclosure occurred on **November 18, 2026**.

### Recommendations

Organizations should identify affected deployments and apply security updates as soon as they are released. We recommend updating NGINX deployments to the latest version, which includes multiple security fixes. However, turning a published fix into protection in production requires substantial manual work, including validating patches and coordinating rollouts with service owners.

For more details, please read the full article: [Read full article](https://www.wiz.io/blog/nginx-http2-rce-vulnerabilities) 
