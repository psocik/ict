---
title: Researchers Detail DifyTap Flaws in Dify That Could Expose AI Chats Across Tenants
date: 2026-06-22
categories: [CYBERSECURITY]
tags: [DIFY,VULNERABILITIES,CYBERSECURITY,AI,RESEARCH]
---

## Researchers Uncover Critical DifyTap Vulnerabilities 🚨

Cybersecurity researchers have disclosed details of four vulnerabilities in **Dify**, an open-source agentic workflow platform, that could allow attackers to stealthily read artificial intelligence (AI) conversations from other customers' applications without requiring authentication. The vulnerabilities have been collectively codenamed **DifyTap** by Zafran Security.

### Key Findings 🔍
- **Two vulnerabilities** were classified as critical severity.
- **Two** required no authentication.
- **Three** had cross-tenant impact on Dify's multi-tenant cloud service, potentially exposing one customer's data to another.

Researchers Ido Shani and Gal Zaban stated, "These security defects could have allowed attackers to read private AI chats from other customers' applications, creating a covert exfiltration channel for every message and model response."

### Additional Flaws Identified ⚠️
The flaws also allowed unauthorized traversal of Dify's internal Plugin Daemon API from unauthenticated requests, enabling attackers to trigger cross-tenant internal API calls. Attackers could preview documents uploaded by other tenants and leak files across users within a tenant by attaching another user's file unique identifier.

Zafran also discovered that Dify's file parsing stack relied on a vulnerable version of PDFium (CVE-2024-5846), which could allow a remote attacker to exploit heap corruption via a crafted PDF file.

### Vulnerability Details 📊
1. **CVE-2026-41947** (CVSS score: 9.1) - Authorization bypass allowing authenticated editor users to set and enable trace configurations for any application regardless of tenant ownership.
2. **CVE-2026-41948** (CVSS score: 9.4) - Path traversal vulnerability allowing authenticated users to manipulate requests to the Plugin Daemon's internal REST API.
3. **CVE-2026-41949** (CVSS score: 7.5/5.9) - Authorization bypass in the file preview endpoint allowing any authenticated user to read up to 3,000 characters of any uploaded document across all tenants.
4. **CVE-2026-41950** (CVSS score: 6.5) - Authorization bypass allowing authenticated users to read full contents of files uploaded by other users within the same tenant.

### Conclusion 🛡️
The missing tenant ownership checks can be exploited to redirect all messages and responses from victim applications to an attacker-controlled LLM trace provider. Following responsible disclosure, all vulnerabilities except CVE-2026-41948 have been addressed in version 1.14.2, which was shipped last month. A fix for the pending flaw is expected in the next release of Dify.

For more details, [Read full article](https://thehackernews.com/2026/06/researchers-detail-difytap-flaws-in.html)