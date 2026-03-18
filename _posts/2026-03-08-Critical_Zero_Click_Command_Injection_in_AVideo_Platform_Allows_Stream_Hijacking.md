---
title: Critical Zero-Click Command Injection in AVideo Platform Allows Stream Hijacking
date: 2026-03-08
categories: [CYBER SECURITY]
tags: [AVIDEO,VULNERABILITY,CYBERSECURITY,STREAMING]
---

## Critical Zero-Click Command Injection in AVideo Platform Allows Stream Hijacking 🚨

A critical vulnerability in AVideo, a widely used open-source video hosting and streaming platform, tracked as **CVE-2026-29058**, carries a maximum severity rating. This vulnerability allows unauthenticated attackers to execute arbitrary operating system commands on the targeted server. Discovered by security researcher **Arkmarta**, it specifically affects AVideo version **6.0** and has been officially patched in version **7.0** and later releases.

### Details of the Vulnerability 🔍

Classified under **CWE-78** for the improper neutralization of special elements in an OS command, this network-based attack requires no system privileges or user interaction. If successfully exploited, attackers could achieve full server compromise, steal sensitive configuration secrets, and completely hijack live video streams.

The root cause of this severe vulnerability lies within the `objects/getImage.php` component of the AVideo platform. The issue occurs when the application processes network requests that contain a `base64Url` parameter. The platform Base64-decodes this user-supplied input and interpolates it directly into a double-quoted **ffmpeg** shell command. While the software attempts to validate the input using standard URL filters, this function only checks for basic URL syntax and fails to neutralize dangerous shell metacharacters or command substitution sequences.

### Recommended Actions 🛡️

According to the advisory on GitHub, administrators running AVideo-Encoder version **6.0** should upgrade to version **7.0** or later to secure their environments. The official patched release resolves the issue by applying strict shell argument escaping, utilizing functions like **escapeshellarg()**. This crucial fix ensures that all user-supplied input is properly sanitized before it interacts with the underlying command line, effectively preventing attackers from breaking out of the intended command structure.

If an immediate software upgrade is not feasible, security teams must deploy temporary workarounds to protect their streaming infrastructure. Administrators should strongly restrict access to the vulnerable `objects/getImage.php` endpoint at the web server or reverse proxy layer using strict IP allowlisting. Additionally, organizations should apply **Web Application Firewall (WAF)** rules designed to inspect and actively block suspicious Base64-encoded shell command patterns. As a final protective measure, administrators can turn off the image retrieval component entirely if it is not required for the platform’s daily operations.

For more information, [Read full article](https://cybersecuritynews.com/avideo-platform-vulnerability/)